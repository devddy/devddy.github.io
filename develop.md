---
layout: default
title: Your New Jekyll Site
---

<div id="develops">
  <h1>개발이야기</h1>
  <ul class="posts noList">
    {% for category in site.categories %}
      {% if category == 'develop' %}
        {% for develop in category %}
          <li>
            <span class="date">{{ develop.date | date_to_string }}</span>
            <h3><a href="{{ develop.url }}">{{ develop.title }}</a></h3>
            <p class="description">{% if develop.description %}{{ develop.description  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ develop.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
          </li>
        {% endfor %}
      {% endif %}
    {% endfor %}
  </ul>
</div>