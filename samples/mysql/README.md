# MySQL Sample

CobolScript can access MySQL server using a Node.js module.

## Setup

Install [Node.js](http://nodejs.org).

Then, execute at command line:
```
npm install
```

This command installs the `mysql` module, according to the dependecies described in `package.json` file.

## Run

With the command line:
```
node run showdb.cob
```

The program connects to the MySQL server at localhost and list its database. The server must be running.

The code
```
perform require using "mysql" giving mysql.
```
loads the `mysql` module.

Then
```
local options.

move object to options.
move "root" to user in options.
move "" to password in options.

local connection.

perform createConnection in mysql using options giving connection.
```
opens the connection.

The code
```
perform query in connection using "show databases" showdbs.

showdbs section using err, rows, fields.
* ....
```
pass `showdbs` as a callback to asynchronous method `query` in `connection`. The callbacks accept three parameters.



