# DSE4.8Spark_MSSQL
# Connecting from DSE 4.8 Spark to MS SQL server

#Get sqljdbc4.jar from MSDN

cd /usr/share/dse/resources/spark/lib/

sudo cp  ~/Downloads/sqljdbc_4.2/enu/sqljdbc4.jar .

sudo chown cassandra:cassandra sqljdbc4.jar 

sudo chmod 644 sqljdbc4.jar


#restart cluster

scala> val resultsDF = csc.load("jdbc", Map( "driver" -> "com.microsoft.sqlserver.jdbc.SQLServerDriver", "url" -> "jdbc:sqlserver://xxx.xxx.xxx.xxx:1433;database=xxxxx;user=xxxxx;password=xxxxx;trustServerCertificate=false;loginTimeout=30;", "dbtable" -> "xxx"))
scala> println(resultsDF.count())
