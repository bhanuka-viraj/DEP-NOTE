
|                                             |                                                                                            |
| ------------------------------------------- | ------------------------------------------------------------------------------------------ |
| what is the use<br>of `inline-block`        | To give the element to the inline layout and allow to change <br>the properties like block |
| What are the <br>methods use for<br>columns | 1. Using  `inline-blocks`<br>2. Using floats<br>3. Using tables                            |
|                                             |                                                                                            |
==1.Using Blocks ->==
![[Pasted image 20240515074657.png]]
can't keep white space between 2 div declarations , if kept, it will be added as space

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Columns</title>

</head>

<body>
    <h1>Columns</h1>
    Go <a href="index.html">Home</a>

    <h2>1. Method</h2>
    <style>
        #container-1 {
            background-color: yellow;
            height: 200px;
            /* overflow: hidden; */

            :first-child {
                background-color: lightpink;
            }

            :nth-child(2){
                background-color: green;
            }

            :last-child{
                background-color: lightblue;
            }
        }

        .col {
            height: 100%;
            /* get width as parent's width / 3 */
            width: calc(100% / 3);
            display: inline-block;
        }
    </style>
    <div id="container-1">
        <div class="col">COLUMN 1</div><div class="col">
            COLUMN 2</div><div class="col">
                COLUMN 3</div>
    </div>
</body>

</html>
```


==2.Using Floats ->==
![[Pasted image 20240515074914.png]]

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Columns</title>

</head>

<body>
    <h1>Columns</h1>
    Go <a href="index.html">Home</a>

    <h2>1. Method</h2>
    <style>
        #container-1 {
            background-color: yellow;
            height: 200px;
            /* overflow: hidden; */

            :first-child {
                background-color: lightpink;
            }

            :nth-child(2){
                background-color: green;
            }

            :last-child{
                background-color: lightblue;
            }
        }

        .col {
            height: 100%;
            /* get width as parent's width / 3 */
            width: calc(100% / 3);
            display: inline-block;
        }
    </style>
    <div id="container-1">
        <div class="col">COLUMN 1</div><div class="col">
            COLUMN 2</div><div class="col">
                COLUMN 3</div>
    </div>


    <style>
        #container-2{
            background-color: yellow;
            height: 200px;
            :first-child{
                float: left;
                background-color: lightpink;
            }
            :nth-child(2){
                background-color: green;
                float: left;
            }
            :last-child{
                background-color: lightblue;
                float: left;
            }
            .col2{
                width: calc(100% / 3);
                height: 100%;
            }
            .clearfix{ /*clear the float*/
                clear: both;
            }
        }
    </style>
    <h2>2. Method</h2>
    <div id="container-2">
        <div class="col2">COLUMN 1</div>
        <div class="col2">COLUMN 2</div>
        <div class="col2">COLUMN 3</div>
    </div>
    <div class="clearfix"></div> <!--clear the float-->
    
</body>

</html>
```

==3.Using Table==

![[Pasted image 20240515075239.png]]

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Columns</title>

</head>

<body>
    <h1>Columns</h1>
    Go <a href="index.html">Home</a>

    <h2>1. Method ( Via inline blocks )</h2>
    <style>
        #container-1 {
            background-color: yellow;
            height: 200px;
            /* overflow: hidden; */

            :first-child {
                background-color: lightpink;
            }

            :nth-child(2) {
                background-color: green;
            }

            :last-child {
                background-color: lightblue;
            }
        }

        .col {
            height: 100%;
            /* get width as parent's width / 3 */
            width: calc(100% / 3);
            display: inline-block;
        }
    </style>
    <div id="container-1">
        <div class="col">COLUMN 1</div><div class="col">
            COLUMN 2</div><div class="col">
            COLUMN 3</div>
    </div>


    <style>
        #container-2 {
            background-color: yellow;
            height: 200px;

            :first-child {
                float: left;
                background-color: lightpink;
            }

            :nth-child(2) {
                background-color: green;
                float: left;
            }

            :last-child {
                background-color: lightblue;
                float: left;
            }

            .col2 {
                width: calc(100% / 3);
                height: 100%;
            }

            .clearfix {
                /*clear the float*/
                clear: both;
            }
        }
    </style>
    <h2>2. Method ( Via Floats )</h2>
    <div id="container-2">
        <div class="col2">COLUMN 1</div>
        <div class="col2">COLUMN 2</div>
        <div class="col2">COLUMN 3</div>
    </div>
    <div class="clearfix"></div> <!--clear the float-->

    <style>
        #container-3 {
            width: 100%;
        }

        .col3 {
            height: 200px;
            vertical-align:top;
        }

        tr>.col3:first-child {
            background-color: lightpink;
        }

        tr>.col3:nth-child(2) {
            background-color: lightgreen;
        }

        tr>.col3:last-child {
            background-color: lightblue;
        }
    </style>
    <h2>3. Method ( via Table )</h2>
    <table id="container-3">
        <tr>
            <td class="col3">Column 1</td>
            <td class="col3">Column 2</td>
            <td class="col3">Column 3</td>
        </tr>
    </table>

</body>

</html>
```
