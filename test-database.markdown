---
layout: page
title: test database
permalink: /test-database/
---

Here is the database (may)
database [database]

<table>
  {% for row in site.data.database_may %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>


[database]: https://docs.google.com/spreadsheets/d/e/2PACX-1vTNfntt8VumPBAZNOWf1iwf3f1SAtgQUwWXuNT8GJuUAuco7EuYJruaLXGk54S4W2mwryrTma9clfb7/pubhtml
