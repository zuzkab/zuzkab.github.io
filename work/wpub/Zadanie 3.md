---
layout: wpub
title: Zadanie 3
categories: task
description: XML prezentácia.
---
Dokumentácia je rozdelená podľa jednotlivých podmienok vypracovania zadania.

---
### Opis typu dokumentu

Na opis elementov prezentácie som si zvolila DTD, v ktorom som zadefinovala nasledujúce elementy s ich atribútmi:

* **presentation**		- koreňový element

* **information**		- element obsahujúci zákaldné informácie o prezentácií
* **name**				- názov prezentácie
* **authors**			- element obsahujúci mená autorov prezentácie
* **author**			- autor prezentácie s atribútom *id*
* **date**				- dátum prezentácie
* **institution**		- spoločnosť alebo inštitúcia

* **content**			- prázdny element označujúci či autor chce automaticky generovaný obsah na začiatku alebo nie

* **body**				- element obsahujúci jednotlivé slajdy prezentácie
* **page1**				- slajd pozostávajúci z nadpisu a podnadpisu
* **page2**				- slajd pozostávajúci z nadpisu, podnadpisu a textu
* **page3**				- slajd pozostávajúci z nadpisu, podnadpisu a dvoch textových polí
* **page4**				- slajd pozostávajúci z nadpisu, podnadpisu a obrázku
* **page5**				- slajd pozostávajúci z nadpisu, podnadpisu, textu a obrázku
* každý slajd má atribút *id* a *author_id*
* **title**				- nadpis
* **subtitle**			- podnadpis
* **text**				- textové pole
* **para**				- jednotlivé odrážky textového poľa, atribút *type* označuje pododrážku
* **effect**			- atribútom *type* vyberáme či bude text odrážky italic alebo bold
* **picture**			- obrázok

* **bibliography**		- element obsahujúci jednotlivé zdroje prezentácie
* **reference**			- konkrétny zdroj


---
### Vytvorenie ukážkovej XML prezentácie

Vo vzorovom xml prezentácie som použila všetky definované typy slajdov spolu so slajdom s obsaohm a zdrojmi prezentácie.
V druhom slajde je názorne ukázané využitie elementu *effect* a taktiež pododrážok definovaných atribútom *type* elementu *para* .

---
### Vytvorenie XSLT pre konverziu prezentácie z XML -> XHTML+CSS

Na vytvorenie samostatného xhtml súboru pre každý slajd prezentície som použila element *xsl:result-document*.

Každý slajd obsahuje navigáciu na predchádzajúce a nasledujúce slajdy. Na presmerovanie som využila XPath výrazy pre nasledujúceho a predchádzajúceho súrodenca. Okrem toho sa testuje či slajd je prvý v prezentácií alebo posledný.

Využíva sa niekoľko templatov pre úvodnú stranu, obsah, bibliografiu a jednotlivé slajdy. V template pre slajdy sa volajú templaty pre jednotlivé elementy slajdu s rôznymi paramatrami podľa toho, aký typ slajdu sa aktuálne spracováva.

---
### Vytvorenie XSLT pre konverziu prezentácie z XML -> PDF

Rozloženie strany som definovala pomocou elementu *fo:layout-master-set* a využívam pri všetkých stranách - slajdoch to isté. Na to, aby sa každý slajd zobrazil na samostatnej strane som vyžila element *fo:page-sequence*, v ktorom definujem jednotlivé *fo:block*y slajdov. 

Rovnako ako pri XSLT pre XML do XHTML som využila templaty pre jednotlivé elementy slajdov, ktoré sú podľa typu slajdu aplikované s rôznymi paramatrami.

Jednotlivé typy písma sú definované pomocou elementu *xsl:attribute-set* a aplikované sú atribútom *xsl:use-attribute-sets*.

