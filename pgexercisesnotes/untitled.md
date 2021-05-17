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
IN takes any table with a single column
{% endhint %}



