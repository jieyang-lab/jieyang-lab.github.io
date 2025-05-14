---
title: Members
permalink: /members/
layout: single
---

<!-- === Current Members === -->
{% for author in site.data.authors %}
  {% assign member = author[1] %}
  {% if member.member and member.current %}

## {{ member.name }}

{% if member.avatar %}
![Photograph of {{ member.name }}]({{ member.avatar }}){:style="float: left; object-fit: contain; width: 40%; max-height: 12em; margin-left: 1em; margin-right: 1em;"}
{% endif %}

{% if member.bio %}
**{{ member.bio }}**
{% endif %}

{% if member.email %}
Email: [{{ member.email }}](mailto:{{ member.email }})
{% endif %}

{% if member.website %}
[Personal website]({{ member.website }})
{% endif %}

{% if member.twitter %}
Twitter: [@{{ member.twitter }}](https://twitter.com/{{ member.twitter }})
{% endif %}

{% if member.gscholar %}
[Google Scholar]({{ member.gscholar }})
{% endif %}

<p style="text-align: justify;">
{{ member.fullbio }}
</p>

<div style="clear: both;"></div>
  {% endif %}
{% endfor %}

---

## Yang Lab Alumni

<div style="clear: both;"></div>

{% for author in site.data.authors %}
  {% assign member = author[1] %}
  {% if member.member and member.current == false %}

### {{ member.name }}

{% if member.bio %}
**{{ member.bio }}**
  {% if member.start %} ({{ member.start }}{% if member.end %}&ndash;{{ member.end }}{% endif %}){% endif %}
{% endif %}

{% if member.next %}
Next: {{ member.next }}
{% endif %}

<br><br>

  {% endif %}
{% endfor %}
