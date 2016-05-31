#Interview Prep

(Partially from https://github.com/h5bp/Front-end-Developer-Interview-Questions)

Go through all of the following questions and think about how you would respond to
each. You should be able to answer many of the questions from memory, but you may
have to research a few of them.

**Copy this md file to your homework folder and add a short answer under each item.**
You should try to be as concise as possible, and list any handy resources you used
to answer the question. This will be useful for studying for interviews after class.

## General Questions

* What did you learn yesterday/this week?



* What excites or interests you about coding?

  Having the ablity to create new things. 
  You can do a lot of stuff.
  The Eureka moment when you finally solve something
  There's lots of little puzzles and problem solving.
  You can turn your ideas into life
  It allows you to explore ideas
  There's lots of things to play with (images, movies, sound, text, numbers!!)

* What is a recent technical challenge you experienced and how did you solve it?



* What UI, Security, Performance, SEO, Maintainability or Technology considerations
do you make while building a web application or site?



* Talk about your preferred development environment.



* Which version control systems are you familiar with?



* Can you describe your workflow when you create a web page?

  First: plan everything out first
  make sure you understand the scope
  make sure you're got the proper tools and resources before you start!
  if you don't have plan then you're going to do things you don't need to do

  Write a simple HTML page (you need that)
  Add some minimal styling to make sure CSS works
  Then adding some JavaScript functionality (make sure clicking works, scripts are set up)

  getting a simple server running
  testing the communication route between the app and the server
    - make sure I can receive data from the server
    - make sure I can send data to the server

* If you have 5 different stylesheets, how would you best integrate them into the site?



* Can you describe the difference between progressive enhancement and graceful degradation?



* Describe how you would create a simple slideshow page, without any frameworks (HTML/CSS/JS only).

  use CSS animations for transitions using opacity to show and hide elements
  keep an array with all of the image URLs

  attach a click handler to the image so users can click on it and go to the next one
  also, we can set up an interval with JavaScript to automatically transition through the pictures

  make some divs with "< prev" and "next >" text
  attach click handlers to those divs to go backwards and forwards in the slideshow

* If you could master one technology this year, what would it be?



* Explain the importance of standards and standards bodies.




## HTML Questions

* What does a `doctype` do?
Tells the browser what kind of document the page is.
Browsers view lots of types of documents. This tag
let's them know how to treat it.

* What's the difference between HTML and XHTML?
XHTML follows the conventions of XML and is more strict.

* What are `data-` attributes good for?
It's an HTML element attribute that doesn't display visually
and allows data to be stored in the DOM on elements. Bootstrap
uses it.

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
localStorage persists when the browser is closed.
sessionStorage is reset when the browser is closed.
Cookies are older, they can't store as much information and they
can only store strings. Unlike localStorage and sessionStorage
cookies are actually sent to the server.


* Why is it generally a good idea to position CSS `<link>`s between `<head></head>`
and JS `<script>`s just before `</body>`? Do you know any exceptions?

This has to do the order things load in.
CSS styles are loaded before elements appear and are displayed
on the page. We put Javascript files at the end of the page so
everything on the page is loaded before things like click handlers
are set up. We can also use document.onload to detect when the
page loads and execute our javascript once everything is on the page.

If javascript executes before the DOM is loaded then some things like
attaching click handlers won't be properly set up.

The async defer attributes can also be applied to a script tag to
prevent the page blocking while it loads the scripts. The script
will defer execution until the page is loaded.


## CSS Questions

* What is the difference between classes and IDs in CSS?
Classes are for multiple elements. IDs are for single elements.
IDs must be unique.

* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
Normalizing preserves defaults while resetting completely removes
all styles.

* Describe Floats and how they work.
Float is a CSS property that allows us to pull items left and right.
Be careful with floats! Floating elements don't have a height.
Use the CSS 'clear: both' property to get things to appear below
floated elements properly.

* Describe z-index and how stacking context is formed.
Z-index defines how elements are "stacked" on the page.
An element with a higher z-index will appear on top of
an element with a lower  z-index.

* Have you ever used a grid system, and if so, what do you prefer?
Yes! We've seen Bootstrap and Foundation. Their grid systems
are similar and they're both fine.

* Have you used or implemented media queries or mobile specific layouts/CSS?
Yes. We've used @media min-width and max-width queries to set
breakpoints to have our page appear differently on different screens.

* How do you optimize your webpages for print?
Create a separate CSS file specifically designed for printing.
There's a media attribute: media="print"
Use high resolution pictures, at least 300 dpi.

* What are the advantages/disadvantages of using CSS preprocessors?
Preprocessors allow us to write fancier syntax and add logic
to our CSS.

Things we gain:
- variables
- nested query sytanx allows us to write less code

Things we hate:
- harder to debug! the compiled code can be hard to read.
- the compiled code isn't the code we wrote
- preprocessers add an extra step in our workflow
- it adds a learning overhead to the project
  everyone on the team may not know the framework
- when things go wrong it's harder to debug


* Describe what you like and dislike about the CSS preprocessors you have used.
- SASS (great!)
- LESS (it's fine)
- there's also HTML preprocessers YAML

* How would you implement a web design comp that uses non-standard fonts?
Use a font service like Google Fonts, or Font Family.
Include a link to their CSS.
You can specify a list of fonts and fall through them to backups
if certain one's aren't available.

* Explain how a browser determines what elements match a CSS selector.
Selectors refer to IDs, classes and tags. We can combine them to
refer to elements on the page. We can select elements inside of
elements.

* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
The box model refers to margin, border padding and content.
The display property allows us to set elements to be block elements,
inline-block elements or inline. This defines how elements sit next
to each other on a page.

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
Browsers can measure the width and height of elements in different
ways. Each browser interprets box sizing differently. Specifying
a specific box-sizing allows us to know how things are measured.

The border-box value will measure elements including their borders.
The content-box value will measure only the content, not the margin
or border.

Bootstrap sets the box-sizing in their grid system.

* List as many values for the display property that you can remember.
- block: elements take up the full width
- inline: elements like <span> can go next to each other
          they have the width of the content and the height
          of the line. Inline elements cannot have a specified
          height.
- inline-block: A break appears between elements.
- flex: 
- initial: 
- inherit:
- none: hides things from the page.
- table:
- grid:

* What's the difference between inline and inline-block?
inline-block can have a specified height.

* What's the difference between a relative, fixed, absolute and statically positioned element?
This defines how elements are positioned on the page.
fixed: things stay put, no matter if scrolling occurs.
       good for footers that are always always on the
       the bottom of the window, no matter if you scroll
       or not.

absolute: things stay put relative to the entire document
          good for footers that don't appear until you
          scroll to the botto of the page

relative: allows elements to be positioning relative to
          where they would appear normally.

* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?

* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
I would love it if Bootstrap didn't make all the things on my
page look gigantic.
They each have their own style. Perhaps one could be more universal.
It would be cool if a framework supported grids that weren't
based off the number 12.

* Have you played around with the new CSS Flexbox or Grid specs?

* Have you ever worked with retina graphics? If so, when and what techniques did you use?
Retina refers to displays with an extremely high pixel density.
The problem with high density displays is that images built for
low resolution screens will show up super tiny. One way to
deal with this is to have two sets of images. One set is
used for low-density displays, and another is used for high
density displays.

* Explain some of the pros and cons for CSS animations versus JavaScript animations.
Built in CSS animations are more efficient and use the graphics
hardware. The built in CSS animations may be limited. Javascript
allows us to build more custom animations.

## JS Questions

* Explain event delegation
* Explain how `this` works in JavaScript
The 'this' keyword is used in classes, and functions.
Each instance of a object or class will have a this property
where it's own data and properties are stored.

When we create a Point object we can refer to 
this.x
this.y
and different instances of the point can have their own
values. In this case `this` refers to the instance of
the Point.

* Explain how prototypal inheritance works

* Why is it called a Ternary expression, what does the word "Ternary" indicate?
Ternary implies "three."

var meal = isPhilly ? 'cheesesteak' : 'burger';

var meal;
if (isPhilly) {
	meal = 'cheesesteak'
} else {
	meal = 'burger'
}


* What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
Null is an empty value that we can set.
undefined

What is the value of:
var x;

If we just write `var x;` then the value of it is undefined.
The `null` value is something that is explicitly set.


* How would you go about checking for any of these states?

* What is a closure, and how/why would you use one?
A closure is a function that has scope that refers to
variables. We can use closures to save the scope of
variables and their values at a certain point in time.

Closures can be used to encapsulate a module of code.
They wrap up the scope and make it unavailable to code
that exists outside the closure.

for (var i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000 * i);
}

prints 10 10 10 10 10 10 10 10 10...

for (var i = 0; i < 10; i++) {
  setTimeout((function(i) {
    return function() {
      console.log(i);
    }
  })(i), 1000 * i);
}

* What's a typical use case for anonymous functions?
Anonymous functions are useful when creating closures,
for creating click handlers and writing code that
won't be invoked from many places.


* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?

function Person(){}
	defines a function called Person. It's
  not executed yet.

var person = Person()
	this is declaring a variable called `person`
	it will be equal to the return value of the `Person` function.

var person = new Person()
	Using the new keyword invokes Person with a constructor
	and `person` takes on the value of an instance of Person.

* What's the difference between var foo = function(){} and
function foo(){}?

var foo = function(){}
function foo(){}
	these are both function definitions.
	function foo(){} is callable from anywhere
		even if it is defined below where you're calling it

	var foo = function(){} is not created until that line
	  of code is executed. So this declaration isn't calleable
	  until after this line.

	JavaScript does two passes on a file.
	The first pass reads all the input of the file, and saves
	references to functions declared with function foo() {}.
	Some syntax errors will be caught during this pass like
	missing curly braces at the end of the file.

	The second pass actually executes the code. This pass
	will actually evaluate expressions like var foo = function(){}

(function (){})()
	this is an anonymous function that is invoked immediately.

* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* What's the difference between feature detection, feature inference, and using the User Agent string?
* Explain AJAX in as much detail as possible.
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?

* Explain "hoisting".
Javascript hoists variables declared with var
to the top of a function. Variables will be undefined
until their value is actually set. Variables with the
same name of a variable outside a function as inside
a function can interfere with each other surprisingly.

	var x = 2;
	var z = 3;
	(function() {
	  console.log("x:", x);
	  console.log("z:", z);

	  var x = 4;
	})()

	x: undefined
	z: 3

	var x = 2;
	var z = 3;
	(function() {
	  console.log("x:", x);
	  console.log("z:", z);

	  x = 4;
	})()

	x: 2
	z: 3


* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?

* What is the difference between `==` and `===`?
Triple equals is a more strict definition of equality.
Double equals is the evil cousin which will return bogus results.

Triple equals will check the two of the two operands.
Double equals performs type coersion. Double equals
considers the number zero and the string zero to be
equal. This may cause unexpected behavior.

0 === '0' returns false
0 == '0' returns true

Always prefer ===!

http://stackoverflow.com/questions/359494/does-it-matter-which-equals-operator-vs-i-use-in-javascript-comparisons

* Explain the same-origin policy with regards to JavaScript.
This is a security policy that prevents JavaScript from
accessing sites outside the current domain.

* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?

* What tools and techniques do you use debugging Javascript code?
The chrome developer tools provide a great debugger.
Console.log is always nice.
Breakpoints and the `debugger` keyword are excellent tools.

* What language constructions do you use for iterating over object properties and array items?
For loops, for in loops, .forEach, while loops, do while loops,
.map, .filter, .reduce functions.

for in loops are good for iterating over the properties in an
object and accessing their key.

for loops are good for arrays. For in loops with arrays may
include the `length` property and cause problems.

## Database Questions

* Design a database schema for Facebook, with at least 4 models, a complete set of
attributes for each model, a 1:M association, and a M:M association.

## Ruby/Rails
* What are ruby gems?

  It's a module you add in that can be used for additional functionality
  for example, you can have a gem that provides a library with functions for OAuth

  SASS is a great gem that allows us to preprocess our CSS
  there's tons of auth gems

  there's a great voting gem (acts-as-voteable)

  CarrierWave - uploads files, uploaded Resumes

* What is the difference between a symbol and a string?

  We use symbols in hash maps
  symbols all reference one single value
  there may be many instances of strings

  Ruby created symbols to save some space in memory when using hash maps
  Symbols are simpler, they don't have as many methods and other data attached to them as strings
  Strings take up more memory than symbols

  :dogcat

  s1 = "dogcat"
  s2 = "dogcat"

* What is the difference between a class method and an instance method?

  A class method exists once for all instances of a class
  an instance method acts on instances individually

* What is the difference between local variables, instance variables, and class variables?

  local variables are not associated with any classes. They're only associated with their own scope of
  what function their in.

  instance variables are attached to instances of classes.
  A Point class may have many instances of itself, each with their own X, Y instance variables
  with many different values.

  We could also create a class variable (num_points) which exists once per each class, no matter
  how many instances of the class exist. Each instance of the class can read the same value

* What is a range?

  

* In ruby, what does attr_accessor do?  

  class Point
    attr_accessor :x, :y

    def initialize(x, y)
      @x = x
      @y = y
    end
  end

* What is the purpose of environment files under the config folder in Rails? (development, test, production)



* What is the purpose of the application.rb file in Rails?



* How can you define a constant?



* What is the purpose of `yield`?

  We use the yield keyword when we create our layout template.
  The rest of our site will fill in wherever we put the yield keyword.

  You can also give names to the yield keyword to render different portions of
  the site.

  <body>

  <%- yield :nav %>

  <%- yield %>

  <body>

  ========================================

  form_for @new_user do |u|
    text_field u.usernme
    password_field u.password
  end

  def form_for(obj)
    puts "<form>"
    yield
    puts "</form>"
  end

* How do you store API keys when creating an app?

  we put them in a .env file 
  and don't share it!
  add it to the .gitignore

* How do I send parameters through a url?

  

* Explain MVC

 MVC stands for Model View Controller
 These are the three parts that make up all our front-end apps

 the Model sets up our database structure
 the Model is used to model/represent all the data in our application

 The View defines how things are actually displayed

 the Controller actually controls the flow of information back and
 forth between the front end and the back end

 The controller controls all interaction between the model and the view

* What is a `before_action`? When would you use it?



* What do controllers do in rails?

  In Ruby on Rails we have views that define pages in our app
  We have models that define how our data exists in the database and in the app

  In Rails the controllers they allow us to configure routes
  We can pair controllers with CRUD methods to control how our models are
  Created, Read, Updated and Destroyed

* What is ReSTful routing?

  Representational
  State
  Transfer

  Restful routing is a standard convention that serves as a guide
  for us to create our CRUD routes

  ReSTful routing relies on HTTP verbs (GET, PUT, POST, DELETE)
  to attach more meaning to a single url

  /people/tom
  POST - creates a person Tom              Create
  GET - gets info about the person Tom     Read
  PUT - updates info about the person Tom  Update
  DELETE - deletes the person Tom          Delete

* What is a polymorphic association?

  it's when you're dealing with one database table that want to use for many things
  for example, we can create a table called votes that votes on comments, as well as posts

* What are params?



* How do I make a migration to add a column in Rails?



* What is CSRF? How does Rails protect an app against this?

  Cross Site Request Forgery
  Ruby on Rails puts CSRF tokens into forms and checks to make sure the token exists
  whenever someone tries to submit data on a route that would update or give out information

* What's the difference between `User.find_by_id(1)` and `User.find(1)`?

  find_by_id(1) is guaranteed to return the user with id 1
  find(1) returns one user, but there's no guarantee who the user may be

  If you want to find a specific user you'll want to use find_by_id
  If you're in development using the rails console it's nice to be able to get
  any old one user quickly

  If the id of the use doesn't matter then the database can return us
  any old user much more faster quickly.

* What's are classes in Ruby? What are modules? And what's the difference?

  Modules are things like gems

  A module is a self-contained piece of code that you're able to
  export and import into other places.

  We created modules when we first started learning Ruby
  when we created the calculator and the guessing game.
  

## Testing Questions

* What are some advantages/disadvantages to testing your code?

  Disadvantages:
  - tedious
  - writing tests is not fun
  - you may fall into the trap of writing code that just passes tests,
    and it may not actually have the correct functionality
  - sometimes it's hard to write a test when the code you're trying to test
    has many many dependencies and is tightly coupled to other parts of
    the application.
    - how can you test someone scrolling down through a site and
      clicking a delete button in the middle of a long list?
    - how do you make sure that alerts are properly displayed on
      a page?

  Advantages:
  - you can be more sure that your application works
  - if you have a good test suite then you can run it whenever
    someone submits code, and they can know whether or not
    they're breakig the entire application when they submit
    new code
  - writing tests first allow you to expirement with how
    pieces of code will work in your application and
    tests can actually provide a great library of code
    providing examples of how things work

* What tools would you use to test your code's functionality?

    you can assign someone to manually test the site
    manual testing is expensive and tedious but it's absolutely necessary
    manual testing will expose certain problems with an application tha
    wouldn't have been caught (or would't have been able to be caught) otherwise

    in QA (quality assurance) testing testers create test plans to test different
    portions of an app. Someone is given a very loose set of instructions to
    follow.

    Eventually manual tests may be converted into automated tests.

    For example:
    - typing something wierd into a form kills the form
    - no one thought about that before
    - now we can script a test to make sure it doesn't happen again

    Unit tests: test small parts of code like calling a method and checking a return value with assert

    There are also great tools that allow us to script user interactions like
    - typing things into a form
    - clicking on buttons
    - navigating to pages

    PhantomJs, Selenium, Angular has it's own built in libraries
    the Mocha, Chai, Jasmine libraries all help write unit tests and assertions

    there's also Rspec in ruby

* What is the difference between a unit test and a functional/integration test?



* What is the purpose of a code style linting tool?

  A code linter is a program that checks given code for stylistic errors
  a linter is a nice tool to use to enforce consistent coding patterns throughout
  an application

  A linter can detect all sorts of things:
  - improper indentation
  - inconsistent snake_case vs camelCase
  - inconsistent single or double quote usage, ' vs "
  - non-matching brackets, quotes, curly braces
  - long lines. lines past 80 or 100 characters

  teams can configure linters to detect any stylistic convention they care about.

  code repositories can actually prevent code from being commited until they pass
  a linter.

* What is End-to-end (E2E) testing? How can it be implemented in frameworks like Angular and Rails?

  End to end testing refers to testing things all the from the client end to the server end
  Angular provides it's own end to end testing framework


## Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

## Fun Questions:

* What's a cool project that you've recently worked on?



* What are some things you like about the developer tools you use?



* Do you have any pet projects? What kind?



* How do you like your coffee?




