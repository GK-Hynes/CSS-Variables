# [CSS Variables](https://gk-hynes.github.io/css-variables/)

A page to play with manipulating CSS variables using JavaScript. Built for Wes Bos' [JavaScript 30](https://javascript30.com/) course.

[![Screenshot of CSS Variables page](https://screenshots.firefoxusercontent.com/images/baef2d16-7954-4f92-a092-fde4a3230bd0.png)](https://gk-hynes.github.io/css-variables/)

## Notes

CSS variables can be updated on thr fly with JavaScript. 

CSS variables are declared on an element or root. 

``` css
:root {
--base: #ffc600;
--spacing: 10px;
--blur: 10px;
}
```

To use a CSS variable use ```var(--variable-name)```

``` css
img {
    padding: var(--spacing);
}
```

```document.querySelector()``` returns a node list, not an array. 

A node list has far fewer methods. It does, however, have ```forEach()```.

The spacing and blur variables have suffixes. Use data-attributes to handle this: ```data-sizing="px"```.

``` javascript
const suffix =  this.dataSet.sizing || "";
```

```dataSet``` is an object that will contain all of the data attributes from that specific element. 

Update the variables by selecting the entire document and setting a property of base, spacing, and blur. 

Then update the value inside ```handleUpdate()```: 

``` javascript
document.documentElement.style.setProperty(`${this.name}`, this.value + suffix);
```

When you use a CSS variable you can update that variable on any element and any selectors inside of the element  which reference that variable will be updated. 