# Functions and loops

#### *** If you are having trouble with your code some computers will allow you to inspect elements. Pop your website out into a full tab and then right click on an html element. Then select inspect. If you look at the tabs `elements` and `console` it will give you hints to fix any issues

This lesson uses `functions, loops, events, DOM Traversal, DOM Select, DOM Modification and variables`. The explanations in this lesson does not need to be elaborate as you have already learned most of the topics. Instead, this lesson will focus more on steps to completion and the development process. You are expected to write much of your own code or follow links to generic examples to help yourself.

You are given this table that only has one row. You want to add a button on the bottom. When this button is clicked another row will add to the bottom of the table.

## Task 1
1. Connect the HTML to the JS
2. Add a button under the table that says `Add Row` in the HTML
3. Get the button in JS (https://www.w3schools.com/jsref/met_document_getelementsbytagname.asp)
4. Attach an `onclick` listener to the button with an anonomous function (https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_onclick_dom)
5. Put an `alert("working")` inside your function to test that the button is working.
#

Verify that the button is actually getting the alert to pop before you move forward. Verify code with teacher if necessary.

## Task 2
Inside the function
1. Remove the alert
2. Declare a `const` called `tr` and assign it a `createElement` tr (https://www.w3schools.com/jsref/met_document_createelement.asp)
3. Declare a `const` called `td1` and assign it a `createElement` td
4. Set `td1` `innerText` to `New Data` (https://www.w3schools.com/Jsref/prop_node_innertext.asp)
5. Set `td1` `textAlign` to `center` (https://www.w3schools.com/jsref/prop_style_textalign.asp)
6. Set `td1` `onclick` equal to:
   ```javascript
     () => {
      td.style.backgroundColor = "#" + Math.floor(Math.random()*16777215).toString(16)
    }
    ```
7. `append` `td1` to `tr` (https://www.w3schools.com/jsref/met_node_appendchild.asp)
8. Declare a `const` `tbody` and assign the element `tbody` to it. Move this to line 1
9. `append` `tr` to `tbody`
#

Verify that the function actually adds a row with a single cell. Verify that when you click this cell the color changes. Do not continue until it is functioning properly. Verify code with teacher if necessary.

You should clearly notice that to complete the row you need to create `td2, td3, td4`. This means that you need to repeat Task 2 steps 3-7 three more times and then do steps 8-9. The `same code` four times... If you were to do that then your code would no longer be `DRY`. What you need to do is to move steps 3-7 into a function

## Task 3
1. Declare a `const` `createData` and assign it an anonomous function
2. Cut and Paste Task 2 steps 3-6 into the new function
3. Make the function return `td1` (https://www.w3schools.com/jsref/jsref_return.asp)
4. call the function inside `tr.appendChild(call here)`. This should be found inside the button.onclick function
5. Repeat `step 4` three more times and then run `tbody.appendChild(tr)`
#

Verify that you get an entire new row with 4 td's each time you click the button. Verify code with teacher if necessary.

Your code works nice but it is a bit limited. If you want one or two new tr's then it works great. But what if you wanted 20, 50, or even 100. This would mean that the user would have to do a bunch of clicks to get what they want. There is a better way. If you knew how many tr's the user wanted then you could build a bunch with one click.

## Task 4
1. Change the button HTML to say `Add Rows`
2. 1 line above the button add an input
3. 1 line above the input add
   ```javascript
    <div>How Many More Rows</div>
   ```
4. In JS after const `button` declare `const` `input` and assign the input element selected
#

Verify that you can see the new div and input next to the button

You have everything you need in your HTML. You just need to handle the logic. Currently, your button click will build 1 row. You want it to build `x` rows. Move all of your button logic into a function and then run that inside a for loop. You will run the for loop however many times the user put in the `input`

## Task 5
1. declare `const` `createRow` and assign an anonomous function to it.
2. put `amount` as a parameter to the above function
3. build a for loop that goes from `0` to `i < amount`
4. cut and paste the button logic that builds the row into the for loop

5. Your button logic should currently be an empty function. Add steps 6 and 7 to the button onclick function

6. declare `const` `amount` and assign the `parsed` `value` from the input (https://www.w3schools.com/jsref/jsref_parseint.asp)
7. call the `createRow` function and pass in the `amount` as the `argument`
#

Verify that your code works. The answer code has some embelshments that you don't have to create.

If you got to this point you did it with a whole bunch of guidance. It is now your turn to build something similar but simpler on your own.

## Task 6
1. add a div that says `How many lists do you want?`
2. add an input
3. add a button that says `Add Lists`

   The item that will be created will be an `ol` with three `li`
   ```html
  <ol>
    <li>Item</li>
    <li>Item</li>
    <li>Item</li>
  </ol>
  ```
  
#