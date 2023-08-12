
# debezium-mongodb-example

It is a project that aims to learn how to use Debezium and mongo db.




## Installation

For running whole app layer

```bash
  docker-compose up
```
    
## License

[MIT](https://choosealicense.com/licenses/mit/)


## Run Locally

Need to send POST with json

```bash
  http://localhost:8083/connectors/
```




## Screenshots

![App Screenshot](https://i.imgur.com/wXcSSuB.png)


## FAQ

#### Connector Class (connector.class)

This parameter specifies the type of connector Debezium will use to connect to the target database. In this case, it's using the io.debezium.connector.mongodb.MongoDbConnector, indicating that Debezium is using a specialized connector for MongoDB.

#### Number of Tasks (tasks.max)

This parameter defines the maximum number of parallel tasks that can be run. In this example, only 1 task is allowed, indicating the intention to monitor data changes with a single task.

#### MongoDB Connection String (mongodb.connection.string)

This parameter holds the connection string used to connect to the MongoDB database. The connection string includes the address of the MongoDB server, authentication credentials, and other connection details.

#### Kafka Topic Prefix (topic.prefix)

This parameter specifies the prefix for Kafka topics created by Debezium. In this case, all topics will start with the "quiz" prefix.

#### MongoDB SSL Enabled (mongodb.ssl.enabled)

This parameter determines whether SSL is used for the MongoDB connection. It's set to true, indicating that a secure connection is being used.

#### MongoDB Member Auto-Discovery (mongodb.members.auto.discover)

This parameter controls whether MongoDB members (e.g., replica set members) will be automatically discovered. It's set to true, indicating that Debezium will automatically discover MongoDB members.

#### Capture Mode (capture.mode)

This parameter defines how Debezium will capture data changes in MongoDB. It's set to "change_streams_update_full," indicating that all document changes, including updates, will be captured.

#### Snapshot Mode (snapshot.mode)

This parameter specifies how Debezium's snapshot mode is configured. It's set to "never," meaning that snapshot mode is disabled.

#### Included Databases (database.include.list)

This parameter specifies the list of databases to be monitored. "quiz" database is specified, which means that only changes in the "quiz" database will be monitored.

#### Included Collections (collection.include.list)

This parameter specifies the list of collections to be monitored. "quiz.users" collection is specified, indicating that changes in the "users" collection within the "quiz" database will be monitored.

#### Skipped Operations (skipped.operations)

This parameter specifies the list of collections to be monitored. "quiz.users" collection is specified, indicating that changes in the "users" collection within the "quiz" database will be monitored.

#### Transformations (transforms)

This parameter specifies the transformations applied to the data stream. In this case, the "unwrap" transformation is used.

#### "Unwrap" Transformation Type (transforms.unwrap.type)

This parameter specifies the type of the "unwrap" transformation. It extracts the new document state from the change stream.

#### "Unwrap" Transformation Add Headers (transforms.unwrap.add.headers)

This parameter specifies whether the "unwrap" transformation should add headers. It's set to "op," which means that an operation type header will be added. This header is useful for distinguishing the type of operation that occurred, making it easier to handle the data on the Kafka topic.





