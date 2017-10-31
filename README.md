# CSCI 3340 - ~~Software~~ Startup Engineering I Lecture Notes

# Table of Contents

[TOC]



# Philosophy of the Course

The goal of this course is to bridge the gap between academic computer science and production software engineering. This course will view the problem of designing production software through the lens of creating software that people would actually pay money to use. 

This class is not a get-rich-quick scheme, a get-rich-slow scheme, or even about making money. This class is an exercise in designing modern software systems mixed with the entrepreneurial considerations of today's business landscape.

### Why learn business in a software engineering class?

I believe that programming is a skill that allows us to create with our fingertips. As programmers and computer scientists/engineers we wield so much power. We can create new industries, new technologies, and new forms of entertainment. The question is not can we create something, it is *should we create something*. By learning a little bit about business we might be able to more rigorously answer the question... *should we build this*? 

### Why HTML/CSS/Web Development?

Most current software startups provide or are some form of web service. Netflix, Amazon, iTunes, Dropbox, Facebook, etc. The web is an integral part of how we interact with modern software. Most apps or startups at minimum need to provide basic functions like authentication and billing. These functions generally interact with a *web server* to verify the person is indeed a paying customer.

For many software ideas, we can mockup a functional prototype in HTML/CSS *plus some other stuff* and have it work on all types of computers, phones, and tablets all in one go.

### What is the most important takeaway for this class?

The most important takeaway is for you to learn how to work in a modern software organization. This class will introduce you to the real-world tools used by startups. You will learn about development strategies, code sharing and collaboration strategies, deploying software, software testing, and documentation.




# Architecture of a Web Startup / Building an MVP

## Popular Software Business Models

* **SaaS - Software as a service.** You sell access to the software, not the software itself. Software is hosted and users access it via a thin client.
  * Examples: Dropbox, Slack
* Traditional - Software is distributed to the client. The client runs the program on their device.
  * Examples: Photoshop
* PaaS - Platform as a Service. You sell access to a platform that enables users to develop or build applications without the complexity of building your solution.
  * PaaS Examples: Heroku, Amazon Web Services
* **Platform Services** - A blend of SaaS and PaaS, generally access to software is sold in a way that allows users to develop other applications by interfacing with your software (API access)
  * API Examples: Watson, Twilio, Stripe, PayPal



This course focuses on SaaS and Platform Services.

## Architecture of Modern SaaS

* Frontend
  * The frontend is software that the client directly interacts with. Recieves and presents data that is delivered from the backend. Also sends data to the backend for processing. This can be HTML/CSS or an app.
* Backend
  * The backend is software that manages the business logic, sends data to the frontend for presentation, recieves information from frontend, processes data, loads and stores data from database.
* Infrastructure
  * Things like the database, web server, mail server, etc.

## Popular Frontend Technologies

* HTML/CSS
  * Can be used to display data.
  * Is static. Provides no support for dynamic data.
  * Cannot be programmed or scripted.
* HTML/CSS with Javascript
  * Javascript can be used to manipulate the HTML to do things like loop, if statements, variables, and more.
  * Can also be used to fetch data from a backend service
* User interfaces built in traditional applications and mobile applications
  * JavaFX/Swing/AWT
  * iOS Interface Builder

## Popular Javascript Frontend Frameworks

These are used in combination with HTML/CSS to make a webpage interactive and have data from external sources.

* AngularJS
* jQuery
* ReactJS
* EmberJS

## Popular Backend Languages

* PHP
* Javascript
* Python
* Ruby

## Popular Backend Frameworks

Frameworks do a lot of the heavy lifting and tend to have reusable code to quickly make web based software.

* PHP - Laravel, CakePHP, Wordpress
* Javascript - NodeJS, ExpressJS, SailsJS
* Python - Django, Flask
* Ruby - Rails, Sinatra

## Popular Databases

* MySQL (Relational)

* PosgresQL (Relational with some non-relational features)

* MongoDB (Non-relational)

  ​

# Lean Way to Build a Minimum Viable Product (MVP)

