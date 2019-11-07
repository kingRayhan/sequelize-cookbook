# Update

```js
async function updatePost() {
    let post = await Blog.update(
        {
            title: 'title Updated',
        },
        {
            where: { id: 5 },
        }
    )
    console.log(post)
}

async function updatePostCategories() {
    let post = await Blog.findOne({
        where: { id: 16 },
        include: [User, Category],
        // attributes: { exclude: ['userId'] },
        // attributes: ['title', 'body', ['id', 'name']],
    })
    post.setCategories([1, 2])

    console.log(JSON.stringify(post, undefined, 4))
}
```
