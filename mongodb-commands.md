# MongoDB Basic & Useful Commands

## Connect to MongoDB

Connect to the local MongoDB shell:

```bash
mongosh
```

Connect to a specific host, port, and database:

```bash
mongosh "mongodb://<host>:<port>/<database_name>"
```

Connect with authentication:

```bash
mongosh -u <username> -p <password> --authenticationDatabase admin
```

Connect using a connection string (e.g. Atlas):

```bash
mongosh "mongodb+srv://<username>:<password>@<cluster-url>/<database_name>"
```

## Show Databases

```javascript
show dbs
```

## Switch / Create Database

```javascript
use mydb
```

## Show Collections

```javascript
show collections
```

## Create Collection

```javascript
db.createCollection("users")
```

## Drop Database

```javascript
db.dropDatabase()
```

## Drop Collection

```javascript
db.users.drop()
```

## Insert Data

Insert a single document:

```javascript
db.users.insertOne({ name: "John", age: 30 })
```

Insert multiple documents:

```javascript
db.users.insertMany([{ name: "Jane", age: 25 }, { name: "Bob", age: 40 }])
```

## Query Data

Find all documents:

```javascript
db.users.find()
```

Find with a filter (pretty printed):

```javascript
db.users.find({ age: { $gt: 25 } }).pretty()
```

Find a single document:

```javascript
db.users.findOne({ name: "John" })
```

## Update Data

Update a single document:

```javascript
db.users.updateOne({ name: "John" }, { $set: { age: 31 } })
```

Update multiple documents:

```javascript
db.users.updateMany({ age: { $lt: 30 } }, { $set: { active: true } })
```

## Delete Data

Delete a single document:

```javascript
db.users.deleteOne({ name: "John" })
```

Delete multiple documents:

```javascript
db.users.deleteMany({ active: false })
```

## Count Documents

```javascript
db.users.countDocuments({ age: { $gte: 18 } })
```

## Create Index

```javascript
db.users.createIndex({ name: 1 })
```

## List Indexes

```javascript
db.users.getIndexes()
```

## User Management

Create a user with roles:

```javascript
db.createUser({
  user: "myuser",
  pwd: "mypassword",
  roles: [{ role: "readWrite", db: "mydb" }]
})
```

List all users in the current database:

```javascript
db.getUsers()
```

Drop a user:

```javascript
db.dropUser("myuser")
```

## Backup with mongodump

Dump all databases to the default `dump/` directory:

```bash
mongodump
```

Dump a specific database:

```bash
mongodump --db <database_name> --out /path/to/backup
```

Dump a specific collection:

```bash
mongodump --db <database_name> --collection <collection_name> --out /path/to/backup
```

Dump with authentication:

```bash
mongodump --uri="mongodb://<username>:<password>@<host>:<port>/<database_name>?authSource=admin" --out /path/to/backup
```

Dump to a compressed archive file:

```bash
mongodump --db <database_name> --archive=/path/to/backup.archive --gzip
```

## Restore with mongorestore

Restore from a backup directory:

```bash
mongorestore /path/to/backup
```

Restore a specific database:

```bash
mongorestore --db <database_name> /path/to/backup/<database_name>
```

Restore into a different database:

```bash
mongorestore --nsFrom "olddb.*" --nsTo "newdb.*" /path/to/backup
```

Restore from a compressed archive file:

```bash
mongorestore --archive=/path/to/backup.archive --gzip
```

Drop existing collections before restoring:

```bash
mongorestore --drop /path/to/backup
```

## Export with mongoexport

Export a collection to JSON:

```bash
mongoexport --db <database_name> --collection <collection_name> --out data.json
```

Export a collection to CSV:

```bash
mongoexport --db <database_name> --collection <collection_name> --type=csv --fields name,age --out data.csv
```

## Import with mongoimport

Import a JSON file into a collection:

```bash
mongoimport --db <database_name> --collection <collection_name> --file data.json
```

Import a CSV file with headers:

```bash
mongoimport --db <database_name> --collection <collection_name> --type=csv --headerline --file data.csv
```

## Server Status & Stats

Check server status:

```javascript
db.serverStatus()
```

Show database stats:

```javascript
db.stats()
```

Show collection stats:

```javascript
db.users.stats()
```

## Exit the Shell

```javascript
exit
```
