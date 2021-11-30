---
layout: dark
title: About
example: "Example text in this variable."
---

Some Markdown coontent discribing your site.

This page describes the amazing {{site.title}} by {{site.author.name}}.
{{page.example}}

{% include big-cat.html %}

## About About Pages

The About page is a common convention dound on websites.
It is your opportunity to let us know all the details "about" your project:

- focus and topic area
- peple involved
- code and projects used

{% for animal in site.data.animals %}
  - The {{animals.name}} is a {{animals.size}} animal.
{% endfor%}

##Large animals are best!

{% for animal in site.data.animals %}
  {% if animal.size == "large" %}
    - <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
  {% else %}
    - <small>{{animal.name}}</small>
  {% endif %}
{% endfor %}

## Small animals only

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
  - {{ animal.name | upcase }}
{% endfor %}

