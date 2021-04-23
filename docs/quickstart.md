# Quickstart

## Adding `contextmenu.js` to your web project

### Import

Add the following to the `<head>` tag:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/ColonelParrot/contextmenu.js@latest/src/styles-v1.1.min.css"/>
<script src="https://cdn.jsdelivr.net/gh/ColonelParrot/contextmenu.js@main/src/script.min.js"></script>
```

### Setting up the contextmenu

The contextmenu should be a `ul` tag with the classes `context-menu-js` and `context-menu`. Example below:

```html
<ul class="context-menu-js context-menu">
	<li data-callsign="item-1">Context Menu Item #1</li>
	<li data-callsign="item-2">Context Menu Item #2</li>
</ul>
```

**`data-callsign`** is what your contextmenu item will be identified by. E.g, in the callback function, it will return the `data-callsign` of the clicked contextmenu item.

### Configuring contextmenu

If properly imported, the `window.ContextMenuJS` should exist.

`ContextMenuJS` consists of the `.init()` method and the `.attach()` method. `.init()` should **always** be called before `.attach()`.

The `.init()` method accepts 1 parameter - the contextmenu element.

Once initialized, use the `.attach` method to attach it to an element and a callback function. The callback function accepts 1 parameter, the **`data-callsign`** attribute value of the clicked contextmenu item.

### Demo

```html
<ul id="contextmenu" class="context-menu-js context-menu menu-style-default">
	<li data-callsign="item-1">Context Menu Item #1</li>
	<li data-callsign="item-2">Context Menu Item #2</li>
</ul>
<script>
var contextmenu = document.getElementById("contextmenu");
function callback(callsign){
  console.log(callsign);
}
ContextMenuJS.init(contextmenu).attach(document, callback);
</script>
```

In the example above, it will log the `data-callsign` attribute value of the clicked contextmenu item.

The class `menu-style-default` is one of the [many custom styles that ContextMenu.js offers](https://github.com/ColonelParrot/contextmenu.js/blob/main/docs/custom-styles.md), although you can always try customizing your own.
