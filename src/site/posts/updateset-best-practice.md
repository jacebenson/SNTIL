---
title: Updateset Best Practice
date: 2020-05-30
---

For completed update set on the production instance, you should always change the state to Ignore. This state ensures that the update set is not committed again when cloning the instance.

Credits: Garrison Ball