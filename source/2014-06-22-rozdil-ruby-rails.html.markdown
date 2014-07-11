---
title: Jaký je rozdíl mezi Ruby a Ruby on Rails?
date: 2014-06-22 21:01 UTC
tags: Rails
layout: post
published: false
author: Zuzka
---

Téměř každý, kdo někdy začínal s programováním si někdy položil tuto otázku či její obměnu. Svět moderních technologií je natolik rozsáhlý, že všechny tyto pojmy můžou být pro začátečníka velice matoucí. Přidejme ještě věci jako SQLite, git, příkazová řádka, terminál, bundler, sublime text, server, localhost, comit, migrace .. a už to začíná být spíše jeden velký cirkus. V tomto článku se blíže podíváme na základní rozdělení ze všech, na alfu a omegu vašeho programování v Rails - v čem se Rails liší od samotného Ruby? A kdy použiji co?

Vezmeme to pěkně popořádku. **Ruby je programovací jazyk**. Je jedním z mnoha a mnoha programovacích jazyků, které si dnes můžete zvolit. Určitě jste už alespoň slyšeli některé další jako Javascript, Java, C nebo třeba méně známe jako Lisp, Haskell či Prolog. Programovací jazyk si můžeme představit jako cizí jazyk, jaký se učíme ve škole. Stejně jako španělština je pro nás nejprve nečitelná, tak může vypadat i Ruby. Oba dva mají nějaká gramatická pravidla, syntax kterým se musíme řídit, chceme=li být korektní. Rozdíl je, že lidské jazyky jsou dělané pro komunikaci s lidmi, programovací jazyky pro komunikaci s počítačem. Proto musíme být do detailu přesní, když se snažíme vyjádřit naše úmysly třeba v Ruby (počítač se nás nedoptá, jak jsme to mysleli).

S programovacím jazykem můžem udělat ledacos. Můžeme si zvolit Ruby nebo třeba Javu, mají své odlišnosti, své silné stránky i ty slabší, ale ve výsledku bychom měli být schopni v obou případech dojít k cíli. Můžeme napsat kód, který vyůstí třeba v desktopovou hru, jako je hledání min. Nebo můžeme napsat program, který bude automaticky nahrávat naše data třeba na Facebook :) Můžeme také napsat webovou aplikaci, třeba jako ten samotný Facebook nebo Twitter.

Ruby má plno využití. Rozdíl, oproti hře z prvního příkladu a webové aplikaci z posledního je ten, že desktopová aplikace se dá samostatně spustit. Asi jako když babičce pustíte na počítači Solitaire, nebo otevřete Microsof Excel. Webová aplikace oproti tomu **běží jen uvnitř vašeho prohlížeče**. Potřebujete k ní tedy přístup k internetu. Webová aplikace také většiunou stojí na vašem účtu - který určuje kdo jste, jak se přihlásite a zkrátka o vás ukládá všelijaká data. Když takovou webovou aplikaci navštívíte druhý den, bude si toho hodně pamatovat.

Jistě jste si všimli, že webové aplikace získáváji na popularitě. Jsou všude a lidé je také rádi tvoří. Není to totiž zase natolik obtížné. Někteří chytří lidé (konkrétně 37signals) si všimli, že během každého vytváření nové webové aplikace existují určité kroky, které se vždy opakují. Ačkoliv byl námět jiný, jednou se dělala sociální síť, po té blog, obecné schéma postupu bylo velice podobné. V praxi to pak znamenalo psaní Ruby kodu, který se opakoval či byl opravdu dlouhý. A tak vzniklo Ruby on Rails.

Ruby on Rails je framework, neboli sada několika knihoven. Je to nadstavba nad Ruby, to znamená, že je to v tomto jazyce napsané. A teď co to vlastně znamená. Knihovna je balíček již napsaného kódu, **který můžeme znovupoužít**. Je to jako by někdo jiný za nás udělal část práce a nám dal jen návod, jak se na ni odkazovat a jak pokračovat. Reálně to jsou připravené metody a třídy které jsou někde popsány (třeba v oficiální Ruby on Rails dokumemntaci) a my je můžeme používat, spoléhat se na ně aniž bychom věděli, jak vnitřne fungují. Není to ale žádná magie, je to zas jen Ruby, které bychom si stejně tak mohli napsat sami. Knihovna nám šetří čas a energii a dává nám určitou abstrakci.

Ruby on Rails je tedy taková pomůcka pro tvorbu webových aplikací v Ruby. Není to ale jen o kôdu.

Když si otevřeme jakokouliv Rails aplikaci v editoru, vidíme **stále stejnou strukturu složek** - víme, že máme nějaké `app` a v něm najdeme například naše `views`. To je příklad toho, co nám přináši Rails. Strukturu, řád. Nejsou to jen připravené metody ale i určité konvence a principy, které nám značně usnadní život. Dalším příkladem může být princip **"convention over configuration"** neboli konvence nad nastavováním. Tento princip říká, že v Railsech je téměř vše téměř vždy hned připraveno k použití. Není potřeba nic nastavovat a ani specifikovat, všechno dopředu předpokládá, že chceme to samé, co chce většina developerů. Pouze v případě, že máme nějaké specifické požadavky, musíme sáhnout ke konfigurování souborů. Tento princip potvrzuje i `scaffold`. Když chceme nový model pro `Article`, napíšeme jen

```
rails generate scaffold article title:string content:text
```
A je to, Rails udělají zbytek za nás, protože předpokládájí, že chceme standartní řešení. Mohli bychom si to také napsat ručně, vytvořit soubory, pojmenovat class, udělat migraci pro tabulku v databázi a její atributy, připravit v HTML šablony pro listování všech článků či přidávání nového, a tak dále. Proč se ale obtěžovat, zvlášť když za chvíli budeme dělat to samé pro uživatele, komentáře, ...

Na závěr ještě jedna malá poznámka. Začátečníci se často ptají, kde v Rails aplikaci najdou to Ruby. Zkrátka ho tam nevidí. Je ale všude. Tedy, všude tam, kde máme u souboru **koncovku .rb** a nebo tam, kde se vkládá dynamicky přes ERB. (Rails přidávájí třeba i to, že nám do naší aplikace pěkně spojují ostatní soubory, potřebné pro vývoj, jako HTML, kaskádové styly či javascript). Všechno, co má onu magickou koncovku je ale Ruby. Podívejme se na tento jednoduchý model:

```
class Question < ActiveRecord::Base
  attr_accessible :text
  validates_presence_of :text

  has_many :answers
end
```

Jestli jste se někdy učili Ruby, rozhodně jste se učili deklarovat třídy či jejich dědičnost, není to tedy nic nového. To, co je uvnitř, je jen volání různých metod. Jak jsem říkala v úvodu, my zde nevidíme a ani nechceme vidět implementaci. Spoléháme se a věříme, že například `validates_presence_of` jako metoda, která bere jeden parametr (my ji zde voláme s naším textem) udělá to, co se od ní čeká. Tedy neuloží novou instanci `Question` s prázdným atributem `text`.

A kde se ta implementace bere? Přeci jsme ji nainstalovali na náš počítač když jsme psali `gem install rails`. Stáhli jsme si do počítače všechno, co Rails přináší a začali čerpat jeho výhody. Snad je tedy již jasnější, jaký rozdíl je mezi jazykem, který hovoří s počítačem a překládá mu naše úmysly a mezi knihovnou či celou sadou knihoven, která tento jazyk využívá aby nám ušetřila práci. Úvaha na závěr: gemy jsou vlastně také knihovny!
