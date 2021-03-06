---
layout: api-command 
language: Python
permalink: api/python/close/
command: close 
related_commands:
    connect: connect/
    use: use/
    repl: repl/
    reconnect: reconnect/
---

# Command syntax #

{% apibody %}
conn.close()
{% endapibody %}

# Description #

Close an open connection. Closing a connection cancels all outstanding requests and frees
the memory associated with the open requests.

__Example:__ Close an open connection.

```py
conn.close()
```


