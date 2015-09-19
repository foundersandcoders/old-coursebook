###The CSS box model

All HTML elements can be considered as boxes. In CSS, the term "box model" is used when talking about design and layout.

The CSS box model is essentially a box that wraps around HTML elements, and it consists of: **margins, borders, padding, and the actual content**.

The box model allows us to add a border around elements, and to define space between elements.

The image below illustrates the box model:

![The image illustrates the box model](http://www.w3schools.com/css/box-model.gif)


#####Explanation of the different parts:

* **Content** - The content of the box, where text and images appear
* **Padding** - Clears an area around the content. The padding is transparent
* **Border** - A border that goes around the padding and content
* **Margin** - Clears an area outside the border. The margin is transparent

>Example:  

>div {  
width: 300px;  
padding: 25px;  
border: 25px solid navy;  
margin: 25px;    
}

In order to set the width and height of an element correctly in all browsers, you need to know how the box model works.

When you set the width and height properties of an element with CSS, you just set the width and height of the content area. **To calculate the full size of an element, you must also add padding, borders and margins.**  


**Total element width** = width + left padding + right padding + left border + right border + left margin + right margin

**Total element height** = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin
