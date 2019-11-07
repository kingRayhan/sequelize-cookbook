### Database Connection

```bash
# One of the following:
$ npm install --save pg pg-hstore # Postgres
$ npm install --save mysql2
$ npm install --save mariadb
$ npm install --save sqlite3
$ npm install --save tedious # Microsoft SQL Server
```

```js
let db_user = 'root',
    db_pass = '',
    db_name = 'unpossible'

const db = new Sequelize(db_name, db_user, db_pass, {
    host: 'localhost',
    dialect: 'mysql', /* one of 'mysql' | 'mariadb' | 'postgres' | 'mssql' */
    logging: false,
})
```

**Or Using Connection string**

```js
const sequelize = new Sequelize('mariadb://user:password@example.com:9821/database')
```


### Check DB Connection

```js
db.authenticate()
    .then(() => {
        console.log('Connection has been established successfully.')
    })
    .catch(err => {
        console.error('Unable to connect to the database:', err)
    })
```

### Migrate database

```js
db.sync()
```

**Migrate forcefully**

```js
db.sync({ force: true })
```
