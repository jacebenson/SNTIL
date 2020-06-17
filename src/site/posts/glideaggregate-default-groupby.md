---
title: GlideAggregate default groupby
date: 2020-05-30
---

GlideAggregate groups by the aggregated column by default (when using functions MAX, MIN or AVG).
So don't forget to use its setGroup method.

Sample in comments section.
Credits: @jános Szentpáli

```js
var cmn_location_Ga = new GlideAggregate('cmn_location');
cmn_location_Ga.addNotNullQuery('u_node_id');
cmn_location_Ga.addAggregate('MAX', 'u_node_id');
cmn_location_Ga.setGroup(false);
cmn_location_Ga._query();
if (cmn_location_Ga._next()) {
  return +cmn_location_Ga.getAggregate('MAX', 'u_node_id');
} else {
  return 0;
}
```