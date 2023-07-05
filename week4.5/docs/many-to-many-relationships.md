# Many-to-many Relationships

## 1. exercise using the blog database

Use a SELECT query with a JOIN to retrieve all the posts associated with the tag 'travel'. You should get the following result set:

```bash
 id |          title          
----+-------------------------
  4 | My weekend in Edinburgh
  6 | A foodie week in Spain
```

**solution:**

```bash
SELECT posts.id, posts.title
FROM posts
JOIN posts_tags ON posts_tags.post_id = posts.id
JOIN tags ON posts_tags.tag_id = tags.id
WHERE tags.name = 'travel';
```

## 1. challenge using the blog database

Use SQL to insert a new tag 'sql' and associate the post titled 'SQL basics' with this tag.

Then use a SELECT query with a JOIN to retrieve all posts associated with the tag 'sql' and verify the above worked.

**solution:**

```bash

```