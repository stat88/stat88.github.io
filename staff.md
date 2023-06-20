---
layout: page
title: Staff
nav_order: 3
description: A listing of all the course staff members.
---

# Staff

Append `@berkeley.edu` to all email addresses. **For questions, concerns, personal circumstances, or sensitive matters,** please use the staff email address **[data88s@berkeley.edu](mailto:data88s@berkeley.edu)**, which is monitored only by the instructors. 

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
