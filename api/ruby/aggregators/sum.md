---
layout: api-command 
language: Ruby
permalink: api/ruby/sum/
command: sum
related_commands:
    group_by: group_by
    count: count/
    avg: avg/
---

# Command syntax #

{% apibody %}
r.sum(attr)
{% endapibody %}

# Description #

Compute the sum of the given field in the group.

__Example:__ How many enemies have been vanquished by heroes at each strength level?

```rb
r.table('marvel').group_by(:strength, r.sum(:enemies_vanquished)).run(conn)
```


