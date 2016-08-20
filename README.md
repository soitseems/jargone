<html>
<head>
<link rel="stylesheet" type="text/css"
          href="https://fonts.googleapis.com/css?family=Montserrat">
<style>
body {
    background-color: #fcf5eb;
    font-family: 'Montserrat', sans-serif;
}

h1 {
    
    font-size: 60px;    
    color: #32312f;
    text-align: center;
}

h2 {
    font-size: 35px;    
    color: grey;
    text-align: center;
}

p {
    text-align: center;    
    font-size: 20px;
    color: grey;
}

main1 div { 
  padding: 15px;
  width: 920px;
  max-width: 920px;
  height: auto;
  margin: 5px;
}

main2 div {
  padding: 30px;
  width: 250px;
  max-width: 450px;
  height: auto;
  margin: 5px;
}

.flex-center {
  display: flex;
  justify-content: center;
}

</style>
</head>

<header><title>JARGONE</title></header>
<br>
<h1>JARGONE</h1>
<p><textarea name="textarea" id="myTextarea" style="width:900px;height:150px;">Submit your text and I will analyze its jargon level</textarea></p>

<p><button onclick="jargone();countwords();passivevoice();jargon();wordlength()" >Analyze</button></p>

<br>

<body>

<main1 class="flex-center">
 
<div> 
 <h2 id="demo7"> Jargone score </h2>
   <script>
function jargone() {
    var str = document.getElementById("myTextarea").value;
    var a = str.length;
    var b = str.match(/[aeiouy]{1,2}/g);
    var c = str.split(" ").length;
    var d = str.split(". ").length;
    var regexp = /actionable|activate|actualize|aforementioned|agile|agility|analytics|augment|augmented|best practice|big data|big picture|bleeding edge|blue ocean|blue sky|burning platform|buy-in|clarity|conceptualize|core competencies|core competency|cutting edge|cutting-edge|data driven|database|data-driven|disrupt|disrupted|disruption|downsize|drill down|drilling down|drills down|ducks in a row|ecosystem|empower|entrepreneurial|framework|full service|full-service|functionality|game changer|gamechanger|game-changer|globalize|ideate|ideation|impact|incentivize|innovate|innovation|innovative|Integrate|integration|Internet of Things|IoT|learning|learnings|leverage|low-hanging fruit|metrics-based|moonshot|move the needle|moving parts|network|offline|operationalize|optimize|paradigm|passion|platform|price point|punt|push back|reach out|reaches out|reaching out|revert|robust|ROI|SaaS|scalable|solution|stated|sync|synergies|synergize|synergy|tailored|think outside the box|thinking outside the box|thinks outside the box|transform|transformation|value add|value-add|vertical|verticals|virtual|virtualization|virtualize|vision|whiteboard/g;   
    var x = (str.match(regexp));
    var y;
     if (x == undefined || x == "") {
        y = 0;
    } else {
       y = (str.match(regexp)).length;
    }
    var z = (110-1.25*(c/d)-1.25*((a-c+1)/c)-250*(y/c)).toFixed(0);    
    var greeting;
    if (str == null || str == "") {
        greeting = "Hey you need to write something!";
        } else if (z < 50) {
        greeting = ("Boo! Your JARGONe score is "+z).fontcolor("red");
        } else if ( z < 60) {
        greeting = ("Hmmm... Your JARGONe score is "+z).fontcolor("orange");          
        } else if ( z < 70) {
        greeting = ("Not Bad! Your JARGONe score is "+z).fontcolor("orange");    
        } else if ( z < 90) {
        greeting = ("Good! Your JARGONe score is "+z).fontcolor("green");
        } else if ( z < 100) {
        greeting = ("Hooray! Your JARGONe score is "+z).fontcolor("green");          
        } else {
        greeting = ("Perfect! Your JARGONe score is 100!").fontcolor("green");
        
     }  
    document.getElementById("demo7").innerHTML = greeting ;
}
</script>
</div>
</main1>

