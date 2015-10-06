---
layout: post
title:  Testing different styles
date:   2015-05-03 10:30:00
---

First of all, let's have a glance at the basic styles:
**strong**, *italic*, <del>deletion</del>, <ins>insertion</ins>. Underscore also works as on [Github](https://help.github.com/articles/github-flavored-markdown/):

- in code: `test_, test_test, _test in italic_, test_test_test`
- in text: test_, test_test, _test in italic_, test_test_test

# Header 1

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

## Header 2

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

### Header 3

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

### Lists:

- list item 1
- list item 2
- list item 3

1. list item 1
2. list item 2
3. list item 3

### Blockquote:

> Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### [BASSCSS](http://www.basscss.com/) colors:

- <span class="black">black</span>
- <span class="gray">gray</span>
- <span class="silver">silver</span>
- <span class="white">white</span>
- <span class="aqua">aqua</span>
- <span class="blue">blue</span>
- <span class="navy">navy</span>
- <span class="teal">teal</span>
- <span class="green">green</span>
- <span class="olive">olive</span>
- <span class="lime">lime</span>
- <span class="yellow">yellow</span>
- <span class="orange">orange</span>
- <span class="red">red</span>
- <span class="fuchsia">fuchsia</span>
- <span class="purple">purple</span>
- <span class="maroon">maroon</span>

### Horizontal rule:

-----------------------

### Image:

![](/images/image.jpg)

### Tables:

Tables can be created using Markdown. The first table fits on screen:

| Name | Age | Fruit      |
|:-----|----:|:-----------|
| Alex | 22  | Apple      |
| Bran | 20  | Orange     |
| Mike | 21  | Watermelon |


If the table is wider than the screen, a scroll bar appears:

|x  |        y1|        y2|        y3|        y4|        y5|        y6|        y7|        y8|        y9|       y10|
|:--|---------:|---------:|---------:|---------:|---------:|---------:|---------:|---------:|---------:|---------:|
|A  | 0.0120322| 0.1604227| 0.0475750| 0.0195603| 0.6300875| 0.0988451| 0.7523581| 0.1064724| 0.9263830| 0.2172876|
|B  | 0.7866424| 0.8760143| 0.1726650| 0.1236457| 0.9585477| 0.2710412| 0.3114512| 0.0961548| 0.1499255| 0.5575171|
|C  | 0.4248450| 0.8750728| 0.3494551| 0.8178633| 0.3962382| 0.1846068| 0.8154139| 0.5149306| 0.5695919| 0.3242904|


### Code

Here are an ES6 code segment, in which `x => x * x` defines a function:

```javascript
// index.js
var arr = [1, 2, 3, 4, 5];
var b = arr.map(x => x * x);
console.log(b);
```
