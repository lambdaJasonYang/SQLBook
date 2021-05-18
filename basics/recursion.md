# Recursion

## Getting Super Powers

Single column from 1 to 5

```sql
WITH RECURSIVE counter AS (
    SELECT 1 AS i
    UNION ALL
    SELECT i+1 FROM counter WHERE i < 5
    )    SELECT i FROM counter;
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

{% code title="hello.sh" %}
```bash
# Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```
{% endcode %}



