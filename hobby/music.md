---
layout: default
title: Hudba
categories: hobby
description: Všetko o mojom hudobnom vkuse, chodení na koncerty a hraní na hudobné nástroje.
---
# Hudba :notes:

Hudbu mám veľmi rada. 

## Žánre

Mojím jednoznačným favoritom v hudobných žánroch je rock, punk a ska. Avšak neznamená to, že ostatné štýly odmietam. Ak je pesnička rytmická a hrá mi v hlave celý deň je mi jedno od koho je :smile: . 

---

## Festivaly a koncerty

Okrem počúvania hudby doma, rada chodím na koncerty a festivaly. Z koncertov mám najradšej malé, v útulnom klube a s úžasnou atmosférou. 
Medzi kapely, ktorých koncert si nenechám ujsť patrí *Ine Kafe*, *Smola a Hrušky*, *Zoči Voči* alebo *Horkýže Slíže*.

Medzi moje najobľúbenejšie letné festivaly patrí *Grape Festival*, ktorý je jedinečný svojou atmosférou.

---

## Aktuálne najobľúbenejšia pesnička

{% youtube Ra2UQhJNrBY %}

---

## Obľúbené kapely a interpreti:

  <ol>
    {% for item in site.data.music %}
    <li>
        <h3>{{item.name}}</h3> 
        <p style="font-style:italic">{{item.style}}</p> 
    </li>
    {% endfor %}
  </ol>


