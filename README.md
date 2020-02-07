Setup
-----

using imports to use this class:
```
using System;
using System.Data.SQLite;
using System.Data;
```

`System.Data.SQLite` must be installed through NuGet. Follow the example below to install:

GIF EXAMPLE PLACEHOLDER.

Usage
-----

The methods to manage the data are the following.

`Query("<Query string>");`

`Fetch("<Query string>");`

Create database
-----

To create a database you need to create a `SQLite` object and to perform any kind of query. The database will be automatically created.

Here is an example of creating a SQLite object:

```
string sQLite_database_path = "C:\\Users\\user\\Desktop\\SQLITEDATABASE.db";
SQLite sqlite = new SQLite(sQLite_database_path);
```

Query method
-----

The `Query` method can be used to perform either `INSERT`, `UPDATE`, and `DELETE`. The usage is the following:

To peform a query without a console output message:

`sqlite.Query("<Query string>")`

To peform a query with a console output message:

`sqlite.Query("<Query string>","<Console log message string>")`

Examples of `CREATE TABLE`, `INSERT`, `UPDATE`, and `DELETE`.
```
string sQLite_database_path = "C:\\Users\\JMV\\Desktop\\SQLITE DATABASE.db";
SQLite sqlite = new SQLite(sQLite_database_path);

//Create database and first table.
sqlite.Query("CREATE TABLE 'USER' " +
"('id' INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE" +
",'user_name' TEXT" +
", 'role' INTEGER);", "Table USER created.");

//Insert query.
sqlite.Query("INSERT INTO USER ('user_name','role') VALUES ('user0',1)", "User inserted.");
sqlite.Query("INSERT INTO USER ('user_name','role') VALUES ('user1',2)", "User inserted.");
sqlite.Query("INSERT INTO USER ('user_name','role') VALUES ('user2',1)", "User inserted.");
sqlite.Query("INSERT INTO USER ('user_name','role') VALUES ('user3',3)", "User inserted.");
sqlite.Query("INSERT INTO USER ('user_name','role') VALUES ('user4',1)", "User inserted.");

//Update query.
sqlite.Query("UPDATE USER SET user_name = 'user000' WHERE id = 1", "User updated.");

//Delete query.
sqlite.Query("DELETE FROM USER WHERE id = 5");
```

Console output result: 

```
Query successful. Table USER created.
Query successful. User inserted.
Query successful. User inserted.
Query successful. User inserted.
Query successful. User inserted.
Query successful. User inserted.
Query successful. User updated.
Query successful.
```

Fetch method
-----
