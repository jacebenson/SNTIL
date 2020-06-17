---
title: Optional GlideRecord's Update Param
date: 2020-05-30
---

In case you did not know, Gliderecord's update() has an optional parameter which you can use to pass the reason for the update. The reason gets displayed (field-Reason) in Audit record (sys_audit).

Ex: 
```js
var gr = new GlideRecord('incident');
gr.setLimit(1);
gr.query();
if(gr.next()){
    gr.setValue('update short description');
    gr.update('Test Update');
}
```