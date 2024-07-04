---
permalink: /research/
title: "Research"
---

{% assign interests = site.research | sort: "index" %}

{% for interest in interests %}
## {{ interest.name }}

{% assign parity = interest.index | modulo:2 %}
{% if parity == 0 %}
{% assign alignment = "right" %}
{% else %}
{% assign alignment = "left" %}
{% endif %}

![{{interest.image_alt}}]({{interest.image}}){:style="float: {{alignment}}; object-fit: contain; width: 45%; max-height: 40em; margin-left: 2em; margin-right: 2em;"}

<p style="text-align: justify;">
{{ interest.content }}
</p>
{% endfor %}
