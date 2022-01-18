---
layout: page
title: test database
permalink: /test-database/
---

<!--
Problems with double search:
- can only do 2
- only searches on keyup of second box
- only turkish letters for first box
- still doesn't search after turkish letter (regular)
-->
<head>
    <style type="text/css">
        h3 span {
            font-size: 36px;
        }
        .button-default{
          height: 30px;
          width: 30px;
          float: center;
          border: white;
          border-radius: 8px;
          margin: 3px;
          margin-bottom: 20px;
        }
        .search-box{
          width: 70%;
          float: left;
          padding: 10px;
          margin-bottom: 30px;
        }

        .filter-box{
          width: 25%;
          float: right;
          padding: 10px;
          margin-bottom: 30px;
          background-color: WhiteSmoke;
        }

    </style>
</head>
<body class="mt32">

  <div>
    <button type="button" class = "button-default"
    onclick="input('â')">â</button>
    <button type="button" class = "button-default"
    onclick="input('ç')">ç</button>
    <button type="button" class = "button-default"
    onclick="input('ğ')">ğ</button>
    <button type="button" class = "button-default"
    onclick="input('ı')">ı</button>  
    <button type="button" class = "button-default"
    onclick="input('İ')">İ</button>
    <button type="button" class = "button-default"
    onclick="input('î')">î</button>
    <button type="button" class = "button-default"
    onclick="input('ö')">ö</button>
    <button type="button" class = "button-default"
    onclick="input('ş')">ş</button>
    <button type="button" class = "button-default"
    onclick="input('ü')">ü</button>
    <button type="button" class = "button-default"
    onclick="input('û')">û</button>


    <a href="{{site.baseurl}}/advanced-search" style="color:DimGrey; float:right; margin-top:10px; margin-bottom: 20px; font-size: 13px; text-decoration:underline;">Advanced Search</a>
    </div>

    <div>

      <div>
        <h3>
          <input type="text" id="seInput" class="search-box" onkeyup="searchFunc(category.value)" placeholder="Search">
        </h3>

        <select name="category" id="category" class="filter-box">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>
      </div>


    </div>

    <script>
      function input(e){
        var seInput = document.getElementById("seInput");
        seInput.value = seInput.value + e;
        document.getElementById("seInput").focus();
      }
    </script>

<table id="myTable" class="table table-striped mt32 customers-list">
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


<!-- source : https://www.w3schools.com/howto/tryit.asp?filename=tryhow_js_filter_table -->
 <script>
 function searchFunc(val) {
   var input, filter, table, tr, td, i, txtValue;
   input = document.getElementById("seInput").value.toUpperCase();
   table = document.getElementById("myTable");
   tr = table.getElementsByTagName("tr");
   for (i = 0; i < tr.length; i++) {
     td = tr[i].getElementsByTagName("td")[val];
     if (td) {
       txtValue = td.textContent || td.innerText;
       if (txtValue.toUpperCase().indexOf(input) > -1) {
         tr[i].style.display = "";
       } else {
         tr[i].style.display = "none";
       }
     }       
   }
 }


function search(){
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


[database]: https://docs.google.com/spreadsheets/d/e/2PACX-1vTNfntt8VumPBAZNOWf1iwf3f1SAtgQUwWXuNT8GJuUAuco7EuYJruaLXGk54S4W2mwryrTma9clfb7/pubhtml
