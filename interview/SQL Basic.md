Here are some basic examples of SQL queries:

**SELECT**

The `SELECT` statement is used to retrieve data from a database.

```sql
SELECT * FROM users;
```

This query selects all rows and columns from the `users` table.


```sql
SELECT username, email FROM users;
```

This query selects the `username` and `email` columns from the `users` table.


**WHERE**

The `WHERE` clause is used to filter the results of a `SELECT` query.

```sql
SELECT * FROM users WHERE age > 18;
```

This query selects all rows from the `users` table where the `age` column is greater than 18.

```sql
SELECT * FROM users WHERE username = 'john';
```

This query selects all rows from the `users` table where the `username` column is 'john'.

**INSERT**

The `INSERT` statement is used to add new rows to a table.

```sql
INSERT INTO users (username, email, age) VALUES ('john', 'john@example.com', 25);
```

This query adds a new row to the `users` table with the values 'john', '[john@example.com](mailto:john@example.com)', and 25 for the `username`, `email`, and `age` columns, respectively.

**UPDATE**

The `UPDATE` statement is used to modify existing rows in a table.

```sql
UPDATE users SET age = 26 WHERE username = 'john';
```

This query updates the `age` column of the row in the `users` table where the `username` column is 'john' to 26.

**DELETE**

The `DELETE` statement is used to delete rows from a table.

```sql
DELETE FROM users WHERE username = 'john';
```

This query deletes the row from the `users` table where the `username` column is 'john'.

I hope these examples are helpful! Let me know if you have any questions.