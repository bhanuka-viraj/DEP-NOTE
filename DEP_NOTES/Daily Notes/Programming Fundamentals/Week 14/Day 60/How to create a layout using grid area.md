
```HTML
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Document</title>
<style>
#container {
display: grid;
grid-template-areas:
"logo bread bread bread"
"nav slider slider slider"
"nav text text picture"
"nav widget footer footer"
"copyright widget footer footer";
grid-template-rows: 50px 100px 100px 100px 50px;

}

#container div,nav,footer{
height: 100%;
width: 100%;
background-color: cadetblue;
border: 1px solid black;
display: flex;
justify-content: center;
align-items: center;
font-size: 2rem;
}

#logo {
grid-area: logo;

}

#breadCrumb{
grid-area: bread;
}

#nav{
grid-area: nav;

}

#slider{

grid-area: slider;
}
#text{

grid-area: text;
}

#picture{

grid-area: picture;
}

#copyright{
grid-area: copyright;
}
#widget{

grid-area: widget;

}
#footer{

grid-area: footer;

}

</style>

</head>  

<body>

Go <a href="gridlayout.html">Back</a>
<div id="container">
<div id="logo">LOGO</div>
<div id="breadCrumb">BREAD-CRUMB</div>
<nav id="nav">NAV</nav>
<div id="slider">SLIDER</div>
<div id="text">TEXT</div>
<div id="picture">IMAGE</div>
<div id="copyright">COPYRIGHT</div>
<div id="widget">WIDGET</div>
<footer id="footer">FOOTER</footer>
</div>
</body>
</html>
```

![[Pasted image 20240515183632.png]]

