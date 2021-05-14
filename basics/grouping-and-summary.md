# Aggregation, Counting, Sum

## Aggregation

{% code title="Employee table" %}
```
id          name        age     
----------  ----------  ----------
1           retsu       7         
2           kana        5         
3           auri        4         
4           antek       4         
5           leri             
```
{% endcode %}

### Counting number of rows

```sql
SELECT COUNT(*) FROM employee; --Counts all rows
```

```text
COUNT(*)
----------
5
```

### Counting non-null rows of a specified column

```sql
SELECT COUNT(age) FROM employee;
```

```text
COUNT(age)
----------
4
```

{% hint style="info" %}
Omits the count for "leri" because of NULL age.
{% endhint %}

{% hint style="info" %}
COUNT\(\*\) is really just COUNT\(id\) since primary key id's are never NULL.
{% endhint %}

### Counting Unique occurrences

```sql
SELECT COUNT(DISTINCT age) FROM employee;
```

```text
COUNT(DISTINCT age)
----------
2
```

{% hint style="info" %}
Omits NULL age and does not double count repeats
{% endhint %}

### Summation of data in a column

```sql
SELECT SUM(age) FROM employee;
```

```text
SUM(age)
----------
28
```

{% hint style="info" %}
Notice the title of the new table comes from the selection query.
{% endhint %}

#### Some Extra SQL aggregation queries

```sql
SELECT COUNT(*) FROM employee WHERE age=4;
SELECT MAX(age) FROM employee;
SELECT MIN(age) FROM employee;
```



