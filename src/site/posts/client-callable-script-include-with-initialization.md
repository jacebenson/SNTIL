---
title: Client Callable Script Include with Initialization
date: 2020-06-16
---
While creating a client callable script include, the general practice is to avoid overriding initialize method, which is also stated in the [official documentation](https://docs.servicenow.com/bundle/orlando-application-development/page/script/ajax/topic/p_AJAX.html).

But, in case you do want to override the initialize method for some reason, you can do so easily by following the below sample. You just need to add few extra parameters to your initialize method and invoke AbstractAjaxProcessor's initialize method.

```js
//Sample script include
var DoStuff = Class.create();
DoStuff.prototype = Object.extendsObject(AbstractAjaxProcessor, {

  initialize: function(request, responseXML, gc) {
    AbstractAjaxProcessor.prototype.initialize.call(this, request, responseXML, gc);
    this.stuff = 'something';
  },

  print: function() {
      return this.stuff;
  },
});
```

```js
//Sample script to test script include works
var glideAjax = new GlideAjax('DoStuff');
glideAjax.addParam('sysparm_name','print');
glideAjax.getXMLWait();
alert(glideAjax.getAnswer());
```