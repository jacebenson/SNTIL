---
title: g_scratchpad on Service Portal
date: 2020-06-20
---

`g_scratchpad` works in catalog client script on portal but does not on normal UI.

```js
if (typeof g_scratchpad != 'undefined') {
  alert("Portal");
} else {
  alert("Normal UI");
}
```