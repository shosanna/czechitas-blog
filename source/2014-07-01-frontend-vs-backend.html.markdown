---
title: Frontend vs. Backend
date: 2014-07-01 14:19 UTC
tags: Programování
author: Zuzka
layout: post
---

Pojmy backend a frontend jsou často používané zejména mezi programátory (ale rozumí jim i projektoví manažeři v IT firmách) se často používají v inzerátech a zkrátka jsou velice rožšířené i mezi veřejností. Pro mnohé ale stále může být nejasné, o co vlastně jde a kde je hranice mezi frontendem a backendem. 

Dobrá pomůcka pro zapamatování co které slovo znamená, se dá odvodit z jejich anglického překladu. **Frontend je něco jako "přední konec", neboli to co je vepředu, to co je vidět**. **Backend, tedy "zadní konec" je pak to úúúplně vzadu**. Tyto pojmy zastřešují technologie právě podle toho, jestli se pomocí nich dělají věci, které jsou viditelné, a nebo se pomocí nich dělá vnitřní chování nějaké aplikace. Hned vysvětlím na příkladu.

HTML je jedna z frontendových technologií. Jedná se o značkovací jazyk, pomocí kterého udáváte strukturu a formu textu pro webové stránky. Znáte to, například pomocí tagu `<h1> </h1>` uděláte nadpis první úrovně, a tak dále ... Důležité v tomto případě je, že změny, které v jazyce HTML uděláte, se promítnou na obrazovce pro vaše uživatele - místo ve větách je text v seznamu s odrážkami, tabulka má najendou více řádků, odstavce jsou delší, apod. ... Když to vezmeme víc technicky, jedná se o jazyky, **které fungují na klientovi, neboli v prohlížeči**. Prohlížeč sám je umí interpretovat, rozumí jim. 

Oproti tomu **technologie backendu běží na serveru**, někde klidně i několik stovek kilometrů vzdáleném od počítače, odkud danou aplikaci používáte. Server je potřeba, aby daný jazyk rozluštil, aby mu porozumněl - ten potom posílá výsledky na klienta. Podívete-li se třeba na Facebook, server musí udělat celou řadu práce - podívá se do databáze, najde si vás podle vašich přihlašovacích ůdajů, vytáhne ven novinky vašich kamarádů za poslední dny, zpracuje tyhle informace a pak to všechno pošle na klienta už v technologicích, kterým klient rozumí.

Pod backend spadají například programovací jazyky jako je Ruby, Python, Java, C nebo třeba Haskell. Pomocí nich **naprogramujete, co bude aplikace dělat**. Například že Facebook je postavený na tom, že každý uživatel má svůj ůčet, svou osobní zeď, může se spojovat s kamarády a může psát statusy. Backend to tedy vše připraví a zařídí aby fungovalo jak mělo (na serveru) a pak to vše **odešle na frontend (do klienta)** kde se už jen finalizuje jak to všechno bude dohromady vypadat. Uživatel pak dostane celý výsledek jako jednu stránku.

Až tedy zase příště uvidíte inzerát, že se hledá šikovný frontenďák, budete vědět, že tento člověk nebude muset znát kdovíjaké algoritmy či pracovat s databází, ale mnohem spíše bude potřebovat rozumět HTML a kaskádovým stylům a k tomu se mu bude hodit i špetka citu pro design.

