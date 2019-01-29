# CSS


1. [Intro](#intro)
    1. Syntax Structure
    2. How to tie CSS into HTML
    
2. [Selectors](#selectors): label, class, id, pseudo-classes

3. [Layout and position](#layout)
   1. Box Model
   2. Display property
   3. Position property
   4. Intro to flexbox

4. [Cascade](#cascade)

5. [DevTools](#devtools)

## <a name="intro"></a> 1. Intro

CSS stands for **Cascading Style Sheets** and it describes how HTML elements are to be displayed on screen. It is used to describe the presentation of Web pages -including colors, layout, and fonts- and to adapt the view to different types of devices, as explained in [w3C](https://www.w3schools.com/css/css_intro.asp).

##### 1.1. [Syntax Structure](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/css-intro.md#css-syntax-structure)

```css
selector {
  property : value;
  property : value;
}
```

- **Selector:** what you want to change. It refers to an HTML element. 
Within the brackets it is written the CSS attributes: property and value.
- **Property:** what part you want to change.
- **Value:** how you want to change it.

Example: 

*index.html* 

```html
<p> Random text </p>
```

*style.css* 
```css
p {
  color : red;
  font-size : 16px;
}
```

##### 1.2. How to tie CSS into HTML

There are two main different ways to include CSS in your website:

1. **Inline styles**. When using the style attribute in HTML elements. 
That is, using the tag `<style>` inside the `<head>` section.

    ```html
    <!doctype html>
    <html lang="en">
    <head>
       <meta charset="utf-8">
       <title>Title</title>
       <style>
           h1 {
             color: red;
             font-size: 16px;
           }
       </style>
    </head>
    <body>
       <h1>Title</h1>
    </body>
    </html>
    ```
    However, **we are not going to use these inline styles** because it is a practice not recommended. Instead, we are only going to use external style sheets. 

2. **External style sheet**. The web best practices requires separate the content of the presentation. It is recommended to separate the CSS styles in an external file because it helps avoid duplication, makes maintenance easier and allows you to make a site-wide change in one place.
  
   Link the CSS file to your HTML through the tag `<link>`. This tag contains two attributes, one that says the type of file that is linked (`rel = "stylesheet"`) and another one saying where is the file (`href = "styles.css"`).
   
   Example:
   
   *index.html*
   
   ```html
    <!doctype html>
    <html lang="en">
    <head>
       <meta charset="utf-8">
       <title>Title</title>
       <link rel="stylesheet" href="style.css">
    </head>
    <body>
       <h1>Title</h1>
    </body>
    </html>
   ```

    *style.css*

    ````css
    h1 {
      color: blue;
      font-family: Arial, sans-serif;
      font-size: 20px;
    }
    ````

## <a name="selectors"></a> 2. Selectors

As was shown above, selectors can be used to change the appearance of an HTML element. 

There are several types of selectors:

- The **label** of the HTML element: `<h1>, <p>, <ul>, <a>`… 

- **Class**. It is an attribute of the HTML element: `<p class= "example"`>

- **Id**. It is an attribute of the HTML element: `<p id= "example">`

- **Pseudo-classes**. It is used to define a special state of an element.

- There are [many others selectors](https://www.w3schools.com/cssref/css_selectors.asp).  


**a) Label of the HTML element**

It should be used with caution and rarely, since the styles that we apply to an element, such as a `<p>`, will be applied to all `<p>` of the page (if there is no other selector indicating the opposite).

````css
p {
 font-size : 32px;
}
````
**b) Class**

Classes are keywords that we attribute to HTML elements in order to group them by function or appearance.
Classes are useful when you have more than one element that shares the same style.
The way to indicate in CSS that it is a class is writing a `.` 

***index.html***

````html
<h1 class="title-lg"> Title </h1>
````
***style.css***

````css
.title-lg {
  font-size : 32px;
}
````

**c) Id**

Id is a keyword that we used as an identifier for a **single element**. We should not write more than one Id per page. 

Instead of `.` that we use for classes, to use an Id we write a `#` followed by the identifier.

***index.html***

````html
<button type="button" id="btn-cancel">Cancel</button>
````
***style.css***

````css
#btn-cancel {
  background-color : red;
}
````

**d) Pseudo-classes**

A CSS pseudo-class is a keyword added to selectors that specifies a special state of the element to be selected.
The symbol for pseudo clases is `:` . 

The most used is the **hover** state, which is when we place the mouse on top of the element.

***index.html***

````html
<h1 class= "title-lg"> Title </h1>
````
***style.css***

````css
.title-lg {
  font-size : 32px;
}
.title-lg:hover {
  background-color : blue;
}
````

As we have seen above, selectors can be mixed and we can use tag, 
classes and Ids. In addition, **HTML elements can have multiple classes**. To accomplish this, use the same class attribute and add a space in between the two class name values.

````html
<p class="txt-medium center">Random text</p>
````

You can play with [Adalab ´s example in Codepen](https://codepen.io/oneeyedman/pen/gGNpaQ).

###### Exercise

In a [Codepen](https://codepen.io/pen/), create three buttons. When moving the mouse over the first button, the background color will be blue, the second button will be green and the third button will be yellow.


###### Practice

- Play with [CSS Dinner](http://flukeout.github.io/)
- [Khan Academy Quiz](https://www.khanacademy.org/computing/computer-programming/html-css/more-css-selectors/e/quiz--css-specificity-rules)

###### More info

- [The Difference Between ID and Class](https://css-tricks.com/the-difference-between-id-and-class/)

- [CSS Basic Properties](http://web.simmons.edu/~grabiner/comm244/weekthree/css-basic-properties.html)

- [CSS Properties Reference List](http://www.stylinwithcss.com/resources_css_properties.php)


## <a name="layout"></a> 3. Layout and Position


#### 3.1. Box Model

> All HTML elements can be considered as boxes. The CSS box model is essentially a box that wraps around every HTML element. 
It consists of: margins, borders, padding, and the actual content. ([w3Schools]( https://www.w3schools.com/css/css_boxmodel.asp)).

A web page is like a set of boxes one inside another. If we think of each element as a rectangle it will be much easier to visualize how the structure of a web is composed. 

The core of the box is defined by the **width** and **height** of an element. 
**Padding** and then **border** expand the dimensions of the box. 
In addition, any **margin** we have specified will follow the border. 

![MDN Image Model Box](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)
[Source Image: MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model)

For example, to calculate the height of an element, use this formula:

`margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom`

Some programmers prefer not to think about these rules and use the [box-sizing property](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing). The value **border-box** includes padding and border in the element's total width and height.

````css
.container {
  box-sizing : border-box;
}
````
###### More info

- [Opening the Box Model](https://learn.shayhowe.com/html-css/opening-the-box-model/)

- [Difference between margin and padding](https://stackoverflow.com/questions/5958699/difference-between-margin-and-padding/50060282)


#### 3.2. Display Property

`display` property defines how will an HTML element be displayed, how will it be placed on the page and how will the rest of the elements be placed in relation to the element. 
Browsers automatically assign a default display mode to all HTML elements, but through CSS we can change its appearance. 

- **Display block**

> Displays an element as a block element (like `<p>`). 
It starts on a new line, and takes up the whole width ([w3schools](https://www.w3schools.com/cssref/pr_class_display.asp)).

````css
.block {
  display : block;
}
````
There are certain elements that are displayed by default as a block element. For example: 
`<p>, <div>, <fieldset>, <footer>, <form>, <h1>, <header>, <hr>, <li>, <main>, <nav>, <ol>, <ul>, <section>, <table>`. 

You can play with [Adalab ´s Codepen](https://codepen.io/adalab/pen/WXQgrq).

- **Display inline**
> Displays an element as an inline element (like `<span>`). 
Any height and width properties will have no effect.

````css
.inline {
  display : inline;
}
````

There are certain items that are displayed by default as an inline element. For example: 
`<a>, <strong>, <span>, <button>, <input>, <label>, <select>, <textarea>`.

You can play with [Adalab ´s Codepen](https://codepen.io/adalab/pen/vWNzLj).

- **Display inline-block**
> Displays an element as an inline-level block container. The element itself is formatted as an inline element, but you can apply height and width values.

````css
.inline-block {
  display : inline-block;
}
````
You can play with [Adalab ´s Codepen](https://codepen.io/adalab/pen/KydxdP).

- **Display none**

The element is completely removed.

```css
.hidden {
  display : none;
}
```
You can play with [Adalab ´s Codepen](https://codepen.io/adalab/pen/GOpXmw).

###### Exercise

With this [Adalab ´s Codepen](https://codepen.io/adalab/pen/QOjVye):

- Use the `<mark>` tag within several paragraphs and explain what it is for and how it works.
- Within a paragraph of text include a 100x100 image and explain how the content is distributed.
- Between two paragraphs add a 200x200 image and explain how the content is distributed.
- Use the none property to remove any element. 


#### 3.3. Position Property

> The position property specifies the type of positioning method used for an element
 (static, relative, fixed, absolute or sticky) ([w3schools](https://www.w3schools.com/css/css_positioning.asp)).

- **static**. The default value.
- **relative**. An element’s new position relative to its normal position. 
- **absolute**. The element is positioned relative to its first positioned ancestor element. 
- **fixed**. It is similar to absolute, but it is only relative to the `<html>` document, that is, the element is positioned relative to the browser window.

###### More info

- [Video to understand position property](https://www.youtube.com/watch?v=kowh52NmZis)
- [How to use the position property in CSS to align elements](https://medium.freecodecamp.org/how-to-use-the-position-property-in-css-to-align-elements-d8f49c403a26)

#### 3.4. Intro to Flexbox

Flexbox is a layout model to positionate HTML elements in a web page.
Historically, aligning items while working with page flow using CSS 
has been difficult. Flexbox helps you place easily the components of your web.

In flexbox, the HTML elements move through an imaginary container. 
This container has two axes: **main axis** and **cross axis**. This is crucial because the axes will determinate how the item moves and which properties of flex you should use.

![Flexbox container](https://cyphertree.com/wp-content/uploads/2018/05/Screen-Shot-2018-05-03-at-10.46.54-AM-e1525440405230.png)
[Source Cyphertree](https://cyphertree.com). 

The different properties of Flexbox can be divided in two groups: 
the properties for the Parent (the container element) and the properties for the Children (flex items). 
Let's see the most important properties. If you want to see more properties, you can check this [link](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).


##### Parent Properties

- **display**

To start using the Flexbox model, the first thing to do is set the display property in 
the container.

````css
.flex-container {
   display: flex; 
}
````

- **direction**

The main axis is defined by flex-direction. We have two main possibilities values: 
`row` and `column`. Choose `row` to put the main axis as a row, in the inline direction. 
Choose `column` to put the main axis as a column, in the block direction. 

[Example in Codepen](https://codepen.io/anon/pen/mqomXp)

- **wrap**

The default behaviour of the child elements expands on all the row whatever 
the number are. The `flex-wrap` CSS property sets whether flex items are forced
onto one line or can wrap onto multiple lines. If wrapping is allowed, 
it sets the direction that lines are stacked.

[Example in Codepen](https://codepen.io/anon/pen/yPwbKd)

- **justify content**

It is used to align the items on the main axis, the direction in which flex-direction 
has set the flow. This properties offers several values: 
`flex-start, flex-end, space-between`…

[Example in Codepen](https://codepen.io/anon/pen/jaJmxR)

- **align items**

The align-items property will align the items on the cross axis. 
It has several values: `flex-start, flex-end, center`…

[Example in Codepen](https://codepen.io/anon/pen/RjdVBx)


##### Children Properties

- **align self**

We use this property when we want to place a children element in a particular position, 
different than their 'brothers'. 
`Flex-start`, `flex-end` and `center` place the element at the begin,
 at the end and at the middle position of the row or column.
 
- **order**

With this property, we can change the order of the child elements, 
writing an integer that means the order that the element should appear. 

[Example in Codepen](https://codepen.io/anon/pen/yPZGyp)

###### Practice

- [Flexbox Froggy](http://flexboxfroggy.com)

###### More info

- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Visual support](https://codepen.io/enxaneta/full/adLPwv)

## <a name="cascade"></a> 4. Understanding Cascade


Several selectors are sometimes applied to the same element. 
The [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
is an algorithm that defines how to combine property values.

There are three main rules:

- **Importance**. An `!important` rule works like this:

*style.css* 
````css
h2 {
  color : blue !important;
}

.title {
  color : green;
}
````
*index.html* 
````html
<h2 class="title">This text will be blue</h2>
````

On very rare occasions we will use `!important`. You might want to read the [implications of using !importance](https://stackoverflow.com/questions/3706819/what-are-the-implications-of-using-important-in-css).

- **Specificity**. The more specific a selector is, the more force they will have their rules over the others.

- **Order**. If several selectors have the same importance and specificity, 
the styles that are at the end of the CSS file take precedence over the ones above. 
This happens because the CSS is 'read' from top to bottom.
 
###### Exercise

- [Specificity Practice Ada Developers Academy](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/exercises/specificity-practice.md)

###### More info

- [CSS Specificity: Things You Should Know](https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/)

- [CSS Specificity Wars](https://stuffandnonsense.co.uk/archives/css_specificity_wars.html)


* * *

## References 
- [Ada Developers Academy](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/css-intro.md#css-syntax-structure)
- [Curso programación front end Adalab](https://books.adalab.es/curso-programacion-front-end-2018/)