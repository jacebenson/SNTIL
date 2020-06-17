---
title: Evil of toString()
date: 2020-05-30
---

The evil of toString() - "Regex strikes back"

Spent few hours tracking this down as Replace method won't support regex for objects. What a fun Friday this was.

Simplified code:

```js
var uri = gs.action.getGlideURI()
var object = uri.toString();
var string = uri+"";

gs.print(uri);
//gs.print(object.replace(/sys_scripts/,'')); //throws an error.
gs.print(string.replace(/sys.scripts/,''));

gs.print(typeof object);
gs.print(typeof string);
```