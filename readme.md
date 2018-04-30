# Spark SQL Hints and Tips
### Hive QL integration

The thing about Spark SQL is that it fully supports Hive QL. It achieves this using the Apache Hive language parsers
written into the Hive library.

Check out the usage:
```scala
val sqlContext = new SQLContext(new SparkContext(new SparkConf))

// let the magic happen
sqlContext.sql("USE default") 

// pretty neat huh? integrates with the Hive Metastore just like that
sqlContext.sql("Select acsii(family_name) from accounts")

// Here you can see the ascii function being used
```