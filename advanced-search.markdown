---
layout: page
permalink: /advanced-search/
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
        hr{

          margin-bottom: 10px;
          margin-top: 10px;
        }
        .sizeInput{
          padding: 10px;
          margin-bottom: 30px;
          width: 7%;
          margin-right: 10px;
          margin-left: 10px;
        }

    </style>
</head>
<body class="mt32">
  <h3>Search By Category</h3>

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
    </div>
    <script>
      function input(e){
        var seInput = document.getElementById("seInput");
        seInput.value = seInput.value + e;
        document.getElementById("seInput").focus();
      }

    </script>

    <div>

      <div>
        <h3>
          <input type="text" id="seInput" class="search-box" placeholder="Search">
        </h3>

        <select name="category" id="category" class="filter-box">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>
      </div>

      <div>
        <h3>
          <input type="text" id="seInput2" class="search-box" style="display:none;" placeholder="Search">
        </h3>
        <select name="category" id="category2" class="filter-box" style="display:none;">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>
      </div>

      <div>
        <h3>
          <input type="text" id="seInput3" class="search-box" style="display:none;"  placeholder="Search">
        </h3>
        <select name="category" id="category3" class="filter-box" style="display:none;">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>
      </div>

      <div>
        <h3>
          <input type="text" id="seInput4" class="search-box" style="display:none;"  placeholder="Search">
        </h3>
        <select name="category" id="category4" class="filter-box" style="display:none;">
          <option value="1">Author</option>
          <option value="3">Title</option>
        </select>
      </div>

    </div>

  <!--  <button type="button" id="more" class = "button-default"
        onclick="moreSearch()">+</button> -->
    <input type="image" style="height:30px; width:30px;"
    src="{{site.baseurl}}/images/more.png" id="moreButton" onclick="moreSearch()">

    <script>
    x = 1
      function moreSearch(){
        x+= 1
        if (x == 2){
          document.getElementById("seInput2").style.display = "block";
          document.getElementById("category2").style.display = "block";
        }
        else if (x == 3){
          document.getElementById("seInput3").style.display = "block";
          document.getElementById("category3").style.display = "block";
        }
        else if (x == 4){
          document.getElementById("seInput4").style.display = "block";
          document.getElementById("category4").style.display = "block";
          document.getElementById("moreButton").style.display = "none";
        }

      }
    </script>

    <hr>
    <div>
      <h3>Size</h3>
      <select name="chooseSize" id="chooseSize" class="filter-box" style="float:left; margin-right:20px;">
        <option value="False">Smaller</option>
        <option value="True">Greater</option>
      </select>
      <span>than</span>
      <input type="text" id="sizingChoice" class="sizeInput" style="float:left;" placeholder="15" style="display:inline-block">
      <span>cm by</span>
      <input type="text" id="sizingChoice" class="sizeInput" style="display:inline-block" placeholder="20">
      <span>cm</span>
    </div>
    <hr>
    <div>
      <h3>Date</h3>
      <select name="chooseDate" id="chooseDate" class="filter-box" style="float:left; margin-right:20px;" onchange="checkInBetween()">
        <option value="before">Before</option>
        <option value="after">After</option>
        <option value="between">Between</option>
      </select>
      <span>H. </span><input type="text" id="dateChoice" class="sizeInput" style="float:left;" placeholder="1200" style="display:inline-block">
      <p id="toH" style="display:none;"> to H. </p>
      <input type="text" id="dateChoice2" class="sizeInput" style="display:none" placeholder="1300">
      <script>
        function checkInBetween(){
          if (document.getElementById("chooseDate").value == "between"){
            document.getElementById("toH").style.display = "inline-block";
            document.getElementById("dateChoice2").style.display = "inline-block";
          }
          else{
            document.getElementById("toH").style.display = "none";
            document.getElementById("dateChoice2").style.display = "none";
          }
        }
      </script>
    </div>
    <hr>
    <div>
      <h3>Language</h3>
      <input type="checkbox" id="turkishLang" name="turkishLang" value="T" style="display:inline-block;">
      <label for="turkishLang" style="display:inline-block; margin-right: 30px;"> Turkish </label>
      <input type="checkbox" id="arabicLang" name="arabicLang" value="A" style="display:inline-block;">
      <label for="arabicLang" style="display:inline-block;"> Arabic</label>
    </div>
    <hr>
    <button style="display:inline-block; border-radius:15px; color:white; background-color: DodgerBlue; padding: 10px; margin-top:10px;" onclick="advancedSearch2()">Submit Search</button>
    <hr>

