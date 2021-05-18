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



