# Sequelize Read/Fetch API

### FindAll

```js
Blog.findAll({
    include: [User, Category],
    orderBy: [['id', 'DESC']],
})
    .then(res => console.log(JSON.stringify(res, undefined, 4)))
    .catch(e => console.log(e))
```

### FindOne

```js
User.findOne({
    where: { id: 4 },
    include: [Blog],
})
    .then(res => console.log(JSON.stringify(res, undefined, 4)))
    .catch(e => console.log(e))
```
