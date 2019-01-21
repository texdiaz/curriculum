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



/////////////////


Contenido elaborado con: 
- [Ada Developers Academy](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/css-intro.md#css-syntax-structure)