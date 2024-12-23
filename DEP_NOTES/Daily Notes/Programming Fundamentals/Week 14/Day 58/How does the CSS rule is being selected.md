1.The rule with the highest specificity value is selected

2.If there are some  CSS rules with the same specificity value, then consider the interpret order
 
3.If there is a inline styling it get most priority from all others CSS rule. Specificity is not valid for the inline styling.

4.If there is a CSS rule with `!important` it get the highest priority. 

5.If there are more than one CSS rule with `!important` , the CSS rule with the more specificity value is selected. 

6.If there are more than one CSS rules with `!important` and they have the same specificity value then CSS rule is selected  based on the interpret order.

7.If there is a inline styling with a `!important` then it get most priority




