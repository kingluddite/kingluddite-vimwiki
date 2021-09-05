# Bootstrap Week 03 Notes
## What are HTML custom data-* attributes?
* New in HTML5
* Allow you to create custom attributes to store any data you want in any HTML element
    - Then later, you can access them via JavaScript or CSS

## How do I create a HTMl custom data attribute
* Create an attribute that starts with `data-`
* Then add a string (must be at least one lower case character) of your choice

## Example
* Replace text inside a paragraph with text inside a button
* You add a function
* You add an event
* The event is triggered using the data attribute

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Custom Data Attribute Example</title>
  </head>
  <body>
    <button class="my-button" data-whatever="Yo">Swap Text</button>
    <p class="my-text">Old Text</p>
    <script src="./script.js"></script>
  </body>
</html>
```

`script.js`

```js
const myBtnEl = document.querySelector('.my-button');
const myTxtEl = document.querySelector('.my-text');

function swapSomeText() {
  myTxtEl.textContent = myBtnEl.getAttribute('data-whatever');
}

myBtnEl.addEventListener('click', swapSomeText);
```
* **note** Bootstrap's JavaScript plugins make heavy use of these `data-*` attributes that have been customized by Boostrap
* You just add the right data- attributes and all the JavaScript happens without you having to write JavaScript
    - We used this before in the Bootstrap `nav` and it's `data-toggle="collapse"` attribute
    - And the `data-target="#navbarSupportedContent"` attribute

## The Nav Component
* We already learned about two navigation components
    - navbar
    - breadcrumbs
* There is antother navigation component Bootstrap offers called `nav`
    - This sets up different kinds of navigation interfaces using either the `ul` or `nav` element combined with the class of `nav`

### Examples
* Simple sets of links (horizontal and vertical)
* More complex 
    - tabs
    - pills
* **note** We can use JavaScript plugins can be extended to create panes of content
* Using the predefined `built-in` custom data attributes this behavior can be added without having to write any JavaScript code

## Exercise on Tabs

`aboutus.html`

```
// MORE CODE

      <div class="row row-content">
        <div class="col">
          <h3>Community Partners</h3>
          <ul class="nav nav-tabs">
            <li class="nav-item">
              <a
                class="nav-link active"
                role="tab"
                href="#bootstrap"
                data-toggle="tab"
                >Bootstrap Outfitters</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" role="tab" href="#git" data-toggle="tab"
                >Git Out Expeditions</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" role="tab" href="#mongo" data-toggle="tab"
                >Mongo Fly Shop</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" role="tab" href="#node" data-toggle="tab"
                >Node Outdoor Apparel</a
              >
            </li>
          </ul>
          <div class="tab-content">
            <div
              role="tabpanel"
              class="tab-pane fade show active"
              id="bootstrap"
            >
              <h4>
                Bootstrap Outfitters <small>Outdoor Gear Specialists</small>
              </h4>
              <p class="d-none d-sm-block">
                Bootstrap Outfitters supplies you with the gear you need at
                prices you can't beat.
              </p>
            </div>

            <div role="tabpanel" class="tab-pane fade" id="git">
              <h4>
                Git Out Expeditions <small>Group Adventure Expeditions</small>
              </h4>
              <p class="d-none d-sm-block">
                Join Git Out Expeditions to explore new horizons with a group of
                other adventurers!
              </p>
            </div>

            <div role="tabpanel" class="tab-pane fade" id="mongo">
              <h4>
                Mongo Fly Shop <small>Your Neighborhood Fly Fishing Shop</small>
              </h4>
              <p class="d-none d-sm-block">
                Need a new fishing pole, a tacklebox, or flies of all kinds?
                Stop by Mongo Fly Shop.
              </p>
            </div>

            <div role="tabpanel" class="tab-pane fade" id="node">
              <h4>
                Node Outdoor Apparel <small>Outdoor Clothes & Shoes</small>
              </h4>
              <p class="d-none d-sm-block">
                From polar fleeces to swimsuits, hiking boots to waders, a visit
                to Node will be sure to get you covered.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>


// MORE CODE
```

`styles.css`

* Make them look nicer than default Bootstrap

```
.tab-content {
  border: 1px solid #ddd;
  border-top: none;
  padding: 10px;
}

