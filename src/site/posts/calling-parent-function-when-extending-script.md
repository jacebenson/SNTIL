---
title: Calling Parent Function when Extending Script
date: 2020-06-05
---

Calling parent function when extending script

```js
//Sample Scripts

//Parent class

var ParentScript = Class.create();
ParentScript.prototype = {

    initialize: function () {
        gs.info('In ParentScript Intialize');
    },

    print: function () {
        gs.info('In ParentScript Print');
    },
};

//Child class
var ChildScript = Class.create();
ChildScript.prototype = Object.extendsObject(ParentScript, {

    initialize: function () {
        ParentScript.prototype.initialize.call(this);
        gs.info('In ChildScript Intialize');
    },

    print: function () {
        ParentScript.prototype.print.call(this);
        gs.info('In ChildScript Print');
    },
});

//Execute using

var child = new ChildScript();
child.print();
```