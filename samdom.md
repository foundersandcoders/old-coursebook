# Know the structure of a HTML document

## What is HTML?

HTML is how computers speak to each other over the internet. Websites or the DOM interprets what they say.

HTML is "spoken" by two computers:

* The Client - which is used by the person surfing the net

* The Server - which stores and distributes websites over the net

## Doctype declaration

If we open a webpage and view the “source code” (Command + Alt + U) the top of the page will have the doctype declaration.

It’s good HTML grammar to have this at the top because we should specify what html we are using

<!DOCTYPE html> means “this page is written in HTML5”

## Html tag

This is our first “tag”.

With a couple of exceptions, a “tag” has to be opened and closed. Tags are containers, for example everything between the opening html tag <html> and the closing html tag </html> conforms to the standards of the type of HTML dictated by the doctype declaration.

Everything between the opening tag and closing tag are inside that tag and therefore have the attributes that tag gives them.

Inside the <html> tag we have two important tags:
<head> tag and <body> tag

## The head tag

Web sites have two audiences:
*	Humans
*	“spiders”, “bots” or “web crawlers”

#### The title tag

The contents of the head tag displays little to humans, but it’s important to the bots. The single most important thing you can do for SEO is write a good title tag.

![title](http://www.html-5-tutorial.com/images/title-tag-in-search-results.gif)

The other tag that go in the head tag is the meta tag, there are two types:

* The meta charset tag
* The meta description tag

The meta charset tag ``<meta charset=“utf-8”>``

Tells you what language your page is written in, use the meta tag above if you are writing your page in english.

The description meta tag ``<meta name=“description” content=“The head tag contains the title and meta tags”>``

Gives a description of the webpage.

Note the meta tags do not need closing in HTML5.

## The body tag

The body tag contains the code that generates what is seen in the browser.

## Heading tag

They consist of `<h1>` through to `<h6>` with `<h1>` the largest tag. What you have put in your heading tags is also important in SEO.

Google ranks "relevancy" in a number of ways. Heading tags are one of the ways taken into consideration. It assumes the contents of the `<h1>` tags are more important than `<h2>` tags.

## Other tags

#### Paragraph tags

The paragraph `<p>` tag is probably the handiest and most commonly used tag.

#### List tags

We have next the List tags `<ul>`, `<ol>` and `<li>`

#### Definition list tag

We have the definition list tags `<dl>`. They work in a similar way to `<li>` tags. It is good for formatting in these ways:

John Doe

&nbsp;&nbsp;&nbsp;123 Main St.

Question?

&nbsp;&nbsp;&nbsp;Answer

#### Anchor tags

We have anchor tags. Hyperlinks, or links, are how you move around the web. An a or anchor tag is how you make hyperlinks in HTML. They look like this:

`<a href="http://www.html-5-tutorial.com/a-tag.htm">a tag</a>`

#### Table tags

Table tags

```
<table>
 <tr>
  <td>Row 1 - Col 1</td>
  <td>Row 1 - Col 2</td>
 </tr>
 <tr>
  <td>Row 2 - Col 1</td>
  <td>Row 2 - Col 2</td>
 </tr>
</table>
```

#### Div tags

The `<div>` tag is a generic container for flow content that by itself does not represent anything. The `<div>` tag is the principle tool used to put pages together.

The following is an example of using `<div>` tags
```
<div class="outer-div">
  This div tag
    <div class="inner-div">
       contains this div tag.
    </div>
</div>
```

![](http://www.html-5-tutorial.com/images/layout.gif)

#### Nav tags

The `<nav>` tag is used when assigning a major navigation block

#### Article tags

The `<artcile>` tag is used for the main article of the document

```
<article>
  <h1>The article title</h1>
  <p>This is the contents of the article element.</p>
</article>
```

#### Footer tags

The last essential tag is the `<footer>` tag.

As a rule of thumb, most pages should have a `<header>`, `<nav>`, `<article>` and `<footer>` tag.

The footer `<footer>` could be used to complete what was left undone in the header and nav or act as some kind of broad navigation for the page.

## Further reading

* http://www.html-5-tutorial.com/

## Final comment

* add auto complete html to atom
