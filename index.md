---
layout: home
title: Home
nav_order: 1
description: A week-to-week description of the content covered in the course.
---

# Data 88S: Probability and Mathematical Statistics for Data Science
UC Berkeley, Spring 2025
{: .mb-0 .fs-6 .text-grey-dk-000 }

{% assign announcement = site.announcements | last %}
{{ announcement }}

# Calendar
[**Jump to current week**](#week-8-variance-sd){: .btn } 

{% for module in site.modules %}
{{ module }}
{% endfor %}
