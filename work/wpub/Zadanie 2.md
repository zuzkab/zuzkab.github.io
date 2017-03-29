---
layout: wpub
title: Zadanie 2
categories: task
description: Transformácia vybraného dokumentu do formátu DocBook.
---
Dokumentácia je rozdelená podľa jednotlivých podmienok vypracovania zadania. V každej sekcií je uvedené ako a kde bola konkrétna podmienka aplikovaná.

---
### Štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, generovaný obsah

* **Kapitola, podkapitola a podpodkapitola** - text je členený pomocou tagov chapter a sect1-3.
```xml
  <chapter id="teoria">
    <title>Metódy objavovania znalostí</title>

    <para>Pri zvolenej úlohe predikcie je vhodné použiť proces KDD (angl. Knowledge Discovery from Data), v ktorom sa extrahujú znalosti z dát. Tento proces je tvorený presnou postupnosťou niekoľkých krokov <xref linkend="5"/>:</para>

    ...

    <sect1 id="predspracovanie">
      <title>Prístupy k predspracovaniu dát</title>
      <para>Predspracovanie dát je významnou súčasťou procesu KDD. Podstatou tohto kroku je upraviť dáta, ktoré boli získané pre dolovanie (často z rôznych zdrojov) do podoby, v akej budú použité v ďalšom kroku procesu KDD.</para>

      ...

      <sect2 id="cistenie_dat">
        <title>Čistenie dát</title>
        <para>Čistenie dát sa zameriava na dva hlavné problémy, ktoré sa vyskytujú a tými sú chýbajúce hodnoty a výrazne odchýlené hodnoty. Pre riešenie oboch problémov je dostupných niekoľko metód, ktoré sa dajú uplatniť podľa konkrétneho stavu dát.</para>
        <sect3 id="chybajuce_hodnoty">
          <title>Chýbajúce hodnoty</title>
          <para>Existujú viaceré metódy, ktoré môžeme použiť pre doplnenie chýbajúcich hodnôt <xref linkend="6"/>:</para>
        </sect3>
      </sect2> 
  		...
    </sect1>
  </chapter>
```

* **Príloha** - na konci dokumentu sa nachádza príloha Plán práce na letný semester.

```xml
<appendix>
    <title>Plán práce na letný semester</title>

    <para>Vzhľadom k miere rozpracovania bakalárskeho projektu sme navrhli nasledujúci plán práce na letný semester:</para>
    ...
    <para>Uvedený plán je orientačný a môže sa zmeniť vzhľadom na časovú náročnosť niektorých úloh a dosiahnutý výsledok.</para>
  </appendix>
```

* **Generovaný obsah** - je konfigurovaný v thesis.xsl a zahŕňa obsah dokumentu na základe kapitôl a zoznam obrázkov a tabuliek

```xml
<xsl:param name="generate.toc">
book      figure,table,title,toc
</xsl:param>
```

---
### Zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním

* **zvýraznenie slov** - v dokumente bolo použité bold a italic zvýraznenie.

```xml
<listitem>
	<para><emphasis role="italic">Ignorovanie záznamu</emphasis>, ktorý obsahuje jednu alebo viac chýbajúcich hodnôt...</para>
</listitem>
```

```xml
<entry><emphasis role="bold">Nie</emphasis></entry>
```

* **zvýraznenie členenia textu odrážkami** - bolo použité v prílohe.

```xml
<itemizedlist mark='bullet'>
  <listitem>
  <para>máj: finalizácia dokumentu (zhodnotenie dosiahnutých výsledkov práce)</para>
  </listitem>
  <listitem>
  <para>apríl – máj: porovnanie modelov získaných viacerými metódami dolovania v dátach (Random Forest, KNN algoritmus)</para>
  </listitem>
  <listitem>
  <para>apríl: optimalizácia parametrov KNN algoritmu a jej vyhodnotenie</para>
  </listitem>
  <listitem>
  <para>február – marec: vyhodnotenie modelu získaného dolovacím KNN algoritmom</para>
  </listitem>
  <listitem>
  <para>február: dolovanie v dátach pomocou KNN algoritmu</para>
  </listitem>
  <listitem>
  <para>január: zdokumentovanie existujúcich prístupov k predikcii a analýzy existujúcich riešení</para>
  </listitem>
 </itemizedlist>
```

* **zvýraznenie členenia textu číslovaním**

```xml
<orderedlist numeration="arabic">
  <listitem>
  <para>Výber a vytvorenie dátovej sady</para>
  </listitem>
  <listitem>
  <para>Predspracovanie dát</para>
  </listitem>
  <listitem>
  <para>Dolovanie v dátach (angl. data mining)</para>
  </listitem>
  <listitem>
  <para>Vyhodnotenie získaných modelov</para>
  </listitem>
  <listitem>
  <para>Využitie získaných znalostí</para>
  </listitem>
</orderedlist>
```

---
### Odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL

* **odkazy na iné časti vlastného dokumentu** 

```xml
<para><emphasis role="italic">Diskretizácia</emphasis> je proces, kedy sa numerické hodnoty atribútu nahrádzajú symbolickými. Najpoužívanejšou metódou diskretizácie je „<emphasis role="italic">binning</emphasis>“ (<xref linkend="cistenie_dat"/>), kedy sa numerické hodnoty rozdelia do určitého počtu intervalov (typicky 3, 4 alebo 5) a hodnoty v intervale sa nahradia symbolickou hodnotou.</para>
```

