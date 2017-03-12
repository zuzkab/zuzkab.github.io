---
layout: default
title: Knihy
categories: hobby
permalink: /hobby/books.html
description: Všetko o mojich obľúbených knihách a žánroch.
---
# Knihy

Knihy čítam najmä pri cestovaní vlakom alebo čakaní medzi prednáškami a cvičeniami v škole. Uprednostňujem čítanie e-kníh, keďže môžem mať stovky kníh v jedenj malej čítačke.

## Žánre

Medzi moje naobľúbenejšie knihy patria biografie. Myslím si, že človek má z čítania väčší zážitok, keď vie, že číta a reálnom príbehu. Najmä pri biografiách obetí prvej a druhej svetovej vojny behá mráz po chrbtoch.

---
## Odporúčam:

  <ol>
    {% for item in site.data.books %}
    <li>
    	<img src= "{{site.baseurl}}/images/{{item.image}}" class="list_img"/>
        <h3>{{item.title}}</h3> 
        <p style="font-style:italic">{{item.author}}</p> 
    </li>
    {% endfor %}
  </ol>