<table id="myTable" class="table table-striped mt32 customers-list" style="display: none;">
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

<p id="demo">hi</p>
<!-- source : https://www.w3schools.com/howto/tryit.asp?filename=tryhow_js_filter_table -->
 <script>
  function advancedSearch2(){
     document.getElementById("demo").innerHTML = "Hello World";
     document.getElementById("myTable").style.display = "none";
  }
  function advancedSearch(){
    document.getElementById("myTable").style.display = "block";

    var cat1, query1, cat2, query2, cat3, query3, cat4, query4, table, tr, td, i, txtValue
    table = document.getElementById("myTable");
    tr = table.getElementsByTagName("tr");
    for (i = 0; i < tr.length; i++){
      fitsCriteria = True;
      if (document.getElementById("category").value){
        document.getElementById("myTable").style.display = "block";
        query1 = document.getElementById("seInput").value.toUpperCase;
        td = tr[i].getElementsByTagName("td")[document.getElementById("category").value];
        if (td){
          txtValue = td.textContent || td.innerText;
          if (txtValue.toUpperCase().indexOf(query1) == -1) {
            fitsCriteria = False;
            continue;
          }
        }
        else{
          fitsCriteria = False;
          continue;
        }
      }
      if ( document.getElementById("category2").value){
        query2 = document.getElementById("seInput").value.toUpperCase();

      }
      if (fitsCriteria){
        tr[i].style.display = "";
      }
      else{
        tr[i].style.display = "none";
      }
    }


  }
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
 function searchMultiple(val, val2) {
   var input, input2, filter, filter2, table, tr, td, i, txtValue;
   input = document.getElementById("seInput").value.toUpperCase();
   input2 = document.getElementById("seInput2").value.toUpperCase();
   table = document.getElementById("myTable");
   tr = table.getElementsByTagName("tr");
   for (i = 0; i < tr.length; i++) {
     td = tr[i].getElementsByTagName("td")[val];
     td2 = tr[i].getElementsByTagName("td")[val2];
     if (td || td2) {
       txtValue = td.textContent || td.innerText;
       txtValue2 = td2.textContent || td2.innerText;
       if (txtValue.toUpperCase().indexOf(input) > -1 && txtValue2.toUpperCase().indexOf(input2) > -1) {
         tr[i].style.display = "";
       } else {
         tr[i].style.display = "none";
       }
     }       
   }
 }
function isTrue(query, td){
  input = document.getElementById(query).value.toUpperCase();
  txtValue = td.textContent || td.innerText;
  if (txtValue.toUpperCase().indexOf(input) > -1 ){
    return True;
  }
  else{
    return False;
  }
}

function updateArray(){
  let queries = queries.push
}
function search(){
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");
  for (i = 0; i < tr.length; i++){

     for (#query in list){
<!-- try two lists, one of value and one of search query-->
      td = tr[i].getElementsByTagName("td")[val];
      if (td){
        if ( #function is true){
           tr[i].style.display = "";
         } else {
           tr[i].style.display = "none";
         }
       }

     }
   }
 }


 </script>
 </body>


[database]: https://docs.google.com/spreadsheets/d/e/2PACX-1vTNfntt8VumPBAZNOWf1iwf3f1SAtgQUwWXuNT8GJuUAuco7EuYJruaLXGk54S4W2mwryrTma9clfb7/pubhtml
