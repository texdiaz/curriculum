# HTML


1. [Intro](#intro)
    1. Syntax Structure
    
2. [Comments](#comments)

3. [Main Tags](#tags)

## <a name="intro"></a> 1. Intro

HTML stands for **HyperText Markup Language** and it is used to add and structure information 
we want in our webpage. It includes tags, attributes and flags that help structure content.  

HTML is the foundation for EVERY website. Its purpose is to organize content and every website uses it.

HTML is not concerned about how the content looks. That job is left to CSS.



##### 1.1. [Syntax Structure](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/05-html-css/css-intro.md#css-syntax-structure)

**HTML elements**

Every piece of website content is 'wrapped' in an HTML element. An HTML element is usually composed of two tags, an opening tag and a closing tag (though we will see there are exceptions). Content, such as text or other HTML elements, will be displayed within these tags.
`<p>Text</p>`
Opening tags can include modifiers, called **attributtes** that modify default behaviour of the element, or add
extra information.
In this case, the `lang` attribute in the `p` tag is telling information about the language of the text.
```html
<p lang="es">Párrafo</p>
```

**Nested Elements**
Tags can be nested inside of other tags. To maintain readable code, the parent tags (the outer most ones) should each be on a new line with the nested element indented. Example:
```html
<div>
  <h1>Title</h1>
  <p>Text</p>
</div>
```

**Self Closing Elements**
Some elements do not need a closing tag. Some examples are:
```html
  <br /> 
  <img />
  <link />
  <meta />
  ```

**Types of tags**
Tags can be defined in 2 types; tags that define the document and tags that define content.
1. Tags that define the document:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>My webpage</title>
</head>
<body>

</body>
</html>
```
The `<!DOCTYPE html>, <html>, <head>` and `<body>` tags  are fundamental for every webpage.
You can read more about these tags here: 
[doctype](https://stackoverflow.com/questions/414891/what-is-doctype)
[html](https://stackoverflow.com/questions/3270615/why-we-use-html-tag-although-my-website-runs-perfect-without-html-tag)
[head](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)
[body](https://htmldog.com/references/html/tags/body/)


2. Tags that define content:
Within the <body></body> tag we can include our content tags. 
Browsers will read tags respecting writing order, so we must place them in the order
we intend to. Moreover, the use of correct tags will give our content semantic value, useful for
developers and important for [accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA). 

Some important tags are:
- `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>` used for titles.
- `<p>` for adding text (paragraph).
- Disordered lists:
```html
  <ul>
    <li>List element</li>
    <li>List element</li>
  </ul>
```
- Ordered lists:
```html
  <ol>
    <li>List element</li>
    <li>List element</li>
  </ol>
```
- `<div> and <spans>` are containers.
- `<a href="http://madridforrefugees.org/es/">` The <a> tag defines a hyperlink, which is used to link from one page to another.
- `<header>`: una cacebera o sección de presentación de un bloque
-`<main>`: Indica la principal sección de contenido
- `<footer>`: un pie o sección final de un bloque
- `<nav>`: un bloque de navegación, para un menú.
- `<aside >`: un bloque de contenido de menor importancia o con contenido relacionado
- `<article>`: un artículo
And a lot of other tags which you can research [here](https://www.w3schools.com/tags/).


## <a name="Comments"></a> 2. Comments

In order to add a comment in html:
```html
<!--This is a comment. Comments are not displayed in the browser-->

<p>This is a paragraph.</p>
```


**Links**
Links are very used ways of redirecting users to another place in our website (relative routes)
or to an external webpage (absolute routes)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="utf-8">
    <title>My webpage</title>
</head>
<body>
    <header id="top">
        <h1>Title</h1>
    </header>
    <main id="main">
        <h2>Some awesome thing!</h2>
        <p>Cats are not as cute as dogs</p>
    </main>
    <footer>
        <div><a href="#top">Go to Top</a></div>
    </footer>
</body>
</html>
```


## <a name="tags"></a> 3. Main tags






###### Exercise



###### More info



* * *

## References 
- [Ada Developers Academy]
- [Curso programación front end Adalab](https://books.adalab.es/curso-programacion-front-end-2018/)