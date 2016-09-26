# sneakers.js ![Bower Version](https://badge.fury.io/bo/sneakers.svg) [![Powered by You](http://sapegin.github.io/powered-by-you/badge.svg)](http://sapegin.github.io/powered-by-you/)

<!--
[![Build Status](https://secure.travis-ci.org/mar10/sneakers.js.svg?branch=master)](https://travis-ci.org/mar10/sneakers.js) 
-->
> JavaScript plugin that simulates tty typing and decryption effect as seen in the 
1992 movie [Sneakers](https://youtu.be/F5bAa6gFvLs).

Inspired by Brian Barto's [no-more-secrets](https://github.com/bartobri/no-more-secrets) tool.

Copyright &copy; 2016 Martin Wendt.
License: MIT.

Click here for a [demo](https://rawgit.com/mar10/sneakers.js/master/demo/index.html):

[![Demo](demo/console.png)](https://rawgit.com/mar10/sneakers.js/master/demo/index.html)


### Usage

Include `sneakers.js` and start the effect 
```js
	$(".sneakers").sneakers({
		lockSize: true,  // lock current element size before removing content
		done: function() {
			alert("done");
		}
	});
```

this will remove the content of the target element, then 'type' it in in an 'encrypted'
version, and then 'decrypt' the text:
```html
<p class="sneakers">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas gravida neque sem, in ultrices nunc eleifend at. In quis nibh nunc. Aliquam erat volutpat. Ut ac congue nunc. Proin vitae ante vel metus sodales aliquet. Phasellus volutpat nisi ligula, in laoreet leo aliquam non. Mauris urna turpis, rutrum sed dolor nec, porttitor pretium enim.
</p>
```


### API

Following all options with their defaults:

```js
	$(".sneakers").sneakers({
		typeMs: 5,        // milliseconds per character (0: show immediately)
		decodeMs: 50,     // milliseconds per update
		maxDecode: 1000,  // decode the rest after max. updates
		stopEps: 0.05,    // decode the rest if less than 5% are encrypted
		lockSize: false,  // lock current element size before removing content
		// Events:
		start: $.noop,    // Current text was replaced by encrypted text 
		type: $.noop,     // 'Encrypted' text has been typed to screen
		done: $.noop      // Decrypted text is completely displayed
	});
```
