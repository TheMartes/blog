---
author: "Matej Bunček"
date: 2018-10-21
image: "/img/covers/blog-za-10-eur.jpg"
linktitle: web-za-10eur-rocne
title: Web za 10 eur ročne
weight: 10
authorAvatar: /img/avatar.jpg
tags: [
    "Serverless",
    "Hugo", "Wordpress", "Ghost"
]
---

Keď som sa pred pár rokmi rozhodoval, aký nástroj použiť na moje portfólio, rozhodoval som sa medzi Wordpressom a Custom CMS-kami v Laraveli. Nakoľko mi prišiel wordpress časovo výhodnejší ako kódiť nejakú appku úplne od začiatku s tým že integrácie so sociálnymi sieťami a tému si musím sám nakódiť. Rok ubehol a z toho maličkého 100MB wordpressu sa stalo 1.5GB monštrum. **1 Téma a 2 pluginy**. Preto som sa rozhodol vyhľadat alternatívy.

## OpenSource CMS systémy
Prvá podmienka bola aby systém bol open-source, self-hosted a ideálne free. Do ruky sa mi dostali aj nejaké static site generátory, ale všetkým ako keby niečo chýbalo. Vyskúšal som ghost, ktorý bol dostatočne moderný, postavený na nodeJS, mal vynikajúce témy a bol self-hosted. Až na jednu podmienku. Potrebujete na to VPSko. Keď si pozrieme ceny VPS dnes (čo je momentálne k 21.10.2018), tak v pomere cena/kvalita vyhráva [DigitalOcean](https://www.digitalocean.com/pricing/), a to pri cenovke 5€ na mesiac. Čo je celkom slušné, pokiaľ máte väčší blog. Avšak na ten môj kde napíšem 1-2 články mesačne to je zbytočné. Medzi tými open-source by som aj rád vpratal JigSaw, čo je Static Site Generator, postavený na laraveláckom template engine [blade](https://laravel.com/docs/5.7/blade). Tento "systém" je tak minimálny, že to čo by default dostanete, je len jadro. Dizajn a pluginy si musíte nakódiť sami.

## Platené Systémy

Hľadal som aj iné alternatívy, a medzi nimi by som spomenul statamic, čo je opäť, Static Site generator postavený na laraveli. Narozdiel od ghostu alebo jigsawu, je to ale platený systém a to 100€ za licenciu (1 web). **Lifetime**. Samozrejme, že si to musíte hostovať na svojom hostingu alebo VPS. Rád by som spomenul to slovo hosting ešte raz, pretože nakoľko to je postavené na laraveli, nepotrebujete tak nutne VPS ako pri ghoste, ale stačí Vám aj shared hosting, kde rozbeháte nejakú PHP aplikáciu za pár drobných na rok. Statamic ponúka rôzne témy, pluginy a mnoho ďalšieho na ich [marketplace-i](https://statamic.com/marketplace).

# Hugo a netlify
Samozrejme, ak z toho chcete výjsť finančne čo najlepšie, a ste ochotný spraviť nejaký ten kompromis toto duo Vás nesklame. [Hugo](https://gohugo.io/), je static site generator, kompilovaný pomocou jazyka [Go](https://golang.org/). Je veľmi jednoduchý na používanie, je zadarmo, ponúka veľkú škálu tém, ktoré môžte použiť či už len na blog alebo aj ako prezenčné weby. Jediná vec ktorá Vám bude možno chýbať sú pluginy. Tie sa ale tvorcovia tém snažia istým spôsobom integrovať, buď pomocou API kľúčov alebo JSON parsermi. Ako som povedal, Hugo je zadarmo, rovnako ako aj služba [netlify](https://www.netlify.com/)(s určitými obmedzeniami, ale tie spomeniem neskôr). Služba netlify automatizuje deployment z repozitáru do ich cloudu. To znamená že jednoduchým `git push` si viete stránku hodiť na internet.

## Čo na to treba?
V prvom rade aspoň základná znalosť gitu. Nakoľko to je niečo, bez čoho by ste sa moc nepohli. V druhom rade potrebujete [GitHub](https://github.com)/[GitLab](https://gitlab.com)/[BitBucket](https://bitbucket.org) Konto, kde si budete repozitár hostovať. A samozrejme netlify účet. Ten je v istom zmysle limitovaný len na jednu osobu, pokiaľ chcete využívať free plan, pokiaľ to chcete zdieľať ako team, tak [pricing nájdete tu](https://www.netlify.com/pricing/). No a v neposlednom rade doménu. Tu sa dostávame k tej naozaj must-have platenej položke. Tie sa pohybujú cca okolo 10€, záleží akú si vyberiete.

## Prepojenie služieb
Hneď ako máme k dizpocíi všetky služby, stačí si prepojiť repozitár so službou netlify, skompilovať web pomocou príkazu `hugo`, hodiť `git push` a je to. Netlify bude automaticky syncovať váš repozitár pri každom commite. Samozrejme netreba zabudnúť nastaviť post commit príkazy v netlify a to konkrétne `hugo`. Nasledovne len prepojiť DNSka vašej domény s netlify projektom a *Voilá*. Samozrejme, že to nieje pre každého a treba mať aspoň trošku praxe v týchto vodách v každom prípade sa jedná o jednoduché serverless riešenie.

# Conclusion
Tento typ deployovania webu nieje pre každého. Ak hľadáte niečo, čo má veľkú podporu tém a pluginov oplatí sa Vám isť viacej do wordpressu alebo podobných CMS systémov. Ak hľadáte niečo elegantné čisto na blog ale na vlastom serveri, Ghost bude super alternatíva. Ale ak hľadáte niečo svižné, čo si môžte sami spravovať bez obavy či Vám ďalší update niečo nepokazí, Hugo alebo JigSaw budú spolu s Netlify tvoriť super stack.