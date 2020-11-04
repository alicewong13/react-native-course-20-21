1. Variable types and operations you can do on variables

2. Function arguments (maybe something like an equation solver)

In our last lesson, we saw how JavaScript can bring a website to life- that is, add functionality to a static site.

We also looked at how we can harness the power of JavaScript in our own websites by writing a function to change our site at the click of a button (remember buttonClick()?).

Today, we&#39;re going to dive a little deeper into JavaScript so that we can get to writing more complex functions.

To write fancy functions, we need to take a closer look at variables.

Here&#39;s an example from the previous lesson:

let name = &quot;Bob&quot;

let age = 25

…..[will expand here]

The main primitive data types in JavaScript are

Number

Boolean

String

(there are also other data types including undefined, BigInt, and, Symbol, but we won&#39;t go over these today.

you can read more about them here if you&#39;re interested: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data\_structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures))

JavaScript is a dynamically typed language, which means that every variable type is determined at runtime, when you actually go to use it.

This means you don&#39;t have to worry about specifying the type of each variable you use. That&#39;s really convenient, but it&#39;s still important to know what kind of variable you have, since each data type has its own quirks.

For example, as you might expect, you can add, subtract, multiply, and divide numbers. But what about strings, or a boolean?

[do you think you can add strings?]

String Concatenation

So it turns out that you can actually add strings. What happens when you add them? One string is appended to the other, exactly as they are.

for example:

let firstName = Joe;

let lastName = Bruin;

console.log(firstName + &quot; &quot; + lastName); // Joe Bruin

\*\* console.log() is a function that writes a message to the debugging console

![](RackMultipart20201104-4-g0ysye_html_a63e2d43d9297fbd.png)

Now booleans. Can you add AND subtract booleans? What about multiply and divide?

Math with Booleans

Turns out you can do all of those things! When you use a boolean value in JavaScript, true = 1 and false = 0. If you do arithmetic with booleans, booleans just evaluate to numbers. Like in math, you can&#39;t divide by false since that would be dividing by zero, but you can add/subtract/multiply/divide to your heart&#39;s content otherwise.

Adding strings and numbers? Strings and booleans?

Although you can mix numbers and booleans in JavaScript, you can&#39;t mix numbers and strings.

Let&#39;s put this all together with an example combining JavaScript with some HTML.

![](RackMultipart20201104-4-g0ysye_html_237499165a11f2b9.gif)

Last week, we discussed functions in JavaScript as a way to simplify our code. This allows us to code a specific set of tasks and then be able to do that set of tasks again without typing it all out again!

Last week we made a function that counted how many times a button was pressed, and displayed that number on our web page! We then passed that function to the onclick attribute of a button, which is really just a fancy way of saying that we told the button to run our function when it is clicked!

Let&#39;s take a look at the function we made last week:

function buttonClick() {

click = click + 1;

document.getElementByID(&#39;num&#39;).innerHTML = click

}

Right now, to demonstrate the parts of a function, we will dissect each line, to hopefully make functions seem a little simpler.

The first line is called the function declaration, where we tell our page that we want to define a function called buttonClick. The second and third line are just lines of code that represent the function body--basically just doing what we want our function to do.

The two parentheses after buttonClick () are where we store what are called function parameters or function arguments!

Since there is nothing between the parentheses in this line, it means that we are requiring no parameters for our function. Put more simply, the user doesn&#39;t need to put in any data for our function to work, it&#39;ll just do the same work each time.

However, many times we will need the user to give us input data. We are only able to use this data if it passed to our function through the use of parameters. Parameters are basically just variables that we give our function that it can work with to influence the action of the function.

For example, if we want to create a function that adds two numbers and prints the result to the console log and returns the result as well, it might look something like this:

function addTwoNumbers(number1, number2) {

sum = number1 + number2;

console.log(sum);

return sum;

}

So, let me take you guys through what this all means. The first line is the function declaration, where we define a function called addTwoNumbers. Since there are words between the parentheses, we know that there are function arguments. The function arguments we have are called number1 and number2.

We add together the variables number1 and number2, then print it to the console log in the body of our function, then return the sum, and then close the function with the ending curly brace.

So, basically what we&#39;ve done is we&#39;ve allowed the user to pass us information through the use of function arguments or parameters, specifically two variables called number1 and number2. You can think of these variables as just nicknames of the variables that will be passed to them when the function is called.

This is how we could call the function in our code:

num1 = 5;

num2 = 3;

addTwoNumbers(num1, num2); // this will result in &#39;8&#39; being printed to the console log and 8 as the return value of the function

One thing we notice here is that our variables themselves are not called number1 and number2! In fact, they can be called anything they want!

When we wrote our function, number1 and number2 were just names for the parameters that we used in our function body, so you can think of them as just nicknames for the real variable names that we will know later when the function is called!

This is because we can never predict what variables will be given to us! When using the function, the variables we pass to our function can be called anything, and our function will still deal with them appropriately.

Example for kids:

\&lt;!DOCTYPE html\&gt;

\&lt;html\&gt;

\&lt;head\&gt;

\&lt;metacharset=&quot;utf-8&quot;\&gt;

\&lt;metaname=&quot;viewport&quot;content=&quot;width=device-width&quot;\&gt;

\&lt;title\&gt;repl.it\&lt;/title\&gt;

\&lt;linkhref=&quot;style.css&quot;rel=&quot;stylesheet&quot;type=&quot;text/css&quot;/\&gt;

\&lt;/head\&gt;

\&lt;body\&gt;

\&lt;scriptsrc=&quot;script.js&quot;\&gt;\&lt;/script\&gt;

\&lt;script\&gt;

function addTwoNumbers(number1, number2) {

sum = number1 + number2;

console.log(sum);

return sum;

}

function helperFunction() {

num1 = Number(fnum.value);

num2 = Number(snum.value);

result.value = addTwoNumbers(num1, num2);

}

\&lt;/script\&gt;

\&lt;h1\&gt; Adder \&lt;/h1\&gt;

\&lt;labelfor=&quot;fnum&quot;\&gt;First number:\&lt;/label\&gt;

\&lt;inputtype=&quot;number&quot;id=&quot;fnum&quot;name=&quot;fnum&quot;\&gt;\&lt;br\&gt;\&lt;br\&gt;

\&lt;labelfor=&quot;snum&quot;\&gt;Second number:\&lt;/label\&gt;

\&lt;inputtype=&quot;number&quot;id=&quot;snum&quot;name=&quot;snum&quot;\&gt;\&lt;br\&gt;\&lt;br\&gt;

\&lt;buttononclick=&quot;helperFunction()&quot;\&gt;Calculate \&lt;/button\&gt;\&lt;br\&gt;\&lt;br\&gt;

\&lt;labelfor=&quot;result&quot;\&gt;Result:\&lt;/label\&gt;

\&lt;inputtype=&quot;number&quot;id=&quot;result&quot;name=&quot;result&quot;\&gt;

\&lt;/body\&gt;

\&lt;/html\&gt;

\&lt;!DOCTYPE html\&gt; \&lt;html\&gt; \&lt;head\&gt; \&lt;meta charset=&quot;utf-8&quot;\&gt; \&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width&quot;\&gt; \&lt;title\&gt;repl.it\&lt;/title\&gt; \&lt;link href=&quot;style.css&quot; rel=&quot;stylesheet&quot; type=&quot;text/css&quot; /\&gt; \&lt;/head\&gt; \&lt;body\&gt; \&lt;script src=&quot;script.js&quot;\&gt;\&lt;/script\&gt; \&lt;script\&gt; function addTwoNumbers(number1, number2) { sum = number1 + number2; console.log(sum); return sum; } function helperFunction() { num1 = Number(fnum.value); num2 = Number(snum.value); result.value = addTwoNumbers(num1, num2); } \&lt;/script\&gt; \&lt;h1\&gt; Adder \&lt;/h1\&gt; \&lt;label for=&quot;fnum&quot;\&gt;First number:\&lt;/label\&gt; \&lt;input type=&quot;number&quot; id=&quot;fnum&quot; name=&quot;fnum&quot;\&gt;\&lt;br\&gt;\&lt;br\&gt; \&lt;label for=&quot;snum&quot;\&gt;Second number:\&lt;/label\&gt; \&lt;input type=&quot;number&quot; id=&quot;snum&quot; name=&quot;snum&quot;\&gt;\&lt;br\&gt;\&lt;br\&gt; \&lt;button onclick=&quot;helperFunction()&quot;\&gt;Calculate \&lt;/button\&gt;\&lt;br\&gt;\&lt;br\&gt; \&lt;label for=&quot;result&quot;\&gt;Result:\&lt;/label\&gt; \&lt;input type=&quot;number&quot; id=&quot;result&quot; name=&quot;result&quot;\&gt; \&lt;/body\&gt; \&lt;/html\&gt;