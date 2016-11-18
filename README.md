GETTING STARTED
===============

This guide will be focused on development in Windows, for OSX or Linux tutorials, please send me a request.
We will start by installing NodeJS as a server and Atom as the editor, but Notepad++ or Sublime Text are both valid options.

INSTALL ATOM
------------
* Download the [Windows installer](https://github.com/atom/atom/releases/download/v1.12.4/AtomSetup.msi).
* Run the installer (the .msi file you downloaded in the previous step.)
* Follow the prompts in the installer (Accept the license agreement, click the NEXT button a bunch of times and accept the default installation settings).

###PACKAGES
Atom is very extendable with themes and plugins, for now we'll be using [script](https://atom.io/packages/script) to avoid using the terminal, but theres plenty of packages to explore and I highly recommend to do it once we get used to the enviroment. To install packages, press the buttons ctrl+shift+p (all at the same time) and a search menu will appear. In the search menu type the keywords *Install packages* and click *Settings View:Install Packages and Themes*.

> We will search for script-runner and hit install

> ![Package list](https://zenagiwa.files.wordpress.com/2015/02/installview.jpg?w=700)

INSTALL NODEJS
---------------
* Download the [Windows installer](https://nodejs.org/dist/v7.1.0/node-v7.1.0-x64.msi).
* Run the installer (the .msi file you downloaded in the previous step.)
* Follow the prompts in the installer (Accept the license agreement, click the NEXT button a bunch of times and accept the default installation settings).
* Restart your computer. You won’t be able to run NodeJS until you restart your computer.

CREATE FIRST PROJECT
--------------------

###The project
We will create an empty folder, in *My Documents* for example. Open it and right click inside it, select *Open in Atom* or open atom and select *File->Open...* and select that folder.

To do a simple test that everything is ok, create a file with ctrl+n or in File->new and paste the code on the right of this text, save it with ctrl+s

``` javascript
console.log("This code runs!");
```

###Running it
In JavaScript the interface of the user is the HTML file, so for now let's use the console log as the way to show the data. If you installed the script package, run this file with shift+ctrl+b. A windows will appear from the bottom with the text that we put inside the *console.log*.

OUR FIRST FUNCTION AND VARIABLE
-------------------------------

###Functions
**Functions** are a resource to **organize and avoid duplication** of code, one of the basic tools with conditions and loops. In JavaScript functions have this shape, they have a name '*add*' and some input data '*x, y*'. Every action in code must end in **;** a common thing to let the machine know when we are finished doing an action.

``` javascript
function add(x, y) {
  return x+y;
};

console.log(add(3,4));
```

###Variables
**Variables** are a way to **store the data** for later reuse, in most of the languages there's a need to define what kind of data is going to be stored, a number, characters, etc. But in JavaScript this need doesn't exist, making it more flexible although harder to find errors when we don't know where exactly is the problem.

``` javascript
var res = 7;
console.log(res);
```

###Together
Let's create our function, call it by it's name, store the result in a variable and print the result. To concatenate an string with a variable or another string just use the *+* Symbol.

``` javascript
function add(x, y) {
  return x+y;
};

var res = add(3,4)
console.log("The result is "+res);
```

###Reusability
In order to improve code maintenance and reusability is always a good idea to store on the top of the code the *static* numbers, that way if later we need to change something we won't need to read all the code trying to find where this numbers are stored.

``` javascript
//Here we store the numbers we'll use
var number1 = 3.1418;
var number2 = 3;

//Lets use a multiline comment
/*
  @function add This function will return the addition of two passed numbers
  @param {number} x The first number to add
  @param {number} y The second number to add
  @returns The addition of the parameters
*/
function add(x, y) {
  return x+y;
};

//Call the function and store the result
var res = add(number1, number2);
//Print the result
console.log("The result is "+res);
```

Another good idea is to put comments on the code, specially before each function or a really complicated operation, this doesn't have any repercussions on the result of the running code, but really helps other people (and years-later-you) in reading and understanding the code.

Notice the [format](http://usejsdoc.org/tags-returns.html) of the multiline code to describe the function, it uses this [format](http://usejsdoc.org/tags-param.html) to make it understandable by automatic documentation generators like [JSDoc](http://usejsdoc.org/index.html), commonly used in big projects to avoid wasting time in keeping the documentation updated. Not really necessary at this point, but a good habit to earn from the start.