```

## Collapse and Accordion
* Combining Boostrap Card component to create a type of Collapse called an Accordion

## We'll replace our tabs with an Accordion
* Delete `nav nav-tabs` "ul"

`aboutus.html`

```
// MORE CODE

      <div class="row row-content">
        <div class="col">
          <h3>Community Partners</h3>

          <div id="accordion">
            <div class="card">
              <div role="tab" class="card-header">
                <a data-toggle="collapse" data-target="#bootstrap">
                  <h4>
                    Bootstrap Outfitters <small>Outdoor Gear Specialists</small>
                  </h4>
                </a>
                <div
                  class="collapse show"
                  id="bootstrap"
                  data-parent="#accordion"
                >
                  <div class="card-body">
                    <p class="d-none d-sm-block">
                      Bootstrap Outfitters supplies you with the gear you need
                      at prices you can't beat.
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <div class="card">
              <div role="tab" class="card-header">
                <a class="collapsed" data-toggle="collapse" data-target="#git">
                  <h4>
                    Git Out Expeditions
                    <small>Group Adventure Expeditions</small>
                  </h4>
                </a>
                <div class="collapse" id="git" data-parent="#accordion">
                  <div class="card-body">
                    <p class="d-none d-sm-block">
                      Join Git Out Expeditions to explore new horizons with a
                      group of other adventurers!
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <div class="card">
              <div role="tab" class="card-header">
                <a
                  class="collapsed"
                  data-toggle="collapse"
                  data-target="#mongo"
                >
                  <h4>
                    Mongo Fly Shop
                    <small>Your Neighborhood Fly Fishing Shop</small>
                  </h4>
                </a>
                <div class="collapse" id="mongo" data-parent="#accordion">
                  <div class="card-body">
                    <p class="d-none d-sm-block">
                      Need a new fishing pole, a tacklebox, or flies of all
                      kinds? Stop by Mongo Fly Shop.
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <div class="card">
              <div role="tab" class="card-header">
                <a class="collapsed" data-toggle="collapse" data-target="#node">
                  <h4>
                    Node Outdoor Apparel <small>Outdoor Clothes & Shoes</small>
                  </h4>
                </a>
                <div class="collapse" id="node" data-parent="#accordion">
                  <div class="card-body">
                    <p class="d-none d-sm-block">
                      From polar fleeces to swimsuits, hiking boots to waders, a
                      visit to Node will be sure to get you covered.
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

// MORE CODE
```

* Bootstrap changes - update since verison 4.5.1 (But looks like that was fixed with a more recent update)
* You can remove the custom `.tab-content` CSS as you are not using that element any more (keep your code clean)

`styles.css`

```
.tab-content {
  border: 1px solid #ddd;
  border-top: none;
  padding: 10px;
}
```

## Tooltips and Modals
* [docs](https://getbootstrap.com/docs/4.0/components/tooltips/)

### What is difference between Tooltip and Popovers?
* Tooltip - hover over element on page and text pops up
* Popover - same as tooltip but you need to click on the element in order to see the info (rather than just a hover over event)
* This is possible using JavaScript
  - This behavior is possible because we added the `popper.js` JavaScript library
    + popper.js is a library that is required with:
      * popovers
      * tooltips
        - **note** Tooltips are "opt in" won't work on a page without first being initialize (for performance reasons)
        - This means we'll need to add some JavaScript (in the form of jQuery) that Bootstrap provides to initialize tooltips
      * And most dropdown menus in Bootstrap

### Enable tooltips everyone
* We select all tooltips by their `data-toggle` attribute

```
$(function () {
  $('[data-toggle="tooltip"]').tooltip()
})
```

* We'll add it to `index.html`

```
// MORE CODE
  <script
    src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
    integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
    crossorigin="anonymous"
  ></script>
  <script>
    $(function () {
      $('[data-toggle="tooltip"]').tooltip();
    });
  </script>
</html>
```

### Adding the actual tooltip
* Tooltip is not built using classes but rather using `custom data attributes`

`index.html`

```
// MORE CODE

  <body>
    <header class="jumbotron jumbotron-fluid">
      <div class="container">
        <div class="row">
          <div class="col">
            <h1>NuCamp</h1>
            <h2>a better way to camp</h2>
          </div>
          <div class="col-md-4 col-xl-2 mt-4">
            <a
              href="#reserveForm"
              role="button"
              class="btn btn-lg btn-info"
              data-toggle="tooltip"
              title="Or call us at 1-800-123-1234"
              >Anchor Text</a
            >
          </div>
        </div>
      </div>
    </header>

