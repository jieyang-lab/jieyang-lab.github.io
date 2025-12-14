---
permalink: /publications/
title: "Publications"
layout: single
---

## Before UVA

{% for article in site.posts %}
  {% if article.publication and article.date %}
    {% assign article_date = article.date | date: "%Y-%m-%d" %}
    {% if article_date < "2024-09-01" %}

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
  {% endif %}
{% endfor %}

## @ UVA

{% for article in site.posts %}
  {% if article.publication and article.date %}
    {% assign article_date = article.date | date: "%Y-%m-%d" %}
    {% if article_date >= "2024-09-01" %}

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
  {% endif %}
{% endfor %}

## All articles and reviews

[Google Scholar](https://scholar.google.com/citations?user=BldDEr0AAAAJ&hl=en)
