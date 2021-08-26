# style-import

<a href="https://www.npmjs.com/package/style-import">
    <img src="https://nodei.co/npm/style-import.png?mini=true">
</a>

Common style patterns for SASS

## install

```js
npm install style-import
```

## SCSS

Include link to file:

```scss
@import "~style-import/index.scss";
```

### children

Adds styles to all children tags

```scss
.container {
    @include children {
        color: white;
        background-color: black;
    };
}
```

### row-space

Adds spacing between children rows

```scss
.container {
    @include row-space(10px);
}
```
### col-space

Adds spacing between children columns

```scss
.container {
    @include col-space(10px);
}
```

### mobile

Adds styles when media query detect mobile

```scss
.container {
    font-size: 12px;

    // $max-width: optional value, default is 800px. 
    @include mobile($max-width) {
        font-size: 16px;
    }
}
```

### tablet

Adds styles when media query detect tablet

```scss
.container {
    font-size: 12px;

    // $max-width: optional value, default is 1000px. 
    @include tablet($max-width) {
        font-size: 16px;
    }
}
```