// MORE CODE
```

* If you want to pass HTML to tooltip
  - Pass `data-html="true"`

```
// MORE CODE

  <a
    href="#reserveForm"
    role="button"
    class="btn btn-lg btn-info"
    data-toggle="tooltip"
    data-html="true"
    title="Or call us at<br /> <strong>1-800-123-1234</strong>"
    >Anchor Text</a
  >

// MORE CODE
```

* You can also place where the tooltip appears using `data-placement="bottom"`

```
// MORE CODE

<a
  href="#reserveForm"
  role="button"
  class="btn btn-lg btn-info"
  data-toggle="tooltip"
  data-html="true"
  data-placement="left"
  title="Or call us at<br /> <strong>1-800-123-1234</strong>"
  >Anchor Text</a
>

// MORE CODE
```

## Modals
* Modal is smaller dialog window that opens on the parent window and disables the parent window until the modal is closed (while still keeping the parent window partially visible behind it)
* This is an improvement over a boring alert()
* Modals are fully customizable

### Remember font awesome is included with an install
`$ npm i font-awesome@4.7.0`

```
    <!-- Additional CSS must be placed after Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="node_modules/font-awesome/css/font-awesome.min.css"
    />
```

`index.html`

```
// MORE CODE

            <li class="nav-item">
              <a class="nav-link" href="contact.html">Contact</a>
            </li>
          </ul>
          <span class="navbar-text ml-auto">
            <a
              href=""
              role="button"
              data-toggle="modal"
              data-target="#loginModal"
            >
              <i class="fa fa-sign-in"></i> Login
            </a>
          </span>
        </div>
      </div>
    </nav>


// MORE CODE
```

## Where do we put our modal HTML?
* **tip** We can put it anywhere but a good idea is to place it close to the code that opens the modal
* **note** `sr-only` only available to screen reading software

* Place just after closing `</nav>`

`index.html`

```
// MORE CODE

<div id="loginModal" class="modal fade" role="dialog">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h3 class="modal-title">Login</h3>
                    <button type="button" class="close" data-dismiss="modal">&times;</button>
                </div>
                <div class="modal-body">
                    <div class="container-fluid">
                        <form>
                            <div class="form-row">
                                <div class="form-group col-12">
                                    <label class="sr-only" for="loginEmail">Email address</label>
                                    <input type="email" class="form-control form-control-sm" id="loginEmail" placeholder="Enter email">
                                </div>
                                <div class="form-group col-12">
                                    <label class="sr-only" for="loginPassword">Password</label>
                                    <input type="password" class="form-control form-control-sm" id="loginPassword" placeholder="Password">
                                </div>
                                <div class="col">
                                    <div class="form-check">
                                        <input class="form-check-input" type="checkbox">
                                        <label class="form-check-label"> Remember me</label>
                                    </div>
                                </div>
                            </div>
                            <div class="form-row">
                                <button type="button" class="btn btn-secondary btn-sm ml-auto" data-dismiss="modal">Cancel</button>
                                <button type="submit" class="btn btn-primary btn-sm ml-1">Sign in</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
// MORE CODE
```

## Bootstrap Carousel
* `data-ride` - tells browser to start carousel on page load
* `d-block w-100` - display and sizing utility classes that help prevent the browser default image alignment from taking over our images

### Working Carousel
```
// MORE CODE

    <div class="container">
      <div class="row row-content">
        <div class="col-8 mx-auto">
          <div id="homeCarousel" class="carousel slide" data-ride="carousel">
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img
                  src="./assets/img/breadcrumb-trail.jpg"
                  alt="Breadcrumb Trail Campground"
                  class="d-block w-100"
                />
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/react-lake.jpg"
                  alt="React Lake Campground"
                  class="d-block w-100"
                />
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/chrome-river.jpg"
                  alt="Chrome River Campground"
                  class="d-block w-100"
                />
              </div>
            </div>
          </div>
        </div>
      </div>

