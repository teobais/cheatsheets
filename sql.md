COALESCE() function returns the first non-NULL value of a list, or NULL if there are no non-NULL values.
example: 
mysql> SELECT COALESCE(NULL, 2, 3);
+----------------------+
| COALESCE(NULL, 2, 3) |
+----------------------+
|                    2 |
+----------------------+
