---
sidebar_position: 1
title: Random
comment: true
tags:
  - Javascript
  - 1loc
  - Random
---

## Generate a random integer in given range

```js title=Javascript
const randomInteger = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min;
```

```ts title=Typescipt
const randomInteger = (min: number, max: number): number =>
  Math.floor(Math.random() * (max - min + 1)) + min;
```

## Sort an object by its properties

```js title=Javascript
const sort = (obj) =>
  Object.keys(obj)
    .sort()
    .reduce((p, c) => ((p[c] = obj[c]), p), {});
```

```ts title=Example
const colors = {
  white: '#ffffff',
  black: '#000000',
  red: '#ff0000',
  green: '#008000',
  blue: '#0000ff',
};
sort(colors);
/*
{
    black: '#000000',
    blue: '#0000ff',
    green: '#008000',
    red: '#ff0000',
    white: '#ffffff',
}
*/
```

## Generate a random hex color

```js title=Javascript
const randomColor = () => `#${Math.random().toString(16).slice(2, 8).padEnd(6, '0')}`;

// Or
const randomColor = () => `#${(~~(Math.random() * (1 << 24))).toString(16)}`;
```

```ts title=Typescipt
const randomColor = (): string => `#${Math.random().toString(16).slice(2, 8).padEnd(6, '0')}`;

// Or
const randomColor = (): string => `#${(~~(Math.random() * (1 << 24))).toString(16)}`;
```

## Generate a random string from given characters

```js title=Javascript
const generateString = (length, chars) =>
  Array(length)
    .fill('')
    .map((v) => chars[Math.floor(Math.random() * chars.length)])
    .join('');
```

```ts title=Typescipt
const generateString = (length: number, chars: string) =>
  Array(length)
    .fill('')
    .map((v) => chars[Math.floor(Math.random() * chars.length)])
    .join('');
```

## Generate a random UUID

```js title=Javascript
const uuid = (a) =>
  a
    ? (a ^ ((Math.random() * 16) >> (a / 4))).toString(16)
    : ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, uuid);
```
