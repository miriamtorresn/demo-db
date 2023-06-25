# Initial setup

These are the instructions to run our local server based on docker-compose configuration

### Run mongodb

```sh
docker-compose up -d mongodb
```

### Validate that mongo db is running

```sh
docker-compose ps
```

### Stop container

```sh
docker stop demo-db
```

### Remove container

```sh
docker rm demo-db
```

# Using the database

### Enter mongo basj

```sh
exec mongodb bash
```

### Access to the shell (mongosh)

You can use the MongoDB for Visual Studio Code for getting the link for your db connection

```sh
mongosh "mongodb://root:root@localhost:27017/?authSource=admin&readPreference=primary&ssl=false&directConnection=true"
```

### Creating a collection

```sh
use users # for creating a db
```

### Inserting a document

```sh
db.users.insertOne({name:"Miguel"})
```

### Finding documents into a collection

```sh
db.users.find()
```

### Deleting a document

```sh
db.users.deleteOne({_id: ObjectId("6497dd0fbf6b14a4c0918ac5")})
```

### Get available databases

```sh
show dbs
```

### Get available collections

```sh
show collections
```

# Connect within your project through .mongodb file

```sh
use("lsm-db")
db.users.find
```
