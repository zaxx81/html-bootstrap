# Bootstrap
As web sites become more complicated, so does the task of handling styles and layout. Enter CSS frameworks. A CSS framework is just a set a pre-defined styles (and sometimes Javascript functions) that help us keep styles consistent and responsive. Some popular frame-works are Google's [Materialize](https://materializecss.com/), [Foundation](https://foundation.zurb.com/), and the one we'll explore today, Twitter's [Bootstrap](https://getbootstrap.com/). It's important to note that, though frameworks can seem like magic, they are just using regular CSS and JS under the hood. We can apply these pre-written styles by adding special classes to our HTML elements.

## Installing
You can [install bootstrap](https://getbootstrap.com/docs/4.3/getting-started/introduction/) with npm (we'll do that when we get to react), but for now, we'll use something called a CDN to load Bootstrap into our `index.html` file. This just means that we provide a link to our HTML page so that it can load the Bootstrap library directly from the Twitter Bootstrap servers when it loads.

```HTML
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
  </body>
</html>
```

From here, we'll build out a generic home page to get a sense of how Bootstrap works.

## Navbar

Let's start by using Bootstrap to create a [navbar](https://getbootstrap.com/docs/4.0/components/navbar/) for our webpage. Add the following code to `index.html`.

```HTML
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
```
There's a lot going on here. Our main parent component, `nav` holds all the HTML that makes up our navigation for the site. The important thing to note here are all the classes being applied to our different elements. Open this file in your browser to see a fully styled and positioned nav bar. We haven't written a single line of CSS yet. Instead, we tap into classes already defined by Bootstrap.

The other great thing about Bootstrap is that it is responsize. Resize your window and you'll see that at a certain point the navbar items will dissapear and you'll have a new button appear in the upper right hand corner. Clicking it will create a drop down menu for all of our nav items.

Let's add a few more Bootstrap elements to our HTML page.

[Jumbotron](https://getbootstrap.com/docs/4.0/components/jumbotron/) elements can be set to a specific size or, in our case, be set to fluid so that they take up the entire window.

```HTML
<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="display-1">Welcome</h1>
      <p class="lead">This is a modified jumbotron that occupies the entire horizontal space of its parent.</p>
  </div>
</div>
```


[Cards]() are nice for things like articles, videos or other contained data. (Though you can use them any way you like!) Let's add three in a row.

```HTML
<div class="card col-sm" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>

<div class="card col-sm" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>

<div class="card col-sm" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
```

Each card is styled so that the content is evenly spaced, but they are all stacked one on top of the other. It would be better if we could get them side by side. Luckily, Bootstrap comes with its own way to handle layouts that is very similar to CSS Grid. First, we need to wrap our cards in a container div. Then, we add another `div` with class `row`. (If we wanted coloumns we could add more `div`s with class `col`) This will ensure that all our cards show up side by side.

```HTML
<div class='container'>
  <div class='row'>
  <!-- our card divs go inside  -->
  </div>
</div>
```
Bootstrap can do a lot more than what we've looked at today. Like anything else, it may take a bit of research / practice, but once you get the hang of it, it will make your life a whole lot easier.

## Custom Styles

We can combine our own styles with the ones that Bootstrap gives us. Create a new file `styles.css` in the same directory as `index.html`. Then, import the file in the head. Make sure you import it **after** you import Bootstrap. Then, let's remove `navbar-light bg-light` from our `nav` element. These classes were adding some color to our navbar, but we want to add our own. Next, copy the following code into `styles.css`.

```CSS
.navbar {
  background-color: blue
}
```
As long as we import our own styles **after** Bootstrap's, we can override add or override any of Bootstraps defaults.
Most modern sites use a combination of Bootstrap (or some other framework) and their own styles.


# Bootstrap Challenge 

Use bootstrap to copy a website, choose one that impresses you!

## Release 0 - Planning: 
Come up with a plan for how you are going to implement your solution. How will you split the page up into columns and rows? What Bootstrap classes already exist that will help you create sections on the page? Will you need to add your own styles? What behavior does the page have? Can you recreate that with Bootstrap or will you need to write some custom Javascript? 

Try to make Bootstrap work for you as much as possible. Dig into the docs, read a few articles, do some research before you dive into the code. 

## Release 1 - HTML:
Start by editing your HTML file. Think about what tags you'll need. Remember, CSS is how we style and handle layout, HTML is about structure and meaning. Can you use Bootstrap elements to create a better looking site?

## Release 2 - Layout: 
Start positioning your elements using Bootstrap's columns and rows. Don't worry about colors and fonts just yet. You will want to think about font-size though as adjusting this can break your layout pretty quickly. 

## Release 3 - Style: 
Add colors, images, fonts or anything else you want to make your page look as close to the original as possible. 
