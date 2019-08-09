# Observable - JavaScript mutual conversion

## Observable -> JavaScript

#### add declaration keywords

```js
height = 800
```

to:

```
const height = 800
```

#### block statements in brace adjustment

```js
color = {
  const scale = d3.scaleOrdinal(d3.schemeCategory10);
  return d => scale(d.group);
}
```

to:

```js
const scale = d3.scaleOrdinal(d3.schemeCategory10);
const color = d => scale(d.group);
```

or with closure:

```js
color = (() => {
  const scale = d3.scaleOrdinal(d3.schemeCategory10);
  return d => scale(d.group);
})()
```


#### add build-in values

width is a build-in value in Observable, in JavaScript, we need to manually create it:

```js
const width = 800;
```

#### DOM element manually mount

In Observable, the DOM variable shows automatically. Like:

```js
chart = {
    ...
    return svg.node();
}
```

but in JavaScript, we need manully mount this DOM node to our DOM, like:

```js
chart = svg.node();
document.querySelector('body').appendChild(chart);
```

## JavaScript -> Observable


#### remove declaration keywords

remove `var`, `let`, `const`

#### single value return

put mutiple statement into brances and at the end return one value

```js
const scale = d3.scaleOrdinal(d3.schemeCategory10);
const color = d => scale(d.group);
```

to:

```js
color = {
  const scale = d3.scaleOrdinal(d3.schemeCategory10);
  return d => scale(d.group);
}
```


#### code split

if multiple value are needed, split them into individual cells, it usually happens when you declare and assign multiple values:

```js
const A = 1;
const B = "Hello";
```

to:

```js
A = 1;
```
```js
B = Hello;
```

#### remove width declaration

delete width declaration statement

#### return DOM node instead of mount to document

```js
chart = svg.node();
document.querySelector('body').appendChild(chart);
```

```js
chart = {
    ...
    return svg.node();
}
```