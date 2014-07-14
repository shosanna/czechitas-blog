---
title: Editor nebo příkazová řádka?
date: 2014-06-22 21:15 UTC
tags: Rails, Command line
layout: post
author: Zuzka
---

Pro psaní webové aplikace v Ruby on Rails potřebujeme dva nástroje - editor a příkazovou řádku. Oba dva mají poměrně jasně odlišitelnou funkčnost a způsob použití, pojďme si to objasnit na příkladech.Začneme s **příkazovou řadkou**.

Také se jí jinak říká jejím anglickým jménem command line, na jiných operačních systémech než Windows potom terminál. Ať již ji nazveme jakkoliv, vždy se jedná o to malé černé okno, které krom programování většina z nás nikdy nemusela dříve otevřít. Na Windowsech se k ni dostaneme pres `Start -> Spustit ->` napsat "cmd" a Enter.

![obrazek](http://www.bleepstatic.com/tutorials/cmdprompt/cmdprompt.gif)

A co sem tedy píšeme? Shrňme si to do kategorií:

**1. Navigační příkazy**. To jsou příkazy, jak se v command line dostat ze složky do jiné složky (a ultimátně do naší aplikace) či příkazy, které manipulují se soubory, ukazují nám, kde právě jsme či co se v jaké složce nachází.

Příklady: *(`$` značí, že se mají psát do command line, `#` značí komentář)*

```
$ cd projects      # přesune se z aktuálního umístění do složky projects
$ dir              # vypíše na obrazovku soubory, nacházející se ve složce, kde jsme
```

**2. Gitové příkazy**. Git jako takový nemá nic společného s Rails, můžeme ho používat v jakémkoliv jazyce. Píše se do command line, protože je to obecný nástroj na správu souboru a jejich verzí. My ho používáme pro zálohování našeho kódu či sdílení na GitHub.

Příklady:

```
$ git add .                      # přidá všechny změny k uložení
$ git commit -m "nejaky popis"   # uloží všechny změny
$ git status                     # zobrazí, jestli máme nějaké neuložené změny
```

**3. Rails generování souborů, manipulace s databází a gems**. Tato kategorie už konečně souvisí s Rails, ale týká se jen těch specifických případů, kdy něco generujeme, nebo manipulujeme s třetí stranou jako jsou knihovny - gemy. Týká se to velký změny aplikace, nikoliv ale jejího chování nebo designu. Do terminálu píšeme, když chceme změnit celkovou strukturu - třeba přidat nový model nebo přidat tabulku v databázi. Plus samozrejmě zapínáme celý server přes command line :)

Příklady:

```
$ rails generate scaffold User name:string   # vygeneruje model, views a controller pro uživatele
$ bundle install                             # zaktualizuje všeechny naše gemy
$ rake db:migrate                            # spustí migrace - aktualizuje naši databázi o nové sloupečky či tabulky
```

## Editor

Do editoru (např. Sublime text) pak píšeme všechno, co se přímo týká chování a vzhledu naší aplikace. Všech náš kód, naše HTML šablony, naše styly pro vzhled stránek a podobně. V Rails aplikaci najdeme většinou tyto druhy souborů, do kterých zapisujeme:

- `.rb` soubory, tam píšeme Ruby
- `.html.erb` soubory, tam píšeme HTML a na speciální místa můžeme vkládat ruby (do `<% %>` )
- `.css` soubory, tam dáváme naše kaskádové styly
- `.js` soubory, tam můžeme přidávat javascript

Příklad toho, co píšeme do editoru je pak třeba celý soubor, jako tento:

```ruby
class PlacesController < ApplicationController

  def index
    @places = Place.all
  end

  #...
  end
```

Toto už je chování aplikace, něco, co se bude měnit relativně často (oproti změnám, které jsme inicializovali z command line). Tato metoda `index` patřící do controlleru nám říká, že když se spustí akce `index` (neboli někdo příjde na náš web na /places) tak tato metoda sáhne do databáze a vytáhne z ní všechny jednotlivé Places a připraví je pro view, který je po té uživateli zobrazí.

## Shrnutí:
Do editoru píšeme kód, který určuje, co naše aplikace dělá, jak co vypadá, kde co najdeme, kam vedou jednotlivé odkazy a tak dále. Do příkazové řádky píšeme obecné věci kolem - generujeme soubory (které pak můžeme editovat v editoru, když už jsou na světě), spouštíme server, ukládáme změny do gitu nebo manipulujeme s databází.
