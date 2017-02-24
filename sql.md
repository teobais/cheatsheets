COALESCE() function returns the first non-NULL value of a list, or NULL if there are no non-NULL values.
example: 
mysql> SELECT COALESCE(NULL, 2, 3);
+----------------------+
| COALESCE(NULL, 2, 3) |
+----------------------+
|                    2 |
+----------------------+


Add extra column in a select statement and give it a default value: select ..., ... , ..., 'John' as NAME
The above statement will add a column in the result set with the name of NAME and the value of John for every result of the select statement.
