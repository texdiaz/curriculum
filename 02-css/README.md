# CSS

## 1. Intro

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
- **Value:** is how you want to change it.

Example: 

*index.html* 

```html
<p> Some random text </p>
```

*style.css* 
```css
p {
   color     : red;
   font-size : 16px;
}
```

##### 1.2. How to tie CSS into HTML

There are two main different ways to include CSS in your website.

1. **Inline styles**: put the styles into your HTML. 
You can do it with the tag `<style>`.

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
  
   You link the CSS file to your HTML through the tag `<link>`. This tag contains two attributes, one that says the type of file that is linked (`rel = "stylesheet"`) and another one saying where is the file (`href = "styles.css"`).
   
   Example:
   
   *index.html*
   
   ```html
    <!doctype html>
    <html lang="en">
    <head>
       <meta charset="utf-8">
       <title>Title</title>
       <link rel="stylesheet" href="styles.css">
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

## 2. Selectors

As was shown above, selectors can be used to change the appearance of an element. 

There are several types of selectors:

- The **label** of the HTML element: `<h1>, <p>, <ul>, <a>`… 

- **Class**. It is an attribute of the HTML element: `<p class= "example"`>

- **Id**. It is an attribute of the HTML element: `<p id= "example">`

- **Pseudo-classes**. It is used to define a special state of an element.

- There are [many others selectors](https://www.w3schools.com/cssref/css_selectors.asp).  


**a) Label of the HTML element**

We use the label of an HTML element as selector with care and in few occasions, since the styles that we apply to an element, such as a `<p>`, will be applied to all `<p>` of the page (if there is no other selector indicating the opposite).

````css
h1 {
  font-size: 32px;
}
````
**b) Class**

Classes are keywords that we attribute to HTML elements in order to group them by function or appearance.
Classes are useful when you have more than one element that shares the same style.
The way to indicate in CSS that it is a class is writing a `.` 

***index.html***

````html
<h1 class= "title-lg"> Título grande </h1>
````
***style.css***

````css
.title-lg {
font-size: 32px;
}
````

**c) Id**

Id is a keyword that we used as an identifier for a **single element**. We should not write more than one Id per page. 

Instead of `.` that we use for classes, to use an Id we write a `#` followed by the identifier.

***index.html***

````htmlà
<button type="button" id=”btn-cancel”>Cancel</button>
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
<h1 class= "title-lg"> Título grande </h1>
````
***style.css***

````css
.title-lg {
font-size: 32px;
}
.title-lg:hover {
  background-color: blue;
}
````

As we have seen above, selectors can be mixed and we can use tag, classes and id. In addition, **HTML Elements can have multiple classes**. To accomplish this, use the same class attribute and add a space in between the two class name values.

````html
<p class="txt-medium center">Some random text</p>
````

You can play with [this example of Adalab](https://codepen.io/oneeyedman/pen/gGNpaQ).

###### Exercise

In a [Codepen](https://codepen.io/pen/), create three buttons. When moving the mouse over the first button, the background color will be blue, the second button will be green and the third button will be yellow.


###### Practice

- Play with [CSS Dinner](http://flukeout.github.io/)
- [Khan Academy Quiz](https://www.khanacademy.org/computing/computer-programming/html-css/more-css-selectors/e/quiz--css-specificity-rules)

###### More info

- [The Difference Between ID and Class](https://css-tricks.com/the-difference-between-id-and-class/)

- [CSS Basic Properties](http://web.simmons.edu/~grabiner/comm244/weekthree/css-basic-properties.html)

- [CSS Properties Reference List](http://www.stylinwithcss.com/resources_css_properties.php)












/////////////////


Contenido elaborado con: 
- [Ada Developers Academy](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/css-intro.md#css-syntax-structure)