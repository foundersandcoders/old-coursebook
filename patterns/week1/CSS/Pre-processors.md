# Pre-processors (in CSS)

## What?
CSS pre-processors *extend* CSS by adding more features that CSS by itself does not have.  An example of this is Sass (syntactically awesome stylesheets), which is processed into normal CSS. Other examples of CSS pre-processors include Less, Stylus, and SCSS.

## Why/How?
Why use these? Because they make things easier and save time and typing. They give us more *abstraction* than conventional CSS (which is very simple) can offer. Here are two examples:

* **Nested definitions**: in conventional CSS we would have to write this:
``` css
.container {
    width: 100%;
}
.container h1 {
    color: red;
}
```

* Whereas in Sass you would be able to write this;
``` css
.container {
    width: 100%;
    h1{
      color: red;
    }
}
```

* This is quicker because it nests in an intuitive way and you have to write less.
* **Variables, functions, and other programming capability**: In conventional CSS we would write this:
```css
h1 {
    background: #eeffcc;
}
body {
    background: #eeffcc;
}
```
* In Sass we can do this using a *variable*:
```css
$primaryColor: #eeffcc;
h1 {
    background: $primaryColor;
}
body {
    background: $primaryColor;
}
```
* This saves us typing out the same tricky color combination lots of times.

## Pros and Cons
### Pros:
* Saves time and energy because you don't have to repeatedly type out the same properties
* If you master it, it can be very intuitive and easy to read and maintain.
* Nesting will make your CSS more organised.
* Easier to make prettier websites!
* Lots of frameworks built on top of these pre-processors (e.g. Compass).

### Cons
* Everyone on a project needs to use the same pre-processor - if one person has LESS and another uses Sass, this won't work.
* Easier to make mistakes in than CSS, especially while you are learning.

## Links
* Top recommendation: [An Introduction to CSS Pre-Processors](http://vanseodesign.com/css/css-preprocessors/)
* More detailed: [A walkthrough of the capabilities of Sass](http://learn.shayhowe.com/advanced-html-css/preprocessors/#scss-sass)
* [Ten Reasons You Should Be Using CSS Pre-Processors](https://www.urbaninsight.com/2012/04/12/ten-reasons-you-should-be-using-css-preprocessor)
* More detailed: [An Introduction To CSS Pre-Processors (Sass, LESS, Stylus)](http://htmlmag.com/article/an-introduction-to-css-preprocessors-sass-less-stylus)
* Further Resources (just Sass): [Getting Started with Sass](https://scotch.io/tutorials/getting-started-with-sass)
