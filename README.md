### Multiple Choice Question Template for Anki

This repository contains simple JavaScript, HTML and CSS code for front and back cards, designed specifically for styling multiple choice questions in Anki.


![tuis](https://github.com/muctebanesiri/anki-multiple-choise-question-template/assets/108553374/30477205-23b8-408c-a60e-52e3509bd7f1)


### Instructions for Creating Cards

https://youtu.be/xgRmOmN_gjE

If you wish to use these templates to create cards in the future, follow these steps:

1. **Manage Note Types**
   - Go to `Manage Note Types`.
   - Click `Add`.
   - Select `Add: Basic`.
   - Change the name to "MCQ".

2. **Define Fields**
   - Select the newly created "MCQ" note type and navigate to "Fields".
   - Add the required fields for your multiple choice question.
   - Save the changes.

3. **Set Up Cards**
   - With the "MCQ" note type selected, go to "Cards".
   - Paste the provided code for the Front Template and Back Template accordingly.
### Codes

1. Front Template
```javascript
     <div style='font-family:"Arial";font-size:20px'>{{edit:Question}}</div><br>
<form>
<div class="container" id="A"><input type="radio" name="radAnswer" id="A"><div class="option">{{edit:option_1}}</div></div>
<div class="container" id="B"><input type="radio" name="radAnswer" id="B"><div class="option">{{edit:option_2}}</div></div>
<div class="container" id="C"><input type="radio" name="radAnswer" id="C"><div class="option">{{option_3}}</div></div>
<div class="container" id="D"><input type="radio" name="radAnswer" id="D"><div class="option">{{option_4}}</div></div>
<div class="container" id="E"><input type="radio" name="radAnswer" id="E"><div class="option"></div></div>
<div class="container" id="F"><input type="radio" name="radAnswer" id="F"><div class="option"></div></div>
<div class="container" id="G"><input type="radio" name="radAnswer" id="G"><div class="option"></div></div>
<div class="container" id="container8"><input type="radio" name="radAnswer"><div class="option"></div></div>
</form>
<script>
/*<![CDATA[*/
if (void 0 === window.Persistence) {
var e = "github.com/SimonLammer/anki-persistence/",
t = "_default";
if (window.Persistence_sessionStorage = function () {
var a = !1;
try {
"object" == typeof window.sessionStorage && (a = !0, this.clear = function () {
for (var d = 0; d < sessionStorage.length; d++) {
var c = sessionStorage.key(d);
0 == c.indexOf(e) && (sessionStorage.removeItem(c), d--)
}
}, this.setItem = function (c, d) {
void 0 == d && (d = c, c = t), sessionStorage.setItem(e + c, JSON.stringify(d))
}, this.getItem = function (c) {
return void 0 == c && (c = t), JSON.parse(sessionStorage.getItem(e + c))
}, this.removeItem = function (c) {
void 0 == c && (c = t), sessionStorage.removeItem(e + c)
}, this.getAllKeys = function () {
for (var d = [], c = Object.keys(sessionStorage), g = 0; g < c.length; g++) {
var f = c[g];
0 == f.indexOf(e) && d.push(f.substring(e.length, f.length))
}
return d.sort()
})
} catch (b) {}
this.isAvailable = function () {
return a
}
}, window.Persistence_windowKey = function (a) {
var c = window[a],
b = !1;
"object" == typeof c && (b = !0, this.clear = function () {
c[e] = {}
}, this.setItem = function (d, f) {
void 0 == f && (f = d, d = t), c[e][d] = f
}, this.getItem = function (d) {
return void 0 == d && (d = t), void 0 == c[e][d] ? null : c[e][d]
}, this.removeItem = function (d) {
void 0 == d && (d = t), delete c[e][d]
}, this.getAllKeys = function () {
return Object.keys(c[e])
}, void 0 == c[e] && this.clear()), this.isAvailable = function () {
return b
}
}, window.Persistence = new Persistence_sessionStorage, !Persistence.isAvailable()) {
var i = window.location.toString().indexOf("title"),
n = window.location.toString().indexOf("main", i);
i > 0 && n > 0 && n - i < 10 && (window.Persistence = new Persistence_windowKey("qt"))
}
}
var X = "{{Ans}}";
if (X == X.toLowerCase()) {
var X = X.toUpperCase()
}
var Y = Number(X);
var k = "value";
var accepted = "undifiend";
var choosed = "undifiend";
var radio = document.getElementsByTagName("input");
var option = document.getElementsByClassName("option");
Persistence.setItem(choosed);
var container = document.getElementsByClassName("container");
for (i = 0; i < container.length; i++) {
if (container[i].innerText.length === 0) {
container[i].innerHTML = ""
}
}
if (isNaN(Y)) {
for (i = 1; i < X.length + 1; i++) {
console.log("first method");
eval("var " + k + i + " = '" + X.slice(i - 1, i) + "';")
}
} else {
for (i = 1; i < X.length + 1; i++) {
console.log("second method");
eval("var " + k + i + " = '" + X.slice(i - 1, i) + "';");
var converted = String.fromCharCode(Number(eval(k + i)) + 64)
}
}

function storeAnswer() {
var a = this.id;
Persistence.setItem(a);
console.log(a)
}

function flipToBack() {
if (typeof pycmd !== "undefined") {
pycmd("ans")
} else {
if (typeof study !== "undefined") {
study.drawAnswer()
} else {
if (typeof AnkiDroidJS !== "undefined") {
showAnswer()
} else {
if (window.anki && window.sendMessage2) {
window.sendMessage2("ankitap", "midCenter")
}
}
}
}
}
for (i = 0; i < container.length; i++) {
container[i].addEventListener("click", storeAnswer);
container[i].addEventListener("click", flipToBack);
};
/*]]>*/
</script>
```
2. Back Template
```javascript
<div style='font-family:"Arial";font-size:20px'>{{edit:Question}}</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="A"><div class="circle"></div><div class="option">{{edit:option_1}}</div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer">{{NotesOp1}}</div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="B"><div class="circle"></div><div class="option">{{edit:option_2}}</div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer">{{NotesOp2}}</div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="C"><div class="circle"></div><div class="option">{{option_3}}</div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer">{{NotesOp3}}</div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="D"><div class="circle"></div><div class="option">{{option_4}}</div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer">{{NotesOp4}}</div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="G"><div class="avatar"></div><div class="answer"></div></div>
</div>

<div style='font-family:"Arial";font-size:25px'>
<div class="container" id="E"><div class="circle"></div><div class="option"></div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer"></div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="F"><div class="circle"></div><div class="option"></div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer"></div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="G"><div class="circle"></div><div class="option"></div></div>
</div>

<div style='font-family:"Arial";font-size:14px'>
<div class="container" id="H"><div class="avatar"></div><div class="answer"></div></div>
</div>

<div style='font-family:"Arial";font-size:20px'>
<div class="container" id="container8"><div class="circle"></div><div class="option"></div></div>
</div>

<script>

/*<![CDATA[*/
if (void 0 === window.Persistence) {
var e = "github.com/SimonLammer/anki-persistence/",
t = "_default";
if (window.Persistence_sessionStorage = function () {
var a = !1;
try {
"object" == typeof window.sessionStorage && (a = !0, this.clear = function () {
for (var d = 0; d < sessionStorage.length; d++) {
var c = sessionStorage.key(d);
0 == c.indexOf(e) && (sessionStorage.removeItem(c), d--);
}
}, this.setItem = function (c, d) {
void 0 == d && (d = c, c = t), sessionStorage.setItem(e + c, JSON.stringify(d));
}, this.getItem = function (c) {
return void 0 == c && (c = t), JSON.parse(sessionStorage.getItem(e + c));
}, this.removeItem = function (c) {
void 0 == c && (c = t), sessionStorage.removeItem(e + c);
}, this.getAllKeys = function () {
for (var d = [], c = Object.keys(sessionStorage), g = 0; g < c.length; g++) {
var f = c[g];
0 == f.indexOf(e) && d.push(f.substring(e.length, f.length));
}
return d.sort();
});
} catch (b) {}
this.isAvailable = function () {
return a;
};
}, window.Persistence_windowKey = function (a) {
var c = window[a],
b = !1;
"object" == typeof c && (b = !0, this.clear = function () {
c[e] = {};
}, this.setItem = function (d, f) {
void 0 == f && (f = d, d = t), c[e][d] = f;
}, this.getItem = function (d) {
return void 0 == d && (d = t), void 0 == c[e][d] ? null : c[e][d];
}, this.removeItem = function (d) {
void 0 == d && (d = t), delete c[e][d];
}, this.getAllKeys = function () {
return Object.keys(c[e]);
}, void 0 == c[e] && this.clear()), this.isAvailable = function () {
return b;
};
}, window.Persistence = new Persistence_sessionStorage, Persistence.isAvailable() || (window.Persistence = new Persistence_windowKey("py")), !Persistence.isAvailable()) {
var i = window.location.toString().indexOf("title"),
n = window.location.toString().indexOf("main", i);
i > 0 && n > 0 && n - i < 10 && (window.Persistence = new Persistence_windowKey("qt"));
}
}
var number = Persistence.getItem();
console.log(number);
var X = "{{Ans}}";
if (X == X.toLowerCase()) {
var X = X.toUpperCase();
}
var Y = Number(X);
var k = "value";
var accepted = "undifend";
var circle = document.getElementsByClassName("circle");
var option = document.getElementsByClassName("option");
var container = document.getElementsByClassName("container");
for (i = 0; i < container.length; i++) {
if (container[i].innerText.length === 0) {
container[i].innerHTML = "";
}
}
if (number.length < 4) {
document.getElementById(number).childNodes[0].setAttribute("class", "circleF circle");
}
if (isNaN(Y)) {
for (i = 1; i < X.length + 1; i++) {
console.log("first method");
eval("var " + k + i + " = '" + X.slice(i - 1, i) + "';");
document.getElementById(eval(k + i)).childNodes[1].classList.add("true");
document.getElementById(eval(k + i)).childNodes[0].setAttribute("class", "circleT circle");
}
} else {
for (i = 1; i < X.length + 1; i++) {
console.log("second method");
eval("var " + k + i + " = '" + X.slice(i - 1, i) + "';");
var converted = String.fromCharCode(Number(eval(k + i)) + 64);
document.getElementById(converted).childNodes[1].classList.add("true");
document.getElementById(converted).childNodes[0].setAttribute("class", "circleT circle");
}
}
Persistence.setItem("undefined");
/*]]>*/

</script>
```
3. styling
```CSS
.container:hover {
cursor:pointer
}

.card {
font-family:arial;
font-size:20px;
text-align:left;
color:#000;
background-color:#fff
}

.container {
display:flex;
padding:5px
}

.option {
display:block;
border-radius:8px;
padding:2px 5px
}

.circle {
position:relative;
width:20px;
height:20px;
border-radius:50%;
left:-5px;
display:inline-block;
flex-shrink:0;
top:5px
}

.circleF {
background:#ff595a
}

.circleT {
background:#059862
}

.circleF::before {
content:"✖";
position:relative;
font-size:14px;
left:4.5px;
bottom:3px
}

.circleT::before {
content:"✔";
position:relative;
font-size:14px;
left:4.5px;
bottom:3px
}

.true {
font-size:25px;
font-weight:700;
background:#c7f1dc
}

input[type="radio"] {
width:20px;
height:20px;
border:.15em solid currentColor;
position:relative;
top:2px;
display:inline-block;
flex-shrink:0
}
```
### Code Credits

The original code was provided/modified by u/12yardsfootball. I've made some modifications to ensure proper right-to-left (RTL) support for Persian, along with some other minor adjustments.

### Usage

Feel free to use, modify, and customize these templates for your own Anki flashcard decks. If you have any questions or suggestions for improvements, don't hesitate to reach out.
