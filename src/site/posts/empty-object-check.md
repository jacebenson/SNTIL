---
title: Empty Object Check
date: 2020-05-31
---

While JSUtil.notNil is awesome, do keep in mind that it does not work for empty object. Use JSUtil.isEmpty for checking objects.

Sample:

```js
gs.print("This does not work for object JSUtil.notNil({}):"+JSUtil.notNil({}));
gs.print("This works for empty object JSUtil.isEmpty({}):"+JSUtil.isEmpty({}));

var obj = {a:1};
gs.print("Not a empty object JSUtil.isEmpty(obj):"+JSUtil.isEmpty(obj));
```