<script> 
function toggle() {
 var ele = document.getElementById("toggleText");
 var text = document.getElementById("displayText");
 if(ele.style.display == "block") {
      ele.style.display = "none";
  text.innerHTML = "Find out More";
   }
 else {
  ele.style.display = "block";
  text.innerHTML = "Too Much Information";
 }
} 
</script>
 
<p><a id="displayText" href="javascript:toggle();">Find out More</a> </p>
<div id="toggleText" style="display: none;">

<main2 class="flex-center">
 
<div>
<p><b>Jargon</b></p>   
<p id="demo3">  </p>
   <script>
function jargon() {
    var greeting;
    var str = document.getElementById("myTextarea").value;
    var regexp = /actionable|activate|actualize|aforementioned|agile|agility|analytics|augment|augmented|best practice|big data|big picture|bleeding edge|blue ocean|blue sky|burning platform|buy-in|clarity|conceptualize|core competencies|core competency|cutting edge|cutting-edge|data driven|database|data-driven|disrupt|disrupted|disruption|downsize|drill down|drilling down|drills down|ducks in a row|ecosystem|empower|entrepreneurial|framework|full service|full-service|functionality|game changer|gamechanger|game-changer|globalize|ideate|ideation|impact|incentivize|innovate|innovation|innovative|Integrate|integration|Internet of Things|IoT|learning|learnings|leverage|low-hanging fruit|metrics-based|moonshot|move the needle|moving parts|network|offline|operationalize|optimize|paradigm|passion|platform|price point|punt|push back|reach out|reaches out|reaching out|revert|robust|ROI|SaaS|scalable|solution|stated|sync|synergies|synergize|synergy|tailored|think outside the box|thinking outside the box|thinks outside the box|transform|transformation|value add|value-add|vertical|verticals|virtual|virtualization|virtualize|vision|whiteboard/g;   
    var k = str.match(regexp);
    var m;
    if (k == undefined || k == "") {
        m = 0;
    } else {
        m = k.length;
    }
    var n = str.split(" ").length;    
    if (str == null || str == "") {
        text = "Hey you need to write something!";
    } else if (k == null) {
        text = "You didn't use jargon. Well done!";
    } else {
        text = 100*(m/n).toFixed(2) + "% of the text is jargon.</br> These are the offending words: " + k.join(", ");    }
    document.getElementById("demo3").innerHTML = text;
}
</script>
</div>
  
<div>
<p><b> Sentence Length</b></p>      
<p id="demo1"> </p>
   <script>
function countwords() {
    var greeting;
    var str = document.getElementById("myTextarea").value;    
    var k = str.split(" ").length;
    var p = str.split(". ").length
    var q = k/p	    
    if (str == null || str == "") {
        greeting = "Hey you need to write something!";
    } else {
        greeting = q.toFixed(0) +" words per sentence, on average.</br> (Less than 14 is good.) ";
    }
    document.getElementById("demo1").innerHTML = greeting;
}
</script>
</div>

<div>
<p><b> Word Length</b></p>      
<p id="demo2">  </p>
   <script>
function wordlength() {
var text;    
var str = document.getElementById("myTextarea").value;
    var a = str.length;
    var c = str.split(" ").length;
    if (str == null || str == "") {
        text = "Hey you need to write something!";
    } else {
        text = ((a-c+1)/c).toFixed(0)+" letters per word, </br> on average.</br> (Less than 8 is good.)";    
    }
    document.getElementById("demo2").innerHTML = text ;
}
</script>
</div>

<div>
<p><b> Clarity</b></p>      
<p id="demo5">  </p>
   <script>
function passivevoice() {
    var greeting;
    var str = document.getElementById("myTextarea").value;
    var regexp = /ed by|en by/g;    
    var k = str.match(regexp);
     
    if (str == null || str == "") {
        text = "Hey you need to write something!";
    } else if (k == null) {
        text = "The passive voice was not used by you. Well done!";
    } else if (k.length == 1) {
        text = "You used the passive voice once.";
    } else {
        text = "You used the passive voice " + k.length + " times.";
    }
    document.getElementById("demo5").innerHTML = text;
}
</script>
</div>
</main2>
</body>
</html>
