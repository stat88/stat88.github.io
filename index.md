---
layout: home
title: Home
nav_order: 1
description: A week-to-week description of the content covered in the course.
---

# Data 88S: Probability and Mathematical Statistics for Data Science

{: .mb-2 }
UC Berkeley, Summer 2023
{: .mb-0 .fs-6 .text-grey-dk-000 }

{% assign announcements = site.announcements | reverse %}
{% for announcement in announcements %}
{{ announcement }}
{% endfor %}

# Calendar
[**Jump to current week**](#week-1-the-fundamentals)

{% for module in site.modules %}
{{ module }}
{% endfor %}