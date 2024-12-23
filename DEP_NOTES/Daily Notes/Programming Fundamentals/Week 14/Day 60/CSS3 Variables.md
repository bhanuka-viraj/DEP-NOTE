
|                                            |                                                                                                                                                                                                       |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| When Variables were <br>introduced for CSS | In CSS3                                                                                                                                                                                               |
| `:root` what this mean<br>                 | To catch the root element<br>`<html></html>`<br><br>This is used to declare the variables. this variables can <br>be used within the page.<br><br>this `:root` pseudo class is introduced in CSS3<br> |
| What is the syntax of <br>the variable     | identifier : value                                                                                                                                                                                    |
| what is the difference<br>between this two | `:root{color:red}` and `div{colr:blue}`<br><br>the variables under root works with the all elements <br>in the page. Variables under div works only with elements under div<br><br>github link ->     |
```CSS
<style>

:root{
--my-color:blue;
--theme-color:yellow;
}
h1{
color:var(--my-color);
}
</style>
```

