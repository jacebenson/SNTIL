---
title: Make Catalog Variables ReadOnly
date: 2020-06-20
---

If you want to make all the variables of a catalog readonly on RITM or sc_task table, you can use g_form.setVariablesReadOnly(true);
Note that this will not work on other tables like incident

## Some related notes from Slack

If you have fields you want to exclude from being read only use this

```js
var notReadOnly = ["your_custom_field","other_field_that_is_not_read_only"];
var fields = g_form.getEditableFields();
for (var x = 0; x < fields.length; x++) {
    if(notReadOnly.indexOf(fields[x]) == -1){
        g_form.setReadOnly(fields[x], true);
    }
 }
```

[Official Docs](https://docs.servicenow.com/bundle/newyork-it-service-management/page/product/service-catalog-management/concept/service-catalog-variable-editor.html)

> To make the VEditor read-only in Platform, activate the onLoad client script, "Variable Editor Readonly", for the following tables:

> To make the VEditor read-only in Service Portal, navigate to Service Portal > Portals, select Service Portal, and specify the following code in the Quick start config field. "readonly_variable_editor": "true"

> Catalog UI policies, catalog client scripts, catalog data lookups, reference qualifiers, and dependent reference fields are supported on the default variable editor only for task-extended tables. To support a catalog UI policy or a catalog client script on this editor, select the Applies on the Target Record check box for the catalog UI policy or the catalog client script.

> To make this editor read-only, create an onLoad client script on the task extension and add the following code:

```js
function onLoad() {
    $("variable_map").querySelectorAll("item").forEach(function(item){
    var variable = item.getAttribute("qname");
    g_form.setReadOnly("variables."+ variable, true);
    });
}
```

[Source](https://hi.service-now.com/kb_view.do?sysparm_article=KB0752560)