---
layout: default
title: WPUB
categories: work
permalink: /work/wpub.html
description: Stránka predmetu Webové publikovanie s prehľadom zadaní počas celého semestra.
---
# WPUB

Predmet webové publikovanie sa zaoberá značkovacím jazykom XML a súvisiacimi technológiami. 

## Zadania

Počas semestra sa vypracovávajú 3 zadania s možnosťou získania 26 bodov.

___
  <ul class="post-list">
    {% assign pages = site.pages | where: "categories", "task" %}
    {% for item in pages %}
    <li>
        <h2>
          <a class="post-link" href="{{ item.url | relative_url }}">{{ item.title | escape }}</a>
        </h2>
        <p>{{ item.description }}</p>
    </li>
    {% endfor %}
  </ul>