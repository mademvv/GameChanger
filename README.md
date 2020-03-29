# GameChanger:
<!DOCTYPE html>
<html>
<head>
<title>Interaction: Sortable</title>
<style>
ol
{

list-style-type:none;
width:170px;
height:480px;
}
li
{
height:30px;
width:150px;
border:1px solid black;
margin:2px;
font-size:20px;
text-align: center;
}
#raw li
{
background-color: pink;
}
#cooked li
{
background-color: yellow;
}
fieldset
{
float:left;
margin:30px;
width:200px;
height:500px;
border:5px solid black;
}

.specialFieldsetClass
{
float:left;
margin:30px;
width:500px;
height:500px;
border:5px solid black;
}
.tabs-nav {
  list-style: none;
  margin: 0;
  padding: 0;
}
.tabs-nav .tab-active a {
  background: skyblue;
  font-size: 13px;
  border-width: 1px;
  border-bottom-color: white;
  border-top-color: darkorange;
  border-left-color: darkorange;
  border-right-color: darkorange;
}
.tabs-nav a {
  border-width: 1px 1px 1px 1px;
  border-style: solid;
  border-bottom-color: darkorange;
  border-right-color: #C9C9C9;
  background: #E6E6E6;
  color: #7A7A7A;
  display: block;
  font-size: 12px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  width: 150px;
}
.tabs-nav li {
  float: left;
  
}
.TabContainerClass {
  width: 465px;
  height: 450px;
  border: 1px solid darkorange;
  border-top: 10px;
  border-left-width:1px;
  border-right-width:1px;
  border-bottom-width:1px;
  border-height:500px;
  
  clear: both;
  
  background: white;
}
.YellowDivClass {
  position: absolute;
  background-color: yellow;
  width: 350px;
  height: 200px;
  margin: 30px 0px 0px 20px;
  z-index: 1;
}
</style>

<link href="jquery-ui.css" rel="stylesheet">
<script src="jquery.js"></script>
<script src="jquery-ui.js"></script>
<script>

$(document).ready(function(){
 $("#raw").sortable({connectWith:"#cooked"});
$("#cooked").sortable({connectWith:"#raw"});

$('.tabs-nav a').on('click', function(event) {
  event.preventDefault();

  $('.tab-active').removeClass('tab-active');
  $(this).parent().addClass('tab-active');
  $('.TabContainerClass > div').hide();
  $($(this).attr('href')).fadeIn(300)
});

$('.tabs-nav a:first').trigger('click'); // Default

});
function submit(){
var isInorder=[]
$("ol#cooked li").each(function(){isInorder.push($(this).text())});
alert(isInorder.join("\n"));

}
function submit1(){
var isInorder=[]
$("ol#cooked li").each(function(){isInorder.push($(this).text())});
alert(isInorder.join("\n"));

}
function submit2(){
var isInorder=[]
$("ol#cooked li").each(function(){isInorder.push($(this).text())});
alert(isInorder.join("\n"));

}


</script>

</head>
<body>
<fieldset id="left">
<legend><b>OCLE Letter Components</b></legend>
<ol id="raw">
<li id="mango">Mange</li>
<li id="carrot">Carrot</li>
</ol>
</fieldset>

<fieldset id="left">
<legend><b>Composition</b></legend>
<ol id="cooked">
<li id="brinjal">Brinjal</li>
<li id="tomato">Tomato</li>
</ol>
</fieldset>

<fieldset class="specialFieldsetClass">
<legend><b>Operations</b></legend>
<ul class="tabs-nav">
  <li class="tab-active"><a href="#YellowDiv" rel="nofollow">Generate Tempaltes</a> 
  
  </li>

  <li class=""><a href="#tab-2" rel="nofollow">Validate Template</a>
  </li>
  <li class=""><a href="#tab-3" rel="nofollow">Submit for Approval</a>
  </li>
  
</ul>


<div class="TabContainerClass">

  <div id="YellowDiv" class="YellowDivClass">
    <input type="submit" value="Generate Template" onclick="submit()"  ></br>
  </div>


  <div id="tab-2" style="display: none;">
    <p>This is TAB 2</p>
	<input type="submit" value="Validate Template" onclick="submit1()" ></br>
  </div>

  <div id="tab-3" style="display: none;">
  <input type="submit" value="Submit for Approval" onclick="submit2()" >
    <p>This is TAB 3.</p>
  </div>

  <div id="tab-4" style="display: none;">
    <p>This is TAB 4.</p>
  </div>

</div>
</fieldset>
</body>
</html>