// MORE CODE
```

### Adding text captions
```
// MORE CODE

          <div id="homeCarousel" class="carousel slide" data-ride="carousel">
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img
                  src="./assets/img/breadcrumb-trail.jpg"
                  alt="Breadcrumb Trail Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>Breadcrumb Trail Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/react-lake.jpg"
                  alt="React Lake Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>React Lake Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/chrome-river.jpg"
                  alt="Chrome River Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>Chrome River Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

// MORE CODE
```

## Adding indicators
```
// MORE CODE

>
      <div class="row row-content">
        <div class="col-8 mx-auto">
          <div id="homeCarousel" class="carousel slide" data-ride="carousel">
            <ol class="carousel-indicators">
              <li
                data-target="#homeCarousel"
                data-slide-to="0"
                class="active"
              ></li>
              <li data-target="#homeCarousel" data-slide-to="1"></li>
              <li data-target="#homeCarousel" data-slide-to="2"></li>
            </ol>

// MORE CODE
```

## Manual controls
* Placed just outside of the carousel inner div

```
// MORE CODE

            <!-- /.carousel inner -->
            <a
              href="#homeCarousel"
              role="button"
              data-slide="prev"
              class="carousel-control-prev"
            >
              <span class="carousel-control-prev-icon"></span>
              <span class="sr-only">Previous</span>
            </a>
            <a
              href="#homeCarousel"
              role="button"
              data-slide="prev"
              class="carousel-control-next"
            >
              <span class="carousel-control-next-icon"></span>
              <span class="sr-only">Next</span>
            </a>
          </div>
        </div>
      </div>

// MORE CODE
```

## Custom styles
`styles.css`

```
.carousel-caption {
    background-color: rgba(0, 0, 0, 0.5);
}

