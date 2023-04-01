# estyle

SCSS responsive design pattern

---

<a href="https://www.npmjs.com/package/estyle">
    <img src="https://nodei.co/npm/estyle.png?mini=true"/>
</a>

[DEMO](https://varp.com/responsive-design)

---

## install

```js
npm install estyle
```

## Glossary

- [SCSS](#SCSS)
  - [Responsive Design](#responsive-design)
    - [Mobile First](#mobile-first)
    - [Desktop First](#desktop-first)
  - [children](#children)
  - [scrollbar](#scrollbar)

# SCSS

Add link to file:

```scss
@import "~estyle/index.scss";
```

## Responsive Design

Breaskpoints - the screen width values which usually defines different devices.

| Breaskpoint | Width  | Mobile First CSS                     | Desktop First CSS                    |
| ----------- | ------ | ------------------------------------ | ------------------------------------ |
| `sm`        | 640px  | `@media (min-width: 640px) { ... }`  | `@media (max-width: 640px) { ... }`  |
| `md`        | 768px  | `@media (min-width: 768px) { ... }`  | `@media (max-width: 768px) { ... }`  |
| `lg`        | 1024px | `@media (min-width: 1024px) { ... }` | `@media (max-width: 1024px) { ... }` |
| `xl`        | 1280px | `@media (min-width: 1280px) { ... }` | `@media (max-width: 1280px) { ... }` |
| `2xl`       | 640px  | `@media (min-width: 1536px) { ... }` | `@media (max-width: 1536px) { ... }` |

### Mobile First

Mobile first breakpoint system. Means that by default styles applyied to all screens, but when you set styles for `mf-lg` they will be applied to `lg`(1024px) screens or **above**.

| SCSS mixing  | Minimum width | CSS                                  |
| ------------ | ------------- | ------------------------------------ |
| `mf-sm`      | 640px         | `@media (min-width: 640px) { ... }`  |
| `mf-md`      | 768px         | `@media (min-width: 768px) { ... }`  |
| `mf-lg`      | 1024px        | `@media (min-width: 1024px) { ... }` |
| `mf-xl`      | 1280px        | `@media (min-width: 1280px) { ... }` |
| `mf-2xl`     | 1536px        | `@media (min-width: 1536px) { ... }` |
| `mf($value)` | custom        | `@media (min-width: $value) { ... }` |

Example:

```scss
.container {
  font-size: 12px;

  // when scrren is `lg` or more
  @include mf-lg {
    font-size: 16px;
  }

  // when scrren is `1500px` or more
  @include mf(1500px) {
    font-size: 16px;
  }
}
```

### Desktop First

Desktop first breakpoint system. Means that by default styles applyied to all screens, but when you set styles for `df-lg` they will be applied to `lg`(1024px) screens or **below**.

| SCSS mixing  | Maximum width | CSS                                  |
| ------------ | ------------- | ------------------------------------ |
| `df-sm`      | 640px         | `@media (max-width: 640px) { ... }`  |
| `df-md`      | 768px         | `@media (max-width: 768px) { ... }`  |
| `df-lg`      | 1024px        | `@media (max-width: 1024px) { ... }` |
| `df-xl`      | 1280px        | `@media (max-width: 1280px) { ... }` |
| `df-2xl`     | 1536px        | `@media (max-width: 1536px) { ... }` |
| `df($value)` | custom        | `@media (max-width: $value) { ... }` |

Example:

```scss
.container {
  font-size: 12px;

  // when scrren is `lg` or less
  @include df-lg {
    font-size: 16px;
  }

  // when scrren is `1500px` or less
  @include df(1500px) {
    font-size: 16px;
  }
}
```

## children

Adds styles to all children tags

```scss
.container {
  @include children {
    color: white;
    background-color: black;
  }
}
```

## scrollbar

Adds styles scrollbar

```scss
.container {
  @include scrollbar(
    // scrollbar width
    8px, 
    // track and thumb border radius
    3px, 
    // track color
    #F2F2F2, 
    // thumb color
    #E5E5E5,     
    // hover thumb color
    #D8D8D8
    );
}
```
