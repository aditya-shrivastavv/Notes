# MongoDB

## Setup

Here is the setup of monogoDB on windows using docker.

```bash
docker run --name test-mongo -dit -p 27017:27017 -rm mongo
```

```bash
docker exec -it test-mongo mongo
# this will open the mongo shell
```

## Basics

The query language of mongodb is just javascript. Syntax is same.
**These commands are executed in the mongo shell.**

```bash
# show all databases
show dbs;
```

> Semi-colon is not essential but it is recommended to use it.

```bash
# create a database
use <databaseName>;
```

> If the database does not already exist, it will be created otherwise you will be switched.

```bash
# first entry
db.<collectionName>.insertOne({<key>: <value>});
```

```bash
# for getting info about the queries you can use on a collection
db.<collectionName>.help();

# for getting info about the queries you can use on a database
db.help();

# database status
db.status();
```

> db = active database

If some query ran successfully then, prompt will say `"acknowledged": true` and an object id will be generated for the new entry.
