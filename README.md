# skrollTop.js

**A library that creates scrolling effects for your website.**


## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Development](#development)
- [License](#license)

## Installation

``` bash
npm install skrollTop
```

or if you prefer CDN

``` html
<script type="text/javascript" src="https://nguyenthanh1995.github.io/lib/skrollTop.min.js"></script>
```

## Usage

### Global

You may install skrollTop globally:

``` html
<script type="text/javascript" src="https://nguyenthanh1995.github.io/lib/skrollTop.min.js"></script>
<script>
skrollTop.init({
   el: ".skrollTop"
})
</script>
```
This makes it possible to use the built-in DOM settings for skrollTop such as data-on or data-duration.
### Local

skrollTop allows you to ignore the logic of the JavaScript you can configure in html, but you can also configure the global configuration when init.
``` js
skrollTop.init({
   event: "click touchend",
   duration: 1000
})
```
If you pass an parameter undefined skrollTop will understand that you want it to use the default settings.
### Configuration
| Property                    | Type    | Default | Description                                                                                                                                                                                                                                                                           |
|:----------------------------|:--------|:--------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| event                       | String  | "click" | You can list events to trigger scrolling effects separated by " " |
| goto                        | String, Object, Number | <no default> | You must pass the parameter here is a css selector to an element, element or a number to determine the position to scroll to. |
| duration                    | Number, String | 600 | This determines the time at which the effect will take place in ms |
| type                        | String | "easeInOutCubic" | The effect name you want to skrollTop will work (linear, easeInQuad, easeOutQuad, easeInOutQuad, easeInCubic, easeOutCubic, easeInOutCubic, easeInQuart, easeOutQuart, easeInOutQuart, easeInQuint, easeOutQuint, easeInOutQuint) |
| onScroll                    | Function | nothing | After the effect finishes this function will be called. |

### DOM
| Property                    | Type    | Default | Description                                                                                                                                                                                                                                                                           |
|:----------------------------|:--------|:--------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| data-on                          | String  | "click" | You can list events to trigger scrolling effects separated by " " |
| data-goto                        | String, Object, Number | <no default> | You must pass the parameter here is a css selector to an element, element or a number to determine the position to scroll to. |
| data-duration                    | Number, String | 600 | This determines the time at which the effect will take place in ms |
| data-type                        | String | "easeInOutCubic" | The effect name you want to skrollTop will work (linear, easeInQuad, easeOutQuad, easeInOutQuad, easeInCubic, easeOutCubic, easeInOutCubic, easeInQuart, easeOutQuart, easeInOutQuart, easeInQuint, easeOutQuint, easeInOutQuint) |

If you install on both JS and HTML, the settings on JS will take precedence.

### HTML Structure

It's easy you don't need to care about logic with skrollTop:

``` html
  <ul class="list-group">
    <li class="list-group-item"> <a href="#home" data-duration="1000" data-type="linear" class="skrollTop"> Home </a> </li>
    <li class="list-group-item"> <a href="#active" data-duration="1000" data-type="easeInCubic" class="skrollTop"> Active </a> </li>
    <li class="list-group-item"> <a href="#contact" data-duration="1000" class="skrollTop"> Contact </a> </li>
    <li class="list-group-item"> <a href="#about" data-duration="1000" class="skrollTop"> About </a> </li>
    <li class="list-group-item"> <a href="javascript:void(0)" data-goto="0" data-duration="1000" class="skrollTop"> Goto Top </a> </li>
  </ul>
```
When the dom load is finished, the default class skrollTop element will have an effect if you want to activate many other elements you can.

``` html
  <ul class="list-group">
    <li class="list-group-item"> <a href="#home" data-type="linear" class="skrollTop"> Home </a> </li>
    <li class="list-group-item"> <a href="#active" data-type="easeInCubic" class="skrollTop"> Active </a> </li>
    <li class="list-group-item"> <a href="#contact" class="skrollTop"> Contact </a> </li>
    <li class="list-group-item"> <a href="#about" class="skrollTop"> About </a> </li>
    <li class="list-group-item"> <a href="0" class="skrollTop"> Goto Top </a> </li>
  </ul>
```

``` js
skrollTop.init({
  el: "ul > li > a",
  duration: 1000
})
// so compact
```
or activate only a single object
```
<button class="scroll"> Goto 0 </button>
```

``` js
  new skrollTop(".scroll").attack(undefiend, 0, 1000, undefined, function () {
     console.log("scroll")
  })
  // arguments = [event, goto, duration, type, callback)
```

## More

| Property | Description |
|:---------|:------------|
| on       | Attach events to the object skrollTop.on([..element], [..name event], [..function]) |
| off      | Dittach events to the object skrollTop.on([..element], [..name event], [..function]) |
| query    | Document.querySelectorAll |
| getOffset | Returns the object containing the element position |
| attr     | This function works on the attribute if you do not pass the third argument it will return attr skrollTop.attr([..el], [..key], [..value]) |
| isNaN    | Check if it is NaN or not |
| isNumeric | Check if a string is a number or not |
| scrollTop | Scroll to the position you desire for parameters such as the .attack () function. |

## Development

A sandboxed dev environment is provided by [vue-play](https://github.com/vue-play/vue-play). Changes made to the component files will appear in real time in the sandbox.

To begin development, run:

``` bash
yarn install
yarn dev
```

then navigate to `http://localhost:5000`

To modify and add sandbox scenarios, edit `play/index.js`

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
