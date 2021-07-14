---
layout: page
title: test database
permalink: /test-database/
---

Here is the database (may)
database [database]
<html>
<head>
    <style type="text/css">
        h3 span {
            font-size: 36px;
        }

        .button-default{
          float: right;
          border: white;
          padding: 5px;
          margin: 5px;
        }

        .search-box{
          width: 50%;
          margin: auto;
          float: left;
          padding: 10px;
          margin-bottom: 20px;
        }

        .filter-box{
          width: 20%;
          float: right;
          padding: 10px;
          margin-bottom: 20px;
        }

    </style>
</head>

<body class="mt32">
  <div>
        <h3>
        <input type="text" id="seInput" class="search-box" onkeyup="myFunction(category.value)" placeholder="Search">
        </h3>

        <select name="category" id="category" class="filter-box">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>

        <button type="button" class = "button-default"
        onclick="input('û')">û</button>
        <button type="button" class = "button-default"
        onclick="input('ü')">ü</button>
        <button type="button" class = "button-default"
        onclick="input('ş')">ş</button>
        <button type="button" class = "button-default"
        onclick="input('ö')">ö</button>
        <button type="button" class = "button-default"
        onclick="input('î')">î</button>
        <button type="button" class = "button-default"
        onclick="input('İ')">İ</button>
        <button type="button" class = "button-default"
        onclick="input('ı')">ı</button>  
        <button type="button" class = "button-default"
        onclick="input('ğ')">ğ</button>
        <button type="button" class = "button-default"
        onclick="input('ç')">ç</button>
        <button type="button" class = "button-default"
        onclick="input('â')">â</button>
        </div>

        <script>
          function input(e){
            var seInput = document.getElementById("seInput");
            seInput.value = seInput.value + e;
            document.getElementById("seInput").focus();
          }
        </script>
<div>
  <table id="myTable" class="table table-striped mt32 customers-list">
<!--<table>-->
  {% for row in site.data.database_may %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
    <tbody>
      {% tablerow pair in row %}
        {{ pair[1] }}
      {% endtablerow %}
    </tbody>
  {% endfor %}

  </table>
</div>

<!-- source : https://www.w3schools.com/howto/tryit.asp?filename=tryhow_js_filter_table -->
<script>
function myFunction(val) {
  var input, filter, table, tr, td, i, txtValue;
  input = document.getElementById("seInput");
  filter = input.value.toUpperCase();
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");
  for (i = 0; i < tr.length; i++) {
    td = tr[i].getElementsByTagName("td")[val];
    if (td) {
      txtValue = td.textContent || td.innerText;
      if (txtValue.toUpperCase().indexOf(filter) > -1) {
        tr[i].style.display = "";
      } else {
        tr[i].style.display = "none";
      }
    }       
  }
}
</script>



 </body>
 </html>


[database]: https://docs.google.com/spreadsheets/d/e/2PACX-1vTNfntt8VumPBAZNOWf1iwf3f1SAtgQUwWXuNT8GJuUAuco7EuYJruaLXGk54S4W2mwryrTma9clfb7/pubhtml