---
### Poznámka pod čiarou

Dokument obsahuje poznámku pod čiarou, ktorej obsahom je zároveň odkaz na URL.

```xml
<para>Riešenie predikcie sme implementovali v jazyku R <footnote><para>Využité bolo implementačné prostredie softvéru RStudio:<ulink url="https://www.rstudio.com/">https://www.rstudio.com/</ulink></para></footnote>, ktorý ponúka rozsiahlu funkcionalitu pre analýzu dát a ich grafické zobrazenie.</para>
```

---
### Zoznam použitej literatúry a zdrojov vrátane ich citácie v texte

* **zoznam použitej literatúry** - nachádza sa na konci dokumentu.

```xml
  <bibliography>
    <title>Zoznam použitej literatúry</title>

    <bibliomixed id="1"> Balla U., Malnick S., Schattner A. <title>Early Readmissions to the Department of Medicine as a Screening Tool for Monitoring Quality of Care Problems</title>Medicine. 87, 2008, s. 294-300</bibliomixed>

    <bibliomixed id="2">Hasan O., Meltzer D.O., Shaykevich S.A., et al.<title>Hospital Readmission in General Medicine Patients: Prediction Model</title>J Gen Intern Med. 25, 2010, Zv. 3, s. 211-219</bibliomixed>
    ...
  </bibliography>
```

* **citácia**

```xml
<title>Chýbajúce hodnoty</title>
	<para>Existujú viaceré metódy, ktoré môžeme použiť pre doplnenie chýbajúcich hodnôt <xref linkend="6"/>:</para>
```

---
### Vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu

* **obrázky** - v texte sa nachádza niekoľko obrázkov, na ktoré sa odkazujem v texte. Ich zoznam je uvedený za obsahom dokumentu.

```xml
<figure id="vaha">
	<title>Zobrazenie podielu chýbajúcich hodnôt atribútu váha</title>
    <mediaobject>
    <imageobject>
      <imagedata scalefit="1" width="100%" contentdepth="60%" fileref="obrazky/vaha.png"/>
    </imageobject>
    </mediaobject>
</figure>
```

```xml
<para>Dátová sada obsahovala okrem atribútov s chýbajúcimi hodnotami aj také, ktorých hodnoty boli takmer konštantné. To znamená, že daný atribút mal 2 až 4 triedy, z ktorých výrazne dominovala jedna a ostatné boli zastúpené v minimálnom, niekedy až nebadateľnom podiele (<xref linkend="miglitol"/>). Tento problém sa týkal najmä atribútov, ktoré popisovali užívanie liečebných látok počas pobytu v nemocnici.</para>
```

* **tabuľky** - v texte sa nachádza tabuľka, na ktorú sa odkazujem v texte. Zoznam tabuliek je uvedený za obsahom dokumentu.

```xml
<table id="rehosp" frame='all'><title>Počet záznamov pre jednotlivé triedy atribútu "rehospitalizácia"</title>
          <tgroup cols='4' align='center' colsep='1' rowsep='1'>
            <colspec colname='c1'/>
            <colspec colname='c2'/>
            <colspec colname='c3'/>
            <colspec colname='c4'/>

            <tbody>
            <row>
              <entry namest="c2" nameend="c4" align="center"><emphasis role="bold">Trieda atribútu "rehospitalizácia"</emphasis></entry>
            </row>

            <row>
              <entry></entry>
              <entry><emphasis role="bold">Nie</emphasis></entry>
              <entry><emphasis role="bold">Áno v30</emphasis></entry>
              <entry><emphasis role="bold">Áno m30</emphasis></entry>
            </row>
            
            <row>
              <entry><emphasis role="bold">Počet</emphasis></entry>
              <entry>54 364</entry>
              <entry>35 123</entry>
              <entry>11 877</entry>
            </row>
            </tbody>
          </tgroup>
 </table>
```

```xml
<para>Pri prvom procese dolovania v našej dátovej sade sme identifikovali problém s nerovnomerným podielom záznamov pre triedy atribútu rehospitalizácie (<xref linkend="rehosp"/>). Tento problém nepriaznivo vplýval na proces dolovania, preto bolo nutné upraviť dáta tak, aby rozdelenie záznamov v triedach bolo rovnomerné. Vytvorili sme tri možné varianty novej dátovej sady, ktoré sme následne použili v procese dolovania.</para>
```

---
### Vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni

V dokumente boli pojmy označované tagom indexterm s úrovňami primary, secondary, terciary a na konci dokumentu je pomocou tagu index vygenerovaný zoznam označených pojmov.

```xml
<para><emphasis role="italic">Diskretizácia<indexterm><primary>Transformácia dát</primary><secondary>Diskretizácia</secondary></indexterm></emphasis> je proces, kedy sa numerické hodnoty atribútu nahrádzajú symbolickými. Najpoužívanejšou metódou diskretizácie je „<emphasis role="italic">binning<indexterm><primary>Transformácia dát</primary><secondary>Diskretizácia</secondary><tertiary>Binning</tertiary></indexterm></emphasis>“ (<xref linkend="cistenie_dat"/>), kedy sa numerické hodnoty rozdelia do určitého počtu intervalov (typicky 3, 4 alebo 5) a hodnoty v intervale sa nahradia symbolickou hodnotou.</para>
```

```xml
<index>
	<title>Register pojmov</title>
</index>
```
