<!DOCTYPE html>
<html>
<head>
	<title> MusemEditor </title>
	<style>
div {text-align: center;}
</style>
<link rel="icon" type="image/x-icon" href="/idrk.png">
</head>
<body style="background-color:rgb(54, 54, 54);">
	<h1 style="text-align: center; color:rgb(94, 209, 134); font-family: 'Gill sans MT';"> MusemEditor </h1>
	<div class="codeeditor">
		<textarea id="html-area" rows="12" cols="50" placeholder="HTML area" style="background-color:rgb(54, 54, 54); resize: none;"></textarea>
		<textarea id="css-area" rows="12" cols="50" placeholder="CSS area" style="background-color:rgb(54, 54, 54); resize: none;"></textarea>
		<textarea id="script-area" rows="12" cols="50" placeholder="Javascript area" style="background-color:rgb(54, 54, 54); resize: none;"></textarea>		
	</div>
	<br>
	<div>
		<!-- <button class="buttonruncode" id="run" onclick="run()" style="background-color: green;color: white; padding: 15px 32px;   text-align: center;   font-size: 16px;   margin: 4px 2px;   cursor: pointer;  width: 250px;">Run </button> -->
	</div><br>
	<div class="outputeditor">	
	<iframe id="output-frame" width="1178" height="450" ></iframe>
	</div>
	<script type="text/javascript">
		function run(){
			let htmlCode=document.querySelector(".codeeditor #html-area").value;
			let cssCode="<style>"+document.querySelector(".codeeditor #css-area").value+"</style>";
			let scriptCode=document.querySelector(".codeeditor #script-area").value;
			let output =document.querySelector(".outputeditor #output-frame");
			output.contentDocument.body.innerHTML=htmlCode+cssCode;
			output.contentWindow.eval(scriptCode);
		}
		document.querySelector(".codeeditor #html-area").addEventListener("keyup",run);
		document.querySelector(".codeeditor #css-area").addEventListener("keyup",run);
		document.querySelector(".codeeditor #script-area").addEventListener("keyup",run);
	</script>
</body>
</html>
