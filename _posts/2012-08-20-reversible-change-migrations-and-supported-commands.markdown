---
wordpress_id: RB-6
layout: post
title: Reversible (change) migrations and supported commands
---

So I was trying to recall the commands that are supported by a change migration, and decided to put them up for easy future reference:

- add_column
- add_index
- add_timestamps
- create_table
- remove_timestamps
- rename_column
- rename_index
- rename_table


Source: [CommandRecorder API](http://api.rubyonrails.org/classes/ActiveRecord/Migration/CommandRecorder.html)