.carousel {
    border: solid #5637DD;
}
```

## Final index.html
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags always come first -->
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <!-- <link -->
    <!--   href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0&#45;beta3/dist/css/bootstrap.min.css" -->
    <!--   rel="stylesheet" -->
    <!--   integrity="sha384&#45;eOJMYsd53ii+scO/bJGFsiCZc+5NDVN2yr8+0RDqr0Ql0h+rP48ckxlpbzKgwra6" -->
    <!--   crossorigin="anonymous" -->
    <!-- /> -->
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
      integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
      crossorigin="anonymous"
    />
    <!-- Additional CSS must be placed after Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="node_modules/font-awesome/css/font-awesome.min.css"
    />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Lobster&display=swap"
      rel="stylesheet"
    />

    <link rel="stylesheet" href="./assets/css/styles.css" />
    <title>NuCamp: A Better Way To Camp</title>
  </head>

  <body>
    <header class="jumbotron jumbotron-fluid">
      <div class="container">
        <div class="row">
          <div class="col">
            <h1>NuCamp</h1>
            <h2>a better way to camp</h2>
          </div>
          <div class="col-md-4 col-xl-2 mt-4">
            <a
              href="#reserveForm"
              role="button"
              class="btn btn-lg btn-info"
              data-toggle="tooltip"
              data-html="true"
              data-placement="left"
              title="Or call us at<br /> <strong>1-800-123-1234</strong>"
              >Anchor Text</a
            >
          </div>
        </div>
      </div>
    </header>

    <nav class="navbar navbar-expand-sm navbar-dark sticky-top">
      <div class="container">
        <button
          class="navbar-toggler ml-auto"
          type="button"
          data-toggle="collapse"
          data-target="#nucampNavbar"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="nucampNavbar">
          <ul class="navbar-nav">
            <li class="nav-item active">
              <a class="nav-link" href="#"
                ><i class="fa fa-home fa-lg"></i> Home</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" href="aboutus.html"
                ><i class="fa fa-info fa-lg"></i> About</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" href="sites.html"
                ><i class="fa fa-list fa-lg"></i> Sites</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" href="contact.html"
                ><i class="fa fa-address-card fa-lg"></i> Contact</a
              >
            </li>
          </ul>
          <span class="navbar-text ml-auto">
            <a
              href=""
              role="button"
              data-toggle="modal"
              data-target="#loginModal"
            >
              <i class="fa fa-sign-in"></i> Login
            </a>
          </span>
        </div>
      </div>
    </nav>

    <div id="loginModal" class="modal fade" role="dialog">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h3 class="modal-title">Login</h3>
            <button type="button" class="close" data-dismiss="modal">
              &times;
            </button>
          </div>
          <div class="modal-body">
            <div class="container-fluid">
              <form>
                <div class="form-row">
                  <div class="form-group col-12">
                    <label class="sr-only" for="loginEmail"
                      >Email address</label
                    >
                    <input
                      type="email"
                      class="form-control form-control-sm"
                      id="loginEmail"
                      placeholder="Enter email"
                    />
                  </div>
                  <div class="form-group col-12">
                    <label class="sr-only" for="loginPassword">Password</label>
                    <input
                      type="password"
                      class="form-control form-control-sm"
                      id="loginPassword"
                      placeholder="Password"
                    />
                  </div>
                  <div class="col">
                    <div class="form-check">
                      <input class="form-check-input" type="checkbox" />
                      <label class="form-check-label"> Remember me</label>
                    </div>
                  </div>
                </div>
                <div class="form-row">
                  <button
                    type="button"
                    class="btn btn-secondary btn-sm ml-auto"
                    data-dismiss="modal"
                  >
                    Cancel
                  </button>
                  <button type="submit" class="btn btn-primary btn-sm ml-1">
                    Sign in
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="row row-content">
        <div class="col-8 mx-auto">
          <div id="homeCarousel" class="carousel slide" data-ride="carousel">
            <ol class="carousel-indicators">
              <li
                data-target="#homeCarousel"
                data-slide-to="0"
                class="active"
              ></li>
              <li data-target="#homeCarousel" data-slide-to="1"></li>
              <li data-target="#homeCarousel" data-slide-to="2"></li>
            </ol>
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img
                  src="./assets/img/breadcrumb-trail.jpg"
                  alt="Breadcrumb Trail Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>Breadcrumb Trail Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/react-lake.jpg"
                  alt="React Lake Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>React Lake Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
              <div class="carousel-item">
                <img
                  src="./assets/img/chrome-river.jpg"
                  alt="Chrome River Campground"
                  class="d-block w-100"
                />
                <div class="carousel-caption">
                  <h3>Chrome River Campground</h3>
                  <p class="d-none d-sm-block">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Impedit necessitatibus earum ullam nulla reiciendis beatae,
                    perspiciatis, voluptates asperiores debitis fuga quisquam
                    quas voluptatem, aliquid repellat ea at eius consequatur
                    consectetur?
                  </p>
                </div>
              </div>
            </div>
            <!-- /.carousel inner -->
            <a
              href="#homeCarousel"
              role="button"
              data-slide="prev"
              class="carousel-control-prev"
            >
              <span class="carousel-control-prev-icon"></span>
              <span class="sr-only">Previous</span>
            </a>
            <a
              href="#homeCarousel"
              role="button"
              data-slide="prev"
              class="carousel-control-next"
            >
              <span class="carousel-control-next-icon"></span>
              <span class="sr-only">Next</span>
            </a>
          </div>
        </div>
      </div>
      <div class="row row-content align-items-center">
        <div class="col-sm-4 order-sm-last col-md-3">
          <h2 class="text-sm-right">Discover & Review</h2>
          <h3>Our Campsites</h3>
          <p>
            Explore our growing database of curated campsites and leave your own
            reviews!
          </p>
        </div>
      </div>
    </div>

    <div>
      <h2>Featured Campsites</h2>
      <h3>React Lake Campground</h3>
      <p>
        Nestled in the foothills of the Chrome Mountains, this campground on the
        shores of the pristine React Lake is a favorite for fly fishers.
      </p>
    </div>

    <div>
      <h2>Our Community Partners</h2>
      <h3>Bootstrap Outfitters</h3>
      <p>
        Bootstrap Outfitters supplies you with gear you need at prices you can't
        beat.
      </p>
    </div>

    <footer>
      <div>
        <h5>Links</h5>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Sites</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>
      <div>
        <h5>Social</h5>
        <a href="http://instagram.com/">Instagram</a>
        <a href="http://facebook.com/">Facebook</a>
        <a href="http://twitter.com/">Twitter</a>
        <a href="http://youtube.com/">YouTube</a>
      </div>
      <div>
        Tel: 1-206-555-1234<br />
        Email: campsites@nucamp.co
      </div>
    </footer>
  </body>
  <!-- jQuery must come first, then Popper.js, then the Bootstrap JavaScript plugins.-->
  <!-- <script src="node_modules/jquery/dist/jquery.slim.min.js"></script> -->
  <!-- <script src="node_modules/popper.js/dist/umd/popper.min.js"></script> -->
  <!-- <script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script> -->
  <script
    src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
    integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
    crossorigin="anonymous"
  ></script>
  <script
    src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
    integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
    crossorigin="anonymous"
  ></script>
  <script
    src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
    integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
    crossorigin="anonymous"
  ></script>
  <script>
    $(function () {
      $('[data-toggle="tooltip"]').tooltip();
    });
  </script>
</html>

```

