### Database Connection

```js
let db_user = 'root',
    db_pass = '',
    db_name = 'unpossible'

const db = new Sequelize(db_name, db_user, db_pass, {
    host: 'localhost',
    dialect: 'mysql',
    logging: false,
})
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
