<h1 align="center">
  <br>
   <img src="https://openclipart.org/image/480px/svg_to_png/287053/1505709521.png&disposition=attachment" alt="Logo ArrayMixer" title="Logo ArrayMixer by  cliparteles ( https://openclipart.org/user-detail/cliparteles )" />
  <br>
</h1>
<p align="center">  
<a href="https://www.codacy.com/app/josetelesmaciel/array-mixer?utm_source=github.com&utm_medium=referral&utm_content=teles/array-mixer&utm_campaign=badger"><img src="https://api.codacy.com/project/badge/Grade/2cbd62dd3c284ce79f6e2c35817bec12"></a>
<a href="https://www.codacy.com/app/josetelesmaciel/array-mixer?utm_source=github.com&utm_medium=referral&utm_content=teles/array-mixer&utm_campaign=Badge_Coverage"><img src="https://api.codacy.com/project/badge/Coverage/8a941e0f57c047c8a481f4854666b42d"></a>
<a href="https://travis-ci.org/teles/array-mixer"><img src="https://travis-ci.org/teles/array-mixer.svg?branch=master"></a>
<a href="https://www.npmjs.com/package/array-mixer"><img src="https://img.shields.io/npm/v/array-mixer.svg"></a>
<a href="https://gitter.im/array-mixer/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge"><img src="https://badges.gitter.im/array-mixer/Lobby.svg"></a>
 <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
</p>

<p align="center">
  This repository contains the <strong>ArrayMixer</strong> source code.
  ArrayMixer is a tiny javascript lib with <strong>less than 1kb</strong> made to help ordering groups of arrays in a very personalized manner.
Powerful and easy to use.
</p>

## Table of contents

  * [Common usage](#common-usage)
  * [Installation](#installation)
     * [Node projects](#node-projects)
     * [Web projects](#web-projects)
  * [Parameters](#parameters)
     * [Aliases](#aliases)
     * [Sequence](#sequence)
  * [Examples](#examples)
     * [Example 1) For every 7 photos display an ad:](#example-1-for-every-7-photos-display-an-ad)
     * [Example 2) For every 4 paragraphs of text include 2 images:](#example-2-for-every-4-paragraphs-of-text-include-2-images)
  * [Contributing](#contributing)
  * [License](#license)
  * [Special thanks](#special-thanks)

## Common usage

Let's think we have two arrays:  **photos** and **ads**.

```javascript
photos.length === 12; // true
ads.length === 6; // true
```

Use `ArrayMixer` to create a new array containing **2 photos** followed by **1 ad** until the end of both arrays.


```javascript
let mixedArray = ArrayMixer({P:photos, A:ads}, ["2P", "1A"]);
```

So `mixedArray` will contain:

<table>
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[0]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[1]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[0]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[2]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[3]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[1]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[4]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[5]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[2]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[6]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[7]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[3]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[8]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[9]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[4]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[10]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=P[11]" align="left" vspace="10">
  <img src="https://via.placeholder.com/78x78.png/3498db/fff?text=A[5]" align="left" vspace="10">
</table>

<h2 id="installation">Installation</h2>

`ArrayMixer` can be used in node projects and web projects.

### Node projects

Requires node version **5.7 or later**.

```bash
npm install array-mixer --save
```

Import it to your code using:

```javascript
const ArrayMixer = require("array-mixer");
```

### Web projects

[Download latest ES5 transpiled version from unpkg.com](https://unpkg.com/array-mixer@0.7.2/release/array-mixer.js).

Import *ES5* transpiled version to your code.

```html
<script src="https://unpkg.com/array-mixer@0.7.2/release/array-mixer.js"></script>
```

## Parameters

<img src="https://via.placeholder.com/100x48.png/c0392b/fff?text=Aliases" align="left">
<img src="https://via.placeholder.com/115x48.png/3498db/fff?text=Sequence">

`ArrayMixer` has only two mandatory parameters.

```javascript
let aliases = {M:myArray, O:otherArray};
let sequence = ["3M", "5O"];

let mixed = ArrayMixer(aliases, sequence);
```


### Aliases

This parameter **should be** an object with keys used as alias for sequence and key values pointing to avaliable arrays.


### Sequence

This parameters uses the aliases defined on **aliases** parameter to create a sequence order to display the arrays.

## Examples

`ArrayMixer` can be used combining different arrays, aliases and sequences.
The following examples shows some ways to use it.

### Example 1) For every 7 photos display an ad:

```javascript
ArrayMixer({F: Photos, A: Ads}, ["7P", "1A"]);
```
**or** (as number 1 on sequence can be ommited):

```javascript
ArrayMixer({F: Photos, A: Ads}, ["7P", "A"]);
```


You can manipulate more than two vectors at a time, as in the following example:
 
### Example 6) View photos of puppies, kittens and penguins in sequence:

```javascript
let mixed = ArrayMixer({puppies, kittens, penguins}, ["puppies", "kittens", "penguins"));
```

| `puppies`               | `kittens`               | `penguins`                          | `mixed` |
|-----------------------|-----------------------|-----------------------------------|------------------------------------------------------------------------------|
| [:dog:, :dog:, :dog:] | [:cat:, :cat:, :cat:] | [:penguin:, :penguin:, :penguin:] | [:dog:, :cat:, :penguin:, :dog:, :cat:, :penguin:, :dog:, :cat:, :penguin:] |

### Example 7) Include 1 large photo for every 2 medium size photos followed by 3 small photos:

**Tip:** `ArrayMixer` lets you mix three or more arrays at once.

```javascript 
ArrayMixer({L:large, M:medium, S:small}, ["2M", "3S", "L"]);
```
<table>
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[0]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[1]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[0]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[1]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[2]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/27ae60/fff?text=L[0]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[2]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[3]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[3]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[4]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[5]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/27ae60/fff?text=L[1]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[4]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/3498db/fff?text=M[4]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[6]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[7]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/c0392b/fff?text=S[8]" align="left" vspace="10">
<img src="https://via.placeholder.com/78x78.png/27ae60/fff?text=L[2]" align="left" vspace="10">
</table>

> **Disclaimer**: All arrays mentioned in this section must exist for the examples to work.

### More examples

For more example please check the [specification file](src/spec.js).

## Contributing

You may contribute in several ways like creating new features, fixing bugs, improving documentation and examples
or translating any document here to your language. [Find more information in CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE) - Jota Teles - 2017

## Special thanks

* [Willian Ribeiro](https://github.com/willianribeiro);
* [João Paulo](https://github.com/jpusp);