## Change it up
* Everyone did a nice job of changing things up

## Challenge Codepen
* checkbox and radio buttons docs - https://getbootstrap.com/docs/4.5/components/buttons/#checkbox-and-radio-buttons

### Solution
```
<!-- You will change the HTML code below this comment only. -->

<div class="container-fluid">
  <form>
    <div class="form-group row">
      <label class="col-sm-2 col-form-label">Ice Cream Flavors:</label>
      <div class="col-4 btn-group btn-group-toggle" data-toggle="buttons">
        <label class="btn btn-success active">
          <input type="radio" name="iceCreamFlavor" id="mintchocolate" value="mint chocolate" autocomplete="off" checked />Mint Chocolate
        </label>
        <label class="btn btn-light">
          <input type="radio" name="iceCreamFlavor" id="vanilla" value="vanilla" autocomplete="off" />Vanilla
        </label>
        <label class="btn btn-danger">
          <input type="radio" name="iceCreamFlavor" id="strawberry" value="strawberry" autocomplete="off" />Strawberry
        </label>
      </div>
    </div>
    <div class="form-group row mx-auto">
      <button type="button" onclick="order()" class="btn btn-primary">Order</button>
    </div>
  </form>
</div>
<!-- You will change the HTML code above this comment only. -->
```

URL - https://codepen.io/minae/pen/VwZEZpL (solution)

## JavaScript Basics Overview
* if/else
  - typing in console

```
let dogSits = true;
let dogGetsTreat;
if (dogSits === true) {
    dogGetsTreat = true;
}
dogGetsTreat
```

## refactor to:
`if (dogSits) { ... }`

* If dogSits is true you don't need to be redundant with dogSits === true
* If not true the recommended way to write it is `if (!dogSits) { ... }`

But if not a boolean comparison use:

```
let roll = 1;
if (roll === 1) {
    console.log("You win!");
}
```

* Can't use just `if (roll)` because that would always be true
* Order of operations to JavaScript operators

```
if (roll === 1 || roll === 6) {
    console.log("You win!");
}
```

## If else if else
```
if (roll === 1 || roll === 6) {
    console.log("You win!");
} else if (roll <= 3 ) {
    console.log("Roll again!");
}
```

* **note** 2 separate if statements are different
* In console type `shift` + `enter` to type two lines (instead of just hitting `Enter`)

```
if (roll === 1 || roll === 6) {
    console.log("You win!");
} // after this ending curly brace, press Shift+Enter instead of Enter
if (roll <= 3) {
    console.log("Roll again!");
} // now press Enter
```

* **tip** If you just have one if condition you can omit the curly braces but a best practice for readability is to include them
* No semi-colon is needed for condition closing curly braces
* truthy/falsy value
* up arrow key brings up previous console entries to save you from retyping them

## Challenge Switch Statement
```
/* --------------- Challenge 1 --------------*/

const age = 15;
if ( age >= 16 ) {
    console.log("You are old enough to drive.");
} else {
    console.log("You are not yet old enough to drive.");
}

/* ----------- End of Challenge 1 -----------*/


/* --------------- Challenge 2 --------------*/

const drinkSize = "small";
switch(drinkSize) {
    case "small":   console.log("A small drink is 10 ounces.");
                    break;
    case "medium":  console.log("A medium drink is 16 ounces.");
                    break;
    case "large":   console.log("A large drink is 22 ounces.");
                    break;
    default:        console.log("Unknown drink size.");
}

/* ----------- End of Challenge 2 -----------*/

```

Solution URL - https://codepen.io/minae/pen/MWgGaQr

## Quiz
* Don't memorize, use google foo to find (this helps your reading and understanding documentation)
* This is not cheating!
