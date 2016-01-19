## `display` property

`display` property is CSS's most important property for controlling layout.

#### What?
The `display` property specifies if/how an element is displayed.

Every HTML element has a default `display` value depending on what type of element it is. The default `display` value for most elements is block or inline.

#### Example

```css
p {
  display: inline;
}
```

|Property Values
| --------------------------------------------------------------------------------|
|`inline` Default value. Displays an element as an inline element (like `<span>`)
|`block`	Displays an element as a block element (like `<p>`)
| `flex`	Displays an element as an block-level flex container.
| `inline-block`	Displays an element as an inline-level block container.
| `inline-flex`	Displays an element as an inline-level flex container.
| `inline-table`	The element is displayed as an inline-level table
| `list-item`	Let the element behave like a `<li>` element
| `run-in`	Displays an element as either block or inline, depending on context
| `table`	Let the element behave like a `<table>` element
| `table-caption`	Let the element behave like a `<caption>` element
| `table-column-group`	Let the element behave like a `<colgroup>` element
| `table-header-group`	Let the element behave like a `<thead>` element
| `table-footer-group`	Let the element behave like a `<tfoot>` element
| `table-row-group`	Let the element behave like a `<tbody>` element
| `table-cell`	Let the element behave like a `<td>` element
| `table-column`	Let the element behave like a `<col>` element
| `table-row`	Let the element behave like a `<tr>` element
| `none`	The element will not be displayed at all (has no effect on layout)
| `initial`	Sets this property to its default value. Read about initial
| `inherit`	Inherits this property from its parent element. Read about inherit

***

#### Further reading

[w3 Properties](https://www.w3.org/wiki/CSS/Properties/display)

[w3schools](http://www.w3schools.com/css/css_display_visibility.asp)

[learnlayout](http://learnlayout.com/display.html)
