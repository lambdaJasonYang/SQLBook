# Strings

### Concat with \|\|

Becoming a super hero is a fairly straight forward process:

```sql
select surname || ', ' || firstname as name from cd.members 
--"BOB" + ", " + "JONES"
--outputs "BOB, JONES"
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

### case insensitive search

simply make everything upper -case

{% code title="hello.sh" %}
```bash
select * from cd.facilities where upper(name) like 'TENNIS%';      
```
{% endcode %}

### regex w/ SIMILAR

```bash
select memid, telephone from cd.members where telephone similar to '%[()]%';
```

### Padding with LPAD

```bash
select lpad(cast(zipcode as char(5)),5,'0') zip from cd.members order by zip 
--output with have length 5
--if original string is less than len 5, it will be padded
```

### Map letter of alphabet  to Count\(first letter of name  is the  letter\)

{% tabs %}
{% tab title="SQL" %}
```sql
select substr (mems.surname,1,1) as letter, count(*) as count 
    from cd.members mems
    group by letter
    order by letter          
```
{% endtab %}

{% tab title="output" %}
```
letter	count
B	5
C	2
D	1
F	2
G	2
```
{% endtab %}
{% endtabs %}

