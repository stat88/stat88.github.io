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

{: .highlight }
> Welcome to Data 88S! The first lecture will be on Tuesday, June 20th, from 10:30 AM - 12 PM in McCone 141; the first section will be after the first lecture, from 2:00 PM - 4:00 PM in Evans 340.
>
> Please carefully read through the [syllabus](syllabus), which contains a detailed explanation of how the course will work this summer.

{% assign announcements = site.announcements | reverse %}
{% for announcement in announcements %}
{{ announcement }}
{% endfor %}

# Calendar
[**Jump to current week**](#week-1-the-fundamentals)

{% for module in site.modules %}
{{ module }}
{% endfor %}