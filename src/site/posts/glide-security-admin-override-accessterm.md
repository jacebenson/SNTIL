---
title: glide.security.admin.override.accessterm
date: 2020-05-30
---

When `glide.security.admin.override.accessterm` is `false`, ACLs are evaluated cumulatively. If there are number of ACLs on any given field and the Admin Overrides option is false (not selected) on one of them, then the effective admin overrides for all the ACLs are considered to be false. This causes admins to be unable to pass even the ACL where the override should be in effect.

Credits: Chaithanya Bontha