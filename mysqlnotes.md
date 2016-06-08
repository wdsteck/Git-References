# MySQL Package Information

MySQL Details:
  * [Wiki](https://en.wikipedia.org/wiki/MySQL)
  * [MySQL Home](http://www.mysql.com)
  * [Install MySQL Server on computer](http://dev.mysql.com/doc/refman/5.7/en/installing.html)
  * [Guide to Install MySQL R packages](http://biostat.mc.vanderbilt.edu/wiki/Main/RMySQL)
  * [CRAN R MySQL Package](https://cran.r-project.org/web/packages/RMySQL/RMySQL.pdf)
  * [MySQL Commands](http://www.pantz.org/software/mysql/mysqlcommands.html) - Do not Delete, Add or Join from ensembl. Only Select!
  * [Nice Blog Post on R and MySQL](http://www.r-bloggers.com/mysql-and-r/)

  ```
  install.packages("RMySQL")
  require("RMySQL")
  ```
  
  Example Use:
  
  List the databases in the ucsc.edu genome site:
  ```
  # Open the connection to the Db
  ucscDB <- dbConnect(MySQL(), user="genome", host="genome-mysql.cse.ucsc.edu")
  # send the SQL command "show databases" to get a list of all the databases
  # on the server
  result <- dbGetQuery(ucscDB,"show databases;")
  # and then disconnect the connection
  dbDisconnect(ucscDB)
  ```
  
  Look at one particular database - the 19th version of the human genome (hg19)
  ```
  # this time, connect to the Db
  hg19 <- dbConnect(MySQL(), user="genome", db="hg19", host="genome-mysql.cse.ucsc.edu")
  # list all the tables within that Db
  allTables <- dbListTables(hg19)
  # length of allTables shows lots of tables in this Db
  length(allTables)
  # what are the first 5 tables
  allTables[1:5]
  
  # look at the fields in table "affyU133Plus2"
  dbListFields(hg19, "affyU133Plus2")
  
  # count the number of records in table "affyU133Plus2"
  dbGetQuery(hg19, "select count(*) from affyU133Plus2")
  
  # read data out of the table
  affyData <- dbReadTable(hg19, "affyU133Plus2")
  head(affyData)
  
  # Query a subset of the table to get all rows where the misMatches column has a value between 1 and 3
  # first, send the request
  query <- dbSendQuery(hg19, "select * from affyU133Plus2 where misMatches between 1 and 3")
  # then, get the resulting data
  affyMis <- fetch(query)
  quantile(affyMis$misMatches)
  
  affyMisSmall <- fetch(query, n=10)
  
  # after done querying, must clear the query request.
  dbClearResult(query)
  dim(affyMisSmall)
  
  # Disconnect
  dbDisconnect(hg19)
  ```
