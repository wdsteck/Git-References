#HDF5
* [HDF Group](http://www.hdfgroup.org/HDF5)
* [BioConductor HDF5 Tutorial](http://www.bioconductor.org/packages/release/bioc/vignettes/rhdf5/inst/doc/rhdf5.pdf)

  To Install, must install from the bioclite web page:
  ```
  source("http://www.bioconductor.org/biocLite.R")
  biocLite("rhdf5")
  require(rhdf5)
  file <- "example.h5"
  created <- h5createFile(file)
  h5createGroup(file,"foo")
  h5createGroup(file,"baa")
  h5createGroup(file,"foo/foobaa")
  h5ls(file)

  A = matrix(1:10, nr=5, nc=2)
  h5write(A, file, "foo/A")
  B = array(seq(0.1, 2.0, by=0.1), dim=c(5, 2, 2))
  attr(B, "scale") <- "liter"
  h5write(B, file, "foo/B")
  C = matrix(paste(LETTERS[1:10], LETTERS[11:20], collapse=""), nr=2, nc=5)
  h5write(C, file, "foo/foobaa/C")

  # write a complex data frame
  df = data.frame(1L:5L, seq(0, 1, length.out=5), c("ab", "cde", "fghi", "a", "s"), stringsAsFactors=FALSE)
  h5write(df, file, "df")

  # reading the structures that we wrote
  h5ls(file)
  D = h5read(file, "foo/A")
  E = h5read(file, "foo/B")
  F = h5read(file, "foo/foobaa/C")
  G = h5read(file, "df")

  class(D); D; class(E); E; class(F); F; class(G); G

  # to write to a portion of a structure, use the index parameter
  h5write(c(12:14), file, "foo/A", index = list(1:3, 1))
  h5read(file, "foo/A")
  ```
