---
title: g_form's getGlideUIElement, and getField
date: 2020-06-02
---
`g_form.getGlideUIElement` does not work on portal and `g_form.getField` does not work on normal UI. Both the functions are used to get information related to fields/variable.

For example, to get `sysid` of variable on catalog, you might have to do something like this.

```js
function getVariableID(name) {
    var id = '';
    if (typeof g_scratchpad != "undefined") {
        var fieldPortal = g_form.getField(name);
        id = fieldPortal.sys_id.toString();
    } else {
        var fieldNormalUI = g_form.getGlideUIElement(name);
        id = fieldNormalUI.fieldName.toString();
        id = id.replace("IO:", "");
    }
    return id;
}
```