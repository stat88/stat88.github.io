---
layout: page
title: Staff
nav_order: 3
description: A listing of all the course staff members.
---

# Staff

Append `@berkeley.edu` to all email addresses.

## Instructors

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

{% assign staff = site.staffers | where: 'team', 'Staff' %}
{% assign num_staff = staff | size %}
{% if num_staff != 0 %}
## Course Staff

{% for staffer in staff %}
{{ staffer }}
{% endfor %}
{% endif %}
