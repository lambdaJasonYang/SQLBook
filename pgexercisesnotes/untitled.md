# Untitled

## Getting Super Powers

![3 tables in cd database](../.gitbook/assets/schema-horizontal.svg)

Becoming a super hero is a fairly straight forward process:

{% code title="Search for any word CONTAINING Tennis" %}
```sql
select *
	from cd.facilities 
	where 
		name like '%Tennis%';      
```
{% endcode %}

{% hint style="info" %}
 %    character matching any string    
 \_     matching any single character
{% endhint %}

### IN

{% tabs %}
{% tab title="Ex 1" %}
{% code title="IN operator as alternative to \"where facid = 1 or facid =5\"" %}
```sql
select *
	from cd.facilities 
	where 
		facid in (1,5);
```
{% endcode %}
{% endtab %}

{% tab title="Ex 2" %}
```
select * 
	from cd.facilities
	where
		facid in (
			select facid from cd.facilities
			);
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
\(1,5\) behaves like a single col table.  
IN can be applied to any table with a single column shown in Ex2
{% endhint %}

### CASE WHEN .. THEN .. ELSE .. END

{% tabs %}
{% tab title="SQL" %}
```sql
select name, 
	case when (monthlymaintenance > 100) then
		'expensive'
	else
		'cheap'
	end as cost
	from cd.facilities;     
```
{% endtab %}

{% tab title="output" %}
```
name	          cost
Tennis Court 1	expensive
Tennis Court 2	expensive
Badminton Court	cheap
```
{% endtab %}
{% endtabs %}

### Subquery and Scalar table

Scalar table is a 1 row 1 column table   
Scalar table can be substituted with value constants

```sql
select firstname, surname, joindate
	from cd.members
	where joindate = 
		(select max(joindate) 
			from cd.members);   
```

