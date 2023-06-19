---
layout: home
title: Home
nav_order: 1
description: A week-to-week description of the content covered in the course.
---
Welcome to Data 88S!

Lecture: 10:30 AM - 12:00 PM in McCone 141 on Mondays, Tuesdays, Wednesdays, and Thursdays. 
Discussions: 2:00 PM - 4:00 PM in Evans 340 on Tuesdays and Thursdays.

# Calendar

{% for module in site.modules %}
{{ module }}
{% endfor %}