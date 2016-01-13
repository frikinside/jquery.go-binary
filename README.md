# Go Binary jQuery plugin

A simple plugin to randomize every letter of a text in a binary style

## Live Demo

<http://frikinside.github.io/jquery.go-binary/>

## Instalation

Include script after the include of jQuery library

```html
<script src="/path/to/jquery.go-binary.min.js"></script>
```

### npm
You can use npm for install the plugin
```npm
npm install go-binary
```

## Usage

```js
$("selector").goBinary();
```

### Basic Example
#### HTML
```html
<button id="go-binary">START GO-BINARY</button>
<div id="text">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam a efficitur est.
</div>
```
#### JS
```js
$(document).ready(function() {
    $("button#go-binary").click(function(){
        $("#text").goBinary();
    });
});
```

### Settings options
```js
$.fn.goBinary.defaults = {
    text: '', // text to be binaryzed instead nodes text
    stepsUntilFixed: 2, // how many steps are needed to fix a character
    sps: 25, // steps per second
    matchRE: /[^\s]/, // Wich characters are going to be binary
    mode: 'shuffle', // How write the text with 3 possible values ['shuffle','type','endless']
    callback: function(){}, // A callback function to be called when method finished executing
    spsFormulaBasedOnTextLength: '0' // A formula to add sps base on length of text. The word 'length' gets replaced with the text length, for example: 'length/2' it's a valid formula and adds half of the text length as sps, so with a base sps of 50 and a text length of 100, it would add another 50 sps, being 100 sps the final speed.
};
```
#### Set settings
```js
$("#text").goBinary(
    {
        text: 'This is the text to be binaryzed instead of the text content of the node with id = text.',
        stepsUntilFixed: 5,
        mode: 'type',
        callback: function(){ alert('FINISH!'); },
        spsFormulaBasedOnTextLength: 'length/10' 
    }
);
```

### Methods
- **stop**: Stop method to cancel the binary animation on endless mode.

#### Invoke methods
```js
$("#text").goBinary('stop');
```

## TO-DO
- Maybe adds more options for the endless mode and stopping the endless mode in more fashion ways.