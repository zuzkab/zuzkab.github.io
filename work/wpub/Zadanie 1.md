---
layout: wpub
title: Zadanie 1
categories: task
description: Osobné webové sídlo (GitHub Pages + Jekyll + Markdown).
---
Dokumentácia je rozdelená podľa jednotlivých podmienok vypracovania zadania. V každej sekcií je uvedené ako a kde bola konkrétna podmienka aplikovaná.

---
### Podstránky

Osobné webové sídlo obsahuje momentálne 8 podstránok:

  <ul>
    {% for page in site.pages %}
    {% if page.title %}
    <li>
        <a href="{{ page.url | relative_url }}">{{ page.title | escape }}</a>
    </li>
    {% endif %}
    {% endfor %}
  </ul>

---
### Layouty

Pri podstránkach je využitých 5 layoutov:

* **default** - obsahuje hlavičku a pätičku stránky
* **home** - dedí od *default*. Poskytuje rozloženie úvodnej strany sídla.
* **about** - dedí od *default*. Na vrchu stránky fotografia s tabuľkou, pod ktorými sa nachádza text.
* **list** - dedí od *default*. Popis stránky s jej podstránkami vo forme listu.
* **wpub** - dedí od *default*. Obsahuje základné informácie o zadaní, zísakné z dátového súboru zadaní.

---
### Dárové súbory

Webové sídlo využíva 3 dátové súbory: 

* *books.yml* - názov knihy, autor a obrázok ([Knihy](/hobby/books.html))
* *music.yml* - skupina/interpret a hudobný štýl ([Hudba](/hobby/music.html))
* *tasks.yml* - zoznam zadaní s názvom, časom odovzdania, stavom, bodovým ohodnotením a podmienkami na vypracovanie ([Zadanie 1](/work/wpub/Zadanie%201.html))

---
### Filtre

* **escape**
```html
    <h1 class="post-title">{{ page.title | escape }}</h1>
```

* **relative_url**
```html
	<a href="{{ item.url | relative_url }}">{{ item.title | escape }}</a>
```

* **where**
```html
{% raw %}
	{% assign pages = site.pages | where: "categories", page.list %}
```

---
### Tagy

* **if**, **else**, **for**

* **assign**
```html
	{% assign pages = site.pages | where: "categories", "task" %}
``` 

* **raw**
```html
	{% raw %}
		{% assign pages = site.pages | where: "categories", page.list %}
```

* **include**
```html
	  {% include head.html %}

  <body>

    {% include header.html %}

    <main class="page-content" aria-label="Content">
      <div class="wrapper">
        {{ content }}
      </div>
    </main>

    {% include footer.html %}

  </body>
```

---
### Plugin

Použité sú 2 pluginy:

* **emoji-for-jekyll** - smajlíky nahrádza konkrétnym obrázkom ([O mne](/about.html))
* **youtube** - prehratie videa z youtubu ([Hudba](/hobby/music.html))

Na GitHub Pages sú pluginy nefunkčné, takže je zobrazenie iné ako na localhost-e.

---
### Premenné

V nasledujúcej tabuľke sú uvedené niektoré z použitých premenných.

|Premenná|Použitie|Význam
|---|---|---
|type|about.md, hobby.md, work.md|určuje, že stránka sa zobrazí v navigačnom bare
|age, home, color|about.md|informácie o autorovi stránky
|list|work.md, hobby.md|kategória podstránok, ktoré budú vybraté do listu
|categories|music.md, books.md,...|definuje, do akej kategórie patrí podstránka
|title|all|názov každej podstránky
|author, image, style, deadline,...||premenné použité v dátových súboroch
