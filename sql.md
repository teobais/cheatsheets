COALESCE() function returns the first non-NULL value of a list, or NULL if there are no non-NULL values.
example: 

`mysql> SELECT COALESCE(NULL, 2, 3);`

```sql
+----------------------+
| COALESCE(NULL, 2, 3) |
+----------------------+
|                    2 |
+----------------------+
```

Add extra column in a select statement and give it a default value: select ..., ... , ..., 'John' as NAME
The above statement will add a column in the result set with the name of NAME and the value of John for every result of the select statement.

### Cascading
`ON DELETE CASCADE` actually means "leave no orphans", which means that when a Parent row is deleted (killed), no orphan row should stay alive in the Child table. [Read more](https://dba.stackexchange.com/a/44962).
