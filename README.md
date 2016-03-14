# Replacing base markup

## Overview

Another property we can use is `replace` - let's look into that! You might've noticed that when our directives get inserted into the DOM the directive tag is still there. Replace can *replace* this DOM node!

## Objectives

- Describe "replace"
- Replace the base Directive with our template

## What is replace?

When we put our directive into the DOM, you'll notice that what will happen is this:

```html
<our-directive>
	<div>
		Directive contents here!
	</div>
</our-directive>
```

However, you may not want the `our-directive` HTML element to be there - you might prefer only semantic, proper DOM nodes to be in the DOM. It's completely your choice - there's no benefit to either way.

To get rid of this, we can set the replace property on our object to `true`.

```js
function OurDirective() {
	return {
		replace: true,
		template: '<div>Hello world!</div>'
	};
}

angular
	.module('app')
	.directive('ourDirective', OurDirective);
```

When this is rendered, we won't see `our-directive` in the HTML!