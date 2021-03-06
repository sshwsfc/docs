---
layout: api-command 
language: JavaScript
permalink: api/javascript/has_fields/
command: hasFields
io:
    -   - sequence
        - stream
    -   - array
        - array
    -   - singleSelection
        - boolean
    -   - object
        - boolean
related_commands:
    '() (getField)': get_field/
    withFields: with_fields/
---

# Command syntax #

{% apibody %}
sequence.hasFields([selector1, selector2...]) &rarr; stream
array.hasFields([selector1, selector2...]) &rarr; array
singleSelection.hasFields([selector1, selector2...]) &rarr; boolean
object.hasFields([selector1, selector2...]) &rarr; boolean
{% endapibody %}

# Description #

Test if an object has all of the specified fields. An object has a field if it has the
specified key and that key maps to a non-null value. For instance, the object
`{'a':1,'b':2,'c':null}` has the fields `a` and `b`.

__Example:__ Which heroes are married?

```js
r.table('marvel').hasFields('spouse')
```


__Example:__ Test if a single object has a field.

```js
r.table('marvel').get("IronMan").hasFields('spouse')
```


__Example:__ You can also test if nested fields exist to get only spouses with powers of their own.

```js
r.table('marvel').hasFields({'spouse' : {'powers' : true}})
```


__Example:__ The nested syntax can quickly get verbose so there's a shorthand.

```js
r.table('marvel').hasFields({'spouse' : 'powers'})
```

