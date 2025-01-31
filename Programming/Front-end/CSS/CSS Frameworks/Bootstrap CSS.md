# Bootstrap CSS

[Bootstrap](https://getbootstrap.com/) is a CSS Framework which provides us with pre-styled components and pre-defined layouts to make creating responsive and appealing web pages easier. 

We can include Bootstrap into our projects by:

- Using a *Package Manager*.
- Using a *CDN*.
## Including via CDN:

A CDN or *Content Delivery Network* is a group of geographically distributed servers that speed up the delivery of web content by bringing it closer to where users are.

We can use a CDN in this instance to include the Bootstrap CSS files into our project via link instead of actually serving the files ourselves, this way we can make use of the files in our project and when our users load our web-pages they will download the CSS files that are used from the closest server geographically to them.

Two links to the Bootstrap CDN can be found on on their [website](https://getbootstrap.com/). The *stylesheet* is provided in the `<head>` section of our web page and the script files for functionality provided by the framework must be placed at the end of our `<body>`.

```html nums {6-11,18-22}
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
    <title>Test</title>
  </head>
  <body>
    <div>
      <p>Some Stuff Here</p>
    </div>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```
## Card Component

Let's look at the process of adding the *Card Component* to our project, we can simply navigate to the card section of the [documentations](https://getbootstrap.com/docs/5.3/getting-started/introduction/). 

![](Pictures/Bootstrap%20CSS%20-%20Card%20Component.png)

Here we can see a preview of the component and the code associated with it. Notice that styling is predominately managed by adding predefined classes to our HTML elements.

Let's add this component to our web page.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
    <title>Test</title>
  </head>
  <body>
    <div class="card" style="width: 18rem">
      <img src="flower.jpg"card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

![](Pictures/Bootstrap%20CSS%20-%20Card%20Example.png)

If we'd like to modify the styles provided by Bootstrap we must include our adjustments **after** when the stylesheet is inserted into our HTML file.

```html nums {12-20}
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
    <style>
      /* TODO 4: Use flexbox to center the card in the vertical and horizontal center. */
      .flex-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
    </style>
    <title>Test</title>
  </head>
  <body>
    <div class="flex-container">
      <div class="card" style="width: 18rem">
        <img src="flower.jpg"card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">
            Some quick example text to build on the card title and make up the
            bulk of the card's content.
          </p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

Here we include our style **overrides** after we have included the link to Bootstrap. We can also include our own local CSS file to override the Bootstrap styling as long as it is inserted after the Bootstrap link.

Let's see the result:

![](Pictures/Bootstrap%20CSS%20-%20Example%20Styled.png)

# Bootstrap Layouts

In order to simply the layout of web pages Bootstrap utilizes a *12 Column System* whereby columns will be shifted over into the following rows if there is not enough space on screen to render them alongside one another.

![](Pictures/Bootstrap%20CSS%20-%2012%20Column%20System.png)

Let's look at an example of this behavior in code.
## Layout Code Example

```html
    <div class="container">Container
      <div class="row">Row
        <div class="col">Col 1</div>
        <div class="col">Col 2</div>
        <div class="col">Col 3</div>
        <div class="col">Col 4</div>
        <div class="col">Col 5</div>
        <div class="col">Col 6</div>
        <div class="col">Col 7</div>
        <div class="col">Col 8</div>
        <div class="col">Col 9</div>
        <div class="col">Col 10</div>
        <div class="col">Col 11</div>
        <div class="col">Col 12</div>
      </div>
    </div> 
```

I've given these elements borders to and margins to aid in visually identifying them. The container in green, row in blue and each column in red. Without including Bootstrap you see the following:

![](Pictures/Bootstrap%20CSS%20-%20Example%20No%20Bootstrap.png)

Upon resizing this web page notice no change in behavior:

![](Pictures/Bootstrap%20CSS%20-%20Example%20No%20Bootstrap%20Resize.png)

Now let's include link to the Bootstrap CDN in the `<head>`:

![](Pictures/Bootstrap%20CSS%20-%20Example%20With%20Bootstrap.png)

And let's resize the page:

![](Pictures/Bootstrap%20CSS%20-%20Example%20Bootstrap%20Resize.png)

Notice how columns are dynamically pushed over to new rows when the size is reduced. This is a result of the *Auto-Fit* behavior of Bootstrap. 
## Container Sizing

The maximum width of the *container* is dictated by the container class used.

![](Pictures/Bootstrap%20CSS%20-%20Container%20Sizes.png)

![](Pictures/Bootstrap%20CSS%20-%20Container%20Size%20Examples.png)

In the screenshot above at the size of the browser page you can see where different containers my have margins at the edges of the page or where certain containers may fill the entire screen, remember this dynamically changes based on the size of the browser window.
## Sized Columns

![](Pictures/Bootstrap%20CSS%20-%20Sized%20Columns.png)

Just like when we were working with the grid layout in Tkinter, we can allow columns to span over multiple columns by providing a number a long with the `col` class name to specify how many columns it should span over.
# Bootstrap Breakpoints

We can use *Breakpoints* to specify a size to where our columns will collapse and be spaced to each column taking up the entire screen.

In other words, when the width of our browser is reduced to a specified threshold each column will span the entire screen and subsequent columns will be pushed on to new rows.

![](Pictures/Bootstrap%20CSS%20-%20Breakpoint%20Tiers.png)

Let's look at an example using the *medium* tier (`col-md`).

- Size Greater Than The Breakpoint:

![](Pictures/Bootstrap%20CSS%20-%20Above%20Medium%20Breakpoint.png)

- Size Less Than The Breakpoint:

![](Pictures/Bootstrap%20CSS%20-%20Size%20Less%20Than%20Breakpoint.png)

## Multiple Breakpoints

![](Pictures/Bootstrap%20CSS%20-%20Multiple%20Breakponts.png)

We can also specify multiple breakpoints, this way the amount of columns that a single column will span will depend on the size of the browser window while still collapsing to a single column the size of the screen at a the minimum size.
## Mixing and Matching Layouts

![](Pictures/Bootstrap%20CSS%20-%20Mixing%20and%20Matching%20Layouts.png)

We can also mix and match multiple column layouts in a single row, Bootstrap will dynamically adjust the position of these columns based on the size of our web-page.

**Note:** The lonely `col` column will automatically take up the remaining space in the row.
# Bootstrap Render Forms

We can use the `render_form()` Macro with Flask to render Bootstrap Styled Flask WTForms.

First we will need to import Flask, Bootstrap and WTForms. Then we initialize our application and create our form class. In this example we're creating a form for a blogpost.

**Note**: We are using a CKEditorField in this example but it is is not a necessary component to utilize Bootstrap Render Forms

```python
from flask import Flask
from flask_bootstrap import Bootstrap5
from flask_ckeditor import CKEditor, CKEditorField
from wtforms import StringField, SubmitField
from wtforms.validators import URL, DataRequired, Length

app = Flask(__name__)
Bootstrap5(app)

class PostForm(FlaskForm):
    title = StringField("Post Title", validators=[DataRequired(), Length(max=250)])
    subtitle = StringField("Subtitle", validators=[DataRequired(), Length(max=250)])
    author_name = StringField(
        "Author Name", validators=[DataRequired(), Length(max=250)]
    )
    img_url = StringField(
        "Image URL", validators=[DataRequired(), URL(), Length(max=250)]
    )
    body = CKEditorField("Post Body", validators=[DataRequired()])
    submit = SubmitField("Submit", id="submit")
```

In order to render our form in HTML we can pass it through to our route using Jinja templates.

```python
# TODO: add_new_post() to create a new blog post
@app.route("/new-post", methods=["GET", "POST"])
def new_post():
    new_post_form = PostForm()
    return render_template("make-post.html", form=new_post_form)
```

We will need to import our form into our HTML page and place it:

```html
{% from 'bootstrap4/form.html' import render_form %}
<div class="container">
<div class="row">
  <div class="col-lg-8 col-md-10 mx-auto">
	{{ render_form(form) }}
	<style>
	  .form-control {
		margin-bottom: 15px;
	  }

	  #submit {
		margin-top: 15px;
	  }
	</style>
  </div>
</div>
</div>
```

**Note**: We are simply adjusting the style using divs and classes for this example, the form on the webpage looks as follows:

![](Pictures/Bootstrap%20CSS%20-%20Bootstrap%20Form%20Macro.png)

