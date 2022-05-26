# c-pia_calculadora
<!DOCTYPE html>
<html>
<head>
    <title>Calculadora</title>
    <style type="text/css">
        
        body {
  font-family: Verdana, sans-serif;
  font-size: 0.8em;
  margin: 0px;
}

nav,
section,
article {
  margin: 5px;
  padding: 8px;
}

#content {
  text-align: center;
}

header,
footer {
  background-color: Red;
  color: green;
  padding: 5px;
  margin: 0;
}

h1, h2, p {
  text-align: center;
}

button {
  width: 60px;
  text-align: center;
  font-size: 35px;
  background-color: white;
  color: black;
  border: black solid 1px;
}

input {
  width: 250px;
  font-size: 30px;
  background-color: white;
  color: black;
  border: black solid 1px;
  text-align: right;
}

nav ul {
  margin: 0;
  padding: 0;
}

nav ul li {
  display: inline;
  margin: 5px;
}

    </style>
</head>
<body>
 <script type="text/javascript">
      function writeNumber(elementId) {
  var outputValueTo = document.getElementById('field1');

  if (outputValueTo.value == '0' || outputValueTo.value == 'Syntax error') {
    outputValueTo.value = elementId.textContent;
  } else {

    outputValueTo.value += elementId.textContent;
  }
  
  var history = document.getElementById('histo')
  var outputValueTo = document.getElementById('histo');

  if (outputValueTo.value == '0' || outputValueTo.value == 'Syntax error') {
    outputValueTo.value = elementId.textContent;
  } else {

    outputValueTo.value += elementId.textContent;
  }

  
}

function cleartxt() {
  document.getElementById('field1').value = '0';
  
}

function setOperator(elementId) {
  var outputValueTo = document.getElementById('field1');
  if (outputValueTo.value == '0' || outputValueTo.value == 'Syntax error') {
    outputValueTo.value = '0';
  } else {
    outputValueTo.value += elementId.textContent;
   

  }
  var history = document.getElementById('histo')
  var outputValueTo = document.getElementById('histo');
  if (outputValueTo.value == '0' || outputValueTo.value == 'Syntax error') {
    outputValueTo.value = '0';
  } else {
    outputValueTo.value += elementId.textContent;
   

  }
  
}


function calculate() {

  try {
   
    var field1txt = document.getElementById('field1');
    if (field1txt.value != '') {
      var calculateResult = eval(field1txt.value);
      field1txt.value = calculateResult;
    }
  } catch (err) {

    field1txt.value = 'Syntax error';
    
    
  }
  var history = document.getElementById('histo')
  var newParamentro = eval(field1txt.value)
  var dt=new Date();
  var hora=dt.toLocaleString();

  history.value = "Hora:" + hora + " - " + history.value + " = " + newParamentro + ",";
}

function removeLastNumber() {

  var field1txt = document.getElementById('field1');

  if (field1txt.value.length == 1 || field1txt.value == '0' || field1txt.value == 'Syntax error') {
    field1txt.value = '0';

  } else {
    field1txt.value = field1txt.value.substring(0, field1txt.value.length - 1);
  }
}
    </script>
<section>
  <article>
    <div id='content'>
      <div id='content-app'>
        <input type='text' id='field1' value="0">
        <br /><br />
        <button onclick='writeNumber(this)' id='n1'>1</button>
        <button onclick='writeNumber(this)' id='n2'>2</button>
        <button onclick='writeNumber(this)' id='n3'>3</button>
        <button onclick='setOperator(this)' id='sum'>+</button>
        <br /><br />
        <button onclick='writeNumber(this)' id='n4'>4</button>
        <button onclick='writeNumber(this)' id='n5'>5</button>
        <button onclick='writeNumber(this)' id='n6'>6</button>
        <button onclick='setOperator(this)' id='sustract'>-</button>
        <br /><br />
        <button onclick='writeNumber(this)' id='n7'>7</button>
        <button onclick='writeNumber(this)' id='n8'>8</button>
        <button onclick='writeNumber(this)' id='n9'>9</button>
        <button onclick='setOperator(this)' id='multi'>*</button>
        
        <br /><br />
        <button onclick='setDecimal(this,true)' id='dec'>.</button>
        <button onclick='writeNumber(this)' id='n0'>0</button>
        <button onclick='cleartxt()' id='C'>C</button>
        <button onclick='setOperator(this)' id='divide'>/</button>
        <br /><br />
        <button onclick='calculate()' id='calcular' style='width:190px'>=</button>
        <button onclick='removeLastNumber()' id='removeLast'>←</button>
        <div class="event-log">
          <h1>Histórico</h1>
          <br>
          <textarea readonly class="eventos" rows="16" cols="60" id="histo"></textarea>
        </div>
          
        </div>
      </div>
    </div>
    <br />
    <br /><br />
  </article>
</section>
</body>
</html>



js

unction tableCreate() {
  //body reference 
  var body = document.getElementsByTagName("body")[0];

  // create elements <table> and a <tbody>
  var tbl = document.createElement("table");
  var tblBody = document.createElement("tbody");

  // cells creation
  for (var j = 0; j <= 2; j++) {
    // table row creation
    var row = document.createElement("tr");

    for (var i = 0; i < 2; i++) {
      // create element <td> and text node 
      //Make text node the contents of <td> element
      // put <td> at end of the table row
      var cell = document.createElement("td");
      var cellText = document.createTextNode("cell is row " + j + ", column " + i);

      cell.appendChild(cellText);
      row.appendChild(cell);
    }

    //row added to end of table body
    tblBody.appendChild(row);
  }

  // append the <tbody> inside the <table>
  tbl.appendChild(tblBody);
  // put <table> in the <body>
  body.appendChild(tbl);
  // tbl border attribute to 
  tbl.setAttribute("border", "2");
}
