---
title: setWorkflow doesn't stop flows
date: 2020-06-20
---

`gs.getProperty()` is faster than an equivalent gliderecord.


```js
var stopwatch1 = new GlideStopWatch();
gs.print(gs.getProperty(''));
gs.print('Timer:'+stopwatch1);

var stopwatch2 = new GlideStopWatch();
var gr1 = new GlideRecord('sys_properties');
gr1.addEncodedQuery('name=');
gr1.setLimit(1);
gr1.query();
if (gr1.next()) {
  gs.print(gr1.getValue('value'));
}
gs.print('Timer:'+stopwatch2);
```