For most software startups, we will want to mockup a prototype or create a wireframe. 

We will:

* use HTML/CSS and Bootstrap to create a static mockup of our product

* leverage pre-built themes and UIKits

* Focus (not too much) on what the experience should be like and *feel* like

* Constant iteration based on our assumptions

  ​

# HTML/CSS

HTML (Hypertext Markup Language) is the language of the web. It structures a webpage and gives clues as to how to present the information. CSS (Cascading stylesheets) allow us to add style to that structure to better describe its presentation.

A basic html webpage [(View Here)](./website_examples/basic/index.html):

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>Title of the document</title>
	</head>

	<body>
		Content of the document......
	</body>

</html> 
```

## Basic HTML Tags

* Headline Tag - `<h1>Big Headline</h1>`
* Paragraph Tag - `<p>Paragraph Text Here</p>`
* Bold Text - `<strong>Bolded Text</strong>`
* Italic text - `<em>Italicized Text</em>`
* Links - `<a href="http://www.google.com">Click Here for Google</a>`

## Example HTML Webpage using the basic tags

[(View here)](./website_examples/basic_tags/neversleep.html)

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>NeverSleep</title>
	</head>

	<body>
		<h1>Introducing <em>NeverSleep</em></h1>
		<p>
		NeverSleep is the <strong>revolutionary breakthough</strong> that allows you to stay awake forever! NeverSleep works by sending small electrical shocks to your nervous system causing your body to experience pain!
		You will never sleep again!
		</p>
		<a href="http://www.google.com">Sign up for free trial</a>
	</body>

</html> 
```

## CSS

CSS allows you to style HTML elements of your choosing. In the above example, if we wanted to make the headline red with a yellow background we could do this in a stylesheet and add a line in the HTML to include our stylesheet:

​	*style.css*

```css
h1{
    background-color: yellow;
  	color: red;
}
```

​	*neversleep.html*

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>NeverSleep</title>
  		<link rel="stylesheet" href="style.css">
	</head>

	<body>
		...
	</body>

</html> 
```

Unfortunately, this would apply to all `<h1>` tags we would ever use. We can instead create a style and apply it to anything we want using a *CSS class*.  Notice in the CSS we prefix the class name with a dot. It is reusable and can be applied to many elements.

​	*style.css*

```css
.ugly{
    background-color: yellow;
  	color: red;
}
```

​	*neversleep.html*

```html
<!DOCTYPE html>
<html>
	<head>
		...
  		<link rel="stylesheet" href="style.css">
      	...
	</head>

	<body>
      <h1 class="ugly">Introducing <em>NeverSleep</em></h1>
	  ...
	</body>

</html> 
```



# Bootstrap

## What is Bootstrap

Bootstrap is a pre-designed mega stylesheet that allows you to build mobile-friendly websites and web applications without having to design a bunch of standard components. Many components like a grid, columns, buttons, fonts, etc all have pre-styled defaults that look pretty good.

## Adding Bootstrap to an HTML file

To include Bootstrap to an HTML file you simple add the stylesheet and the JS to the page.

CSS: 

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">
```

JS:

```html
<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.3/umd/popper.min.js" integrity="sha384-vFJXuSJphROIrBnz7yo7oB41mKfc8JzQZiCq4NCceLEaO4IHwicKwpJf9c9IpFgh" crossorigin="anonymous"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/js/bootstrap.min.js" integrity="sha384-alpBpkh1PFOepccYVYDB4do5UnbKysX5WZXm3XxPqe5iKTfUKjNkCk9SaVuEZflJ" crossorigin="anonymous"></script>
```



For example:

```html
<!DOCTYPE html>
<html>
	<head>
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">
	</head>

	<body>
      <h1 class="ugly">Introducing <em>NeverSleep</em></h1>
      <p>
        Paragraph of text!
      </p>
      
      <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
	  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.3/umd/popper.min.js" integrity="sha384-vFJXuSJphROIrBnz7yo7oB41mKfc8JzQZiCq4NCceLEaO4IHwicKwpJf9c9IpFgh" crossorigin="anonymous"></script>
	  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/js/bootstrap.min.js" integrity="sha384-alpBpkh1PFOepccYVYDB4do5UnbKysX5WZXm3XxPqe5iKTfUKjNkCk9SaVuEZflJ" crossorigin="anonymous"></script>
	</body>

</html> 
```



