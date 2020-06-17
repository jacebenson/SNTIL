---
title: Find Record Producer That Created Record
date: 2020-05-31
---

If you want to find which record producer created a record in ServiceNow, look into `sc_item_produced_record` table.

Note that if the target record is a task, it'll show up in the task field of the table. If it's not a task (and also if it is), then you can find the record using the value of the `record_table` field and the `record_key` field.