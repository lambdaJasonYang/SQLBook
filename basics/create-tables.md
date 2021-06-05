# Create Tables and Basic query

### CREATE TABLE

```sql
CREATE TABLE employees (id INTEGER PRIMARY KEY, name TEXT, age INTEGER);
```

{% hint style="info" %}
 id \( PRIMARY KEY\) of the table -- it identifies each row in the table and allows us to conveniently refer to any row.
{% endhint %}

### INSERT INTO , filling data:

```sql
INSERT INTO employee 
    (name,age) 
    VALUES 
        ('bob',47);
        ('ann',32);
```

```text
id          name        age     
----------  ----------  ----------
1           bob         47    
2           ann         32
```

### Null Data

If we omit some parameter in VALUES, we get default value. The default value in our case is NULL.

```sql
INSERT INTO employee (name,age) VALUES ('rex');
```

```text
id          name        age     
----------  ----------  ----------
1           rex   
```

### Basic SQL Queries

```sql
SELECT * FROM employee;
SELECT * FROM employee WHERE name='lancor';
SELECT * FROM employee WHERE age>=16 AND hinta<=36;
SELECT * FROM employee ORDER BY name; --ORDER defaults ASC smallest to largest
SELECT * FROM employee ORDER BY name DESC; --largest to smallest
```

{% hint style="info" %}
ORDER BY -- defaults ordering to ASC  
 smallest on top -&gt; largest on bottom of table
{% endhint %}

### SELECT DISTINCT, merge repeats

DISTINCT -- like using python set\(\) on lists; removes repeats

{% tabs %}
{% tab title="SQL" %}
```sql
SELECT DISTINCT age FROM employee;
```
{% endtab %}

{% tab title="Input" %}
```
id          age     
----------  ----------
1            4
2            2
3            4
4            8


```
{% endtab %}

{% tab title="Output" %}
```
age               
----------  
4            
2            
8        

```
{% endtab %}
{% endtabs %}

### UPDATE data in table

```sql
UPDATE employee SET name='anna', age=9 WHERE id=2;
UPDATE employee SET age=age+1 WHERE id=2;

UPDATE Tuotteet SET age=age+1; --updates all rows 
```

{% hint style="info" %}
UPDATE all rows by omitting the WHERE conditional as shown in last query.
{% endhint %}

### DELETE data from table

```sql
DELETE FROM employee WHERE id=5;

DELETE FROM employee; --deletes all rows, results in empty table
```

{% hint style="info" %}
Transform into an empty table by omitting the WHERE conditional.
{% endhint %}

### DROP entire table

```sql
DROP TABLE employee;
```

{% hint style="info" %}
Unlike DELETE FROM employee,   
DROP TABLE employee, means you cannot refer to the table anymore.
{% endhint %}