# Git/Github

Git allows you to manage your codebase intelligently. It is a source control management system. It allows you to 'save' certain checkpoints and 'undo' certain checkpoints entirely. Its ability to branch allows you to test new ideas without messing up your main codebase if things go wrong.

GitHub is a service that will host your git repository online. This allows you to collaborate with other people as well as have your code accessible from the cloud, from wherever you need it. It is good to host here since it is a form of backup if your computer were ever to die.



### Learn Git

[https://try.github.io/](https://try.github.io/)



## Git Cheatsheet

Initialize a repository in a directory: `git init .`

Track all changes to all files in a directory: `git add .`

Track only a certain file: `git add file`

Commit changes: `git commit -m "Message about what you did"`

Discard all changes and roll back to last commit: `git reset hard --HEAD`

Push to Github: `git push origin master`

Pull latest changes from Github: `git pull`

Switch to master branch: `git checkout master`

Switch to someother branch: `git checkout someother`

Make a new branch: `git branch name`



# Deployment

Having the best website in the world is useless if no one can see it. In this class we will deploy our content to a service called Heroku. Heroku hosts your server and does all the hard work while you simply worry about code. It is a great service.

"Choose Heroku for the same reasons disruptive startups do: it’s the best platform for building with modern architectures, innovating quickly, and scaling precisely to meet demand."



### Step-By-Step Static Website Deployment

1. Create an account on Heroku
2. Install Heroku Toolbelt
3. Change into the directory with your website `cd folder_path`
4. Login to your account with the `heroku login` command from the terminal.
5. Create a new "dyno" via the terminal: `heroku create`
6. Make sure you have an `index.html` file, if so rename it to `index.php`
7. Add your changes for committing: `git add index.php`
8. Commit your changes: `git commit -m "Changed to php"`
9. Deploy to Heroku: `git push heroku master`
10. Browse to the URL given back to you



# Ruby

Ruby is a programming language from Japan created by Yukihiro Matsumoto.

"A dynamic, open source programming language with a focus on simplicity and productivity. It has an elegant syntax that is natural to read and easy to write"

Here is an example Ruby program.

```ruby
print "Please enter your name: "
name = gets
print "Please enter your age: "
age = gets.to_i

print "Your name is #{name} and you are #{age} years old."

```



## Input / Output

`gets` is a method that reads a string from the keyboard

`puts` is a method that puts a string on the console



## Strings

`.to_f` method on strings converts them to `Float`

`.to_i` method on strings converts them to Integer

`.reverse` method on strings reverses them

`.capitalize` method on strings capitalizes the first letter and lower cases the rest

`.include?` method returns true/false whether or not the string includes a given other string



## Arrays

Declaring an array: `myArray = ["Eric", "Maggy, "Billy"]` 

Declaring an empty array: `myArray = []` or `myArray = Array.new`

Appending an item to an array: `myArray << "Bob"`

Looping through an array:

```ruby
myArray = ["Eric", "Maggy", "Billy"]
myArray.each do |item|
  puts "Name: #{item}"
end
```

Indexing/Modifying: `myArray[0] = "Lilly"`

## Hashes

Declaring a hash: `myHash = {"Eric": 100, "Bob": 90}`

Declaring an empty hash: `myHash = {}` or `myHash = Hash.new`

Adding an item to a hash: `myHash["Luther"] = 0`

Looping through a hash:

```ruby
gradebook = {}
gradebook["Eric"] = 100
gradebook["Maggy"] = 100
gradebook["Billy"] = 70

gradebook.each do |name, grade|
  puts "#{name}: #{grade}"
end
```

For more on Ruby please visit [http://www.codeacademy.com](http://www.codeacademy.com)



## Methods

Declare a method that squares a number

```ruby
def square(num)
	return num * num
end
```



# Sinatra

Sinatra is a lightweight framework for putting your Ruby code on the web.

The way you interact with Sinatra applications is generally through a web browser. The  server generally runs on your IP address on port 3000.

To create a Sinatra application that is accessible via [http://localhost:3000](http://localhost:3000), do the following:

```ruby
require 'sinatra'

get '/' do
  message = "Hello World"
  return message
end
```

If you did this, the Sinatra application would listen when a user browses [http://localhost:3000](http://localhost:3000) then it would execute the following:

```ruby
message = "Hello World"
return message
```

and display `Hello World` in the web browser!



## Advanced Hello World

We can ask the user for their name and tell them hello by doing the following.

First we render an erb template on the `/` url that has a form on it. Then the `/say_hello` route will receive that via a POST request and get the name from the `params` hash then display it.

```ruby
require 'sinatra'

get '/' do
  	erb :ask_name
end

post '/say_hello' do
  name = params["name"]
  return "Hi, #{name}"
end
```



*ask_name.erb*

```html
<html>
	<body>
      	<h1>What is your name?</h1>
      	<form action="/say_hello" method="POST">
          <input type="text" name="name"/>
          <input type="submit" value="Submit"/>
      	</form>
  	</body>
</html>
```





# Exam 1 Review

1. Know how make a basic HTML Webpage.
2. Know how to make a CSS file that changes the `background-color` of `h1` tags to `yellow`
3. Know how to define your own reusable CSS class
4. Know what the basic HTML tags are and how to use them `<title>`, `<h1>`, `<p>`, `<a>`, `<div>`
5. Know how to initialize a Git repository in a directory
6. Know how to add files to a Git repository
7. Know how to commit changes with a commit message to a Git repository
8. Know basic Ruby:
   1. Know how to receive strings and numbers from the keyboard
   2. Know how to convert a string to a integer or float
   3. Know how to declare a Hash and retrieve items from a Hash
   4. Know how to declare and use Arrays
   5. Know how to declare a method
   6. Know the difference between print and puts
   7. Know how to loop through an Array and print out each item
   8. Know how to loop through a Hash and print out each key and value pair
9. Know Sinatra
   1. How to require Sinatra
   2. How to define a route that listens in on "http://localhost:3000/" via HTTP Get request and outputs "Hello World"
   3. Given a Post class, how to write a route that displays a new form for a new Post
   4. Given a Post class, how to write a route that retrieves a form submission for a new Post and persists it to the database (assuming the Post class has been properly setup using DataMapper)
10. Know Heroku
   1. How to create a new server via command line
   2. How to push a git repository to that new server

# Appendix

## Lean Startups

### What is a startup?

A startup is a human institution designed to create a new product or service under conditions of extreme uncertainty - *generally looking to make money*. A startup is not about a specific algorithm, product, or software. A startup is greater than the sum of its parts.



### Why do startups fail?

- Build a solution where there is no problem
- Build a product without a market for the product
- Fail to monetize effectively
- Took investments too early
- Failed to pivot
- Failed to rigorously define their goals, make hypotheses, and test those hypotheses with experiments

### Lean Startup Method

- Use the scientific method!
- Make a hypothesis (or several) and test them
- Build - Measure - Learn Feedback Loop
- Pivot or Persevere based on the knowledge gained from BML Feedback Loop

### Validated Learning

We must learn the truth about which elements of our strategy are working to realize our vision and which elements are *just crazy*. Customers will say anything. We want to learn what they really want, not what they say they want. Can we demonstrate empirically some truth about the startup's past, present, and future?

#### Questions to ask?

- What should we build and for whom?
- What market might we enter and do well?
- How could we build durable value that would not be subject to erosion by competition?

### Experimentation

What type of product do customers want? How do we know what features to build? The answer is to treat it as an experiment. Make a hypothesis and test it. Duhhh. If you cannot fail, you cannot learn. 



### Product Development Methodology

1. Find a problem out in the world.

2. Do consumers recognize that they have the problem you are trying to solve?

3. If there was a solution, would they buy it?

4. Would they buy it from us?

5. Can we build a solution for that problem?

   ​

Common Mistakes: 

- Building a solution before confirming that customers have a real problem. 
- Spending engineering time before figuring out how to sell and make the product.

### Step 1: Build and form hypothesis

Build the *minimum viable product* (MVP). The MVP is the version of the product that enables a full turn of the Build-Measure-Learn loop with a minimum amount of effort and least amount of **development** time. The MVP lacks many features that could be useful later but it is not just a prototype. The MVP is a prototype that is put in front of potential customers to gauge their reactions, and that may even be sold to them.

The MVP should allow you to test your hypothesis.

### Step 2: Measure

With an MVP in place, you should be able to start collecting data for your experiment. Maybe your hypothesis is: **people would be willing to pay X for a solution to Y**. Measuring this would involve going around and trying to sell the software and keeping track of who said yes and who said no. 

Initially, the question we probably want to answer is: **are we building something that nobody wants?**

### Step 3: Pivot or Persevere?

If our initial plan or strategy doesn't work (the initial hypothesis was disproven) then maybe it is time to *pivot*, is there a way of salvaging the code base and changing strategies? Maybe, we change ideas, markets, customers, or even the product entirely. At this early stage, we want to find out early if our initial strategy is headed towards failure. If our hypothesis was not disproven, we can *persevere* and enter a new BML Feedback loop by adopting a new hypothesis to measure and learn from. Entering new BML Feedback loops allows us to keep progress moving forward.

#### Assumptions - you know what they say

- Startups are built on assumptions.

- The first plan lays out a strategy that takes those assumptions as a given and proceeds to show how to achieve the company's vision.

- These assumptions are probably wrong.

- They should be tested as early as possible.

  ​

### The Minimum Viable Product

- Not the smallest product imaginable

- Helps start the process of learning as quickly as possible

- Think of the MVP as the fastest way to get through the Build-Measure-Learn Feedback loop

- Its goal is to test fundamental business hypotheses

  ​

Dropbox's MVP wasn't code at all. It was a video that showed how the product would work. Their beta wait list went from 5,000 people to 75,000 people overnight.

### The Last Word on MVPs

- Don't have to be beautiful

- Require the courage to put your assumptions to the test

- If we release a poorly designed product, but customers can figure out how to use it, maybe we don't need a better design (cough Craigslist, cough Ebay)

- If they can't figure out how to use it, maybe we do need a better design

- A simple experiment (of putting it in front of potential customers would help us learn the truth for the above)

- What if customers don't care about the way we do? Maybe we should just get something going

- Must be willing to put aside traditional professional standards to start the process of validated learning as soon as possible.

- This does not mean do **sloppy work** or **undisciplined work**.

  ​

#### Drop the mic

- Remove any feature, process, or effort that does not contribute directly to the learning you seek.

  ​

### Things to consider tracking

Consider tracking each of these things per person that enters your website. Capturing all of this will allow you to work backwards and maximize revenue. 

1. Acquisition - How did you get that person into your world? How did they find out about you? How did they hit your website?
2. Activation - Did they use your product / service? 
3. Retention - Did they use it again?
4. Revenue - Did they pay for it, how are you making money off of that person?
5. Referral - How and did they tell others?

Tracking all of this will allow you to generate more sophisticated experiments. One example hypothesis could be that 50% of the people that visit your app/service via FB ad will become paying customers.

### Rant 1 - Ideas are overrated

- Execution is everything.
- There are a ton of to-do lists, alarm clocks, social networks, gadgets and gizmos out there. People buy for different reasons not just the best and not just the cheapest.
- Many things that people buy were not the first. The iPod was not the first MP3 music player, the iPhone was not the first smartphone, etc.
- Don't worry about patents or people stealing your idea right now.
- Your idea is probably not unique.
- If a niche/market is competitive, people are *probably* making money.