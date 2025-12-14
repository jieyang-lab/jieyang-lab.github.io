---
permalink: /publications/
title: "Publications"
---

## Before UVA

{% assign posts = site.posts %}
{% assign uva_header_printed = false %}

{% for article in posts %}
{% if article.publication %}

{% if article.date >= "2024-09-01" %}
{% unless uva_header_printed %}
## @ UVA
{% assign uva_header_printed = true %}
{% endunless %}
{% endif %}

### {{ article.title }}

{% assign length = article.authors | size %}
{% assign i = 2 %}
{% for author in article.authors %}
{{ author }}{% if i < length %}, {% elsif i == length %}{% if length > 2 %},{% endif %} and {% else %}{% endif %}
{% assign i = i | plus: 1 %}
{% endfor %}

Published in {% if article.doi %}
[*{{ article.journal }}*](https://doi.org/{{ article.doi }})
{% else %}
*{{ article.journal }}*
{% endif %}.

<hr>
{% endif %}
{% endfor %}

# All articles and reviews

[Google Scholar](https://scholar.google.com/citations?user=BldDEr0AAAAJ&hl=en)
