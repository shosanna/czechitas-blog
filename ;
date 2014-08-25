---
title: 5 základních gemů
date: 2014-06-30 1:15 UTC
tags: Rails
layout: post
author: Zuzka
---

V minulém článku jsme vám psali o tom, co to je gem a jak takový gem funguje obecně. Teď už se ale vrhneme na praktické použití! Níže naleznete seznam top 5 gemů, které já osobně instaluji téměř v každé své Railsové aplikaci. Jedná se o velice známe a používané gemy, které vám doporučí téměř každý zkušený Railsista :) Proč se s nimi tedy neseznámit rovnou a nenaučit se, kdy a jak by se měly použít! 


### Číslo 1) - Devise
Na první příčce našeho žebříčku je rozhodně [Devise](https://github.com/plataformatec/devise), řešení pro authentikaci uživatelů. Authentikace, co to je? No to je přeci možnost **zaregistrovat se** na vašem webu, vytvořit si účet a pod ním se pak při každé návštěvě moci **přihlásit**. Správný authentikační systém je pak od toho, aby bylo toho přihlašování bezpečné, tedy aby skutečně jen ten uživatel, který vlastní daný účet, k němu měl přístup. Devise toto všechno udělá za vás. Skutečně, za vás. Nainstalujete gem a v tu ránu máte k dispozici bezpečné šifrování hesla, formuláře pro registraci i login a zkrátka veškerou logiku oddělených "session" pro jednotlivé přihlášení. Jediné, co Devise potřebuje od vás, je název modelu, který předsatvuje vaše uživatele. Nejčastěji to bude asi `User`.

### Číslo 2) - SimpleForm
[SimpleForm](https://github.com/plataformatec/simple_form) zajišťuje práci s formuláři a nahrazuje vestavěné helpery `form_for` a `form_tag` přímo z Rails. Pomocí SimpleForm můžete vytvářet formuláře opravdu rychlostí blesku, neboť je to velice **jednoduché a intuitivní**. Přímo totiž napíšete, **pro co chcete udělat formulář**, například:

```
<%= simple_form_for @user |f| %>
  <%= f.name %>
  <%= f.age %>
  <%= f.hobbies %>
  <%= f.sex %>
  <%= f.submit %>
<% end %>
```

V `controlleru` pak jen uvedete, že `@user = User.new` neboli že to je formulář pro vytváření nového uživatele. Všimněte si také, že nemusíme specifikovat field a label zvlášť, od toho je `f.name` kde `f` reprezentuje form a `name` reprezentuje jaký atribut chceme nastavit. Tento řádek pak vygeneruje jak field, tak label, přičemž druh fieldu pozná podle druhu atributu (pro string vygeneruje text field, pro boolean checkbox, atd).
Na Simpleform je  velice příjemné i to, že má skvělou dokumentaci kde je všechno názorně popsáno i s příklady a umožňuje obrovskou felxibilitu. Podporuje **asociace, kolekce** (výběr z předem daných hodnot) **i různé druhy** formulářových inputů jako jsou radio butony, checkboxy či select boxy. 

### Číslo 3) - CarrierWave
[Tento gem](https://github.com/carrierwaveuploader/carrierwave) slouží pro správu obrázku, přesněji nahrávání jich na server. Představte si situaci, že chcete, aby si uživatelé mohli ke svému účtu připojit také svůj avatar. Jak tam ten obrázek dostanete? **CarrierWave se postará o upload** i úpravu obrázku a jeho uložení. Není problém ani specifikovat dvě verze stejného obrázku, jeden třeba menší pro náhled. Jediné, na co si musíte dát pozor při práci s obrázky, je jejich ukládání. Když pracujete lokálně, obrázky se ukládají na váš počítač a všechno běží, jak má. Jakmile ale nahrajete aplikaci například na Heroku, musíte si také zřídit uložiště obrázků, například přes Amazon S3 - [tento článek](http://blog.pardner.com/2012/01/rails-3-1-carrierwave-s3-heroku/) shrnuje nutné nastavení.

### Číslo 4) - Bootstrap
[Bootstrap](https://github.com/seyhunak/twitter-bootstrap-rails) je můj oblíbený, neboť za pomocí pár základních triků vykouzlí z amatérsky vypadající aplikace profesionálně působící. Bootstrap styluje frontend, neboli poskytuje **předpřipravené CSS styly**, které se pak jednoduše přidávájí do našich HTML souborů pomocí class. Příklad může být jednoduchá tabulka, v HTML napsaná nějak takto:

```
<table>
  <thead>
    <tr>
      <th> Jedna </th>
      <th> Dva </th>
   </tr>
  </thead>
  <tbody>
     <tr>
      <th> Obsah pod jednickou </th>
      <th> Obsah pod dvojkou </th>
   </tr>
  </tbody>
</table>
```

Pokud ji ale přidáme class, kterou definuje Bootstrap:

```
<table class="table table-bordered table-striped">
  <thead>
    ....
```

Rázem se celá tabulka promění. Získáme vzdušně vypadající tabulku, kde text není nepříjemně nalepený na sobě, řádky a sloupce jsou jasně oddělené a zkrátka celé to působí tak nějak upraveně. To vše bez napsání jediné řádky CSS. Otázka ale je, jak zjistíme, jaké takovéhle předpřipravené styly můžeme použít? Od toho slouží dokumentace Bootstrapu, která tentokrát sídlí na [vlastních stránkách](http://getbootstrap.com/) se skvělými příklady, které můžete jednoduše okopírovat a pak přizpůsobit vaší aplikaci. 

### Číslo 5) - Pry
Jako poslední tu máme jednu libůstku. [Pry](https://github.com/pry/pry) , na rozdíl od ostatních gemů, nezpůsobí ve vaší aplikaci nic, co by bylo okamžitě vidět. Pry slouží k hledání chyb, takzvanému **debugování**. Pomocí tohoto malého gemu můžete pak kdekoliv ve vaší aplikaci napsat kouzelná slovíčka `binding.pry` a aplikaci pustit, když pak příjde na řadu kód, kde je i tato řádka, všechno se jako mávnutím proutku zastaví a vy dostanete jedinečnou možnost podívat se dovnitř, co se právě děje. Možná to nezní příliš ůchvatně ale věřte mi, je to obrovitánsky užitečné. Zvláště v případech, kdy něco nefunguje jak má a vy ne a ne přijít na to co je špatně, protože aplikace vám zdánlivě běží, jen nedělá co má. Příklad:

Nefunguje mi ukládání uživatele, vyplním formulář, odešlu ho, stránka se reloadne a .... nic. Uživatel nikde, přičemž ale aplikace ani nehlásí chybu! Co se jen mohlo stát? Najdu si tedy ve svém `controlleru` řádek, kde by se měl uživatel uložit a pod něj dám `binding.pry`. Poté reloadnu stránku, vyplním formulář a čekám. Stránka nedoběhne, ale v terminálu, kde mi běží server, se otevře REPL a já mou dovnitř psát a zkoumat, co se s aplikací děje. Napíšu tedy něco jako `user.save` a zjišťuje, že uložit nejde, protože se mi vrátilo `false`. To bude asi náš kámen ůrazu. Co teď? Aha, `user.errors` mi hned řekne, co je špatně. Nevyplňovala jsem povinné pole a proto mi selhaly validace. Pomocí Pry vždy snadno nahlédnete co se děje a prozkoumáte, jak vaše aplikace běží či neběží. 





