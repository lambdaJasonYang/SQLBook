# Inner Join

## INNER JOIN

![](../.gitbook/assets/schema-horizontal.svg)

The SELECT also uses the aliases. We create a SQL JOIN statement in-&gt;out, from the FROM ..WHERE to SELECT.

```bash
#Step 1 Create the JOIN statement
FROM                        
    firstTable aliasA
    INNER JOIN 
    sndTable aliasB
WHERE
    aliasA.prop ...
    ... 
#Step 2 Create Add the Select statement
SELECT aliasA.prop as blah, aliasB.prop as bleh
FROM
    ...
```

```sql
select bks.starttime as start, facs.name as name
	from 
		cd.facilities facs
		inner join cd.bookings bks
			on facs.facid = bks.facid
	where 
		facs.name in ('Tennis Court 2','Tennis Court 1') and
		bks.starttime >= '2012-09-21' and
		bks.starttime < '2012-09-22'
order by bks.starttime; 
```

{% hint style="info" %}
 we need to link cd.bookings and cd.facilities, and constrain to specific day\(cd.bookings\) and facility\(cd.facilities\). 
{% endhint %}

Once you're strong enough, save the world:

{% code title="hello.sh" %}
```bash
# Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```
{% endcode %}



