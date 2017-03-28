---
title: Sådan sikrer du din WordPress side mod indbrud
layout: post
date: 2017-04-01 23:21:29
category: WordPress
tags: [WordPress]
---

Indledningsvist vil jeg starte med at undskylde clickbait overskriften. Men i modsætning til den gængse clickbait rundt på nettet, er der noget at hente her.

I 2016 havde netbutikkerne et direkte tab på 55 millioner kroner som følge af dankortsvindel. Det er en stigning på 86 procent i forhold til året før. 86 procent? En grund er at [Politiet](http://www.fyens.dk/indland/Netbutikker-Politiet-sylter-svindelsager/artikel/3135273) sylter sagerne så meget, at forbryderne har frit spil. Jacob Risgaard fra Coolshop udtalte f.eks. for nyligt at han har 7 ringbind liggende, med omkring 1000 sager omkring dankortsvindel.

Jeg tror dog, at den helt store sønder, er de såkaldte vifte eller kontakt-løse dankort, der stille og roligt er blevet [almen eje](http://www.business.dk/finans/nu-rykker-danskerne-det-kontaktloese-dankort-brager-afsted) i blandt danskerne. Da disse indeholder en dybt absurd sikkerhedsbrist. Da NFC-chippen, der netop gør det muligt at betale, ved blot at lægge kortet på terminalen i butikken.

Konstant udsender dine kortoplysninger. Bevares, den udsender da ikke din pinkode. Men der er frit spil, hvad angår nethandel.

Jeg har tidligere testet dette af på en unavngiven Baresso her i Aarhus. Da man via en NFC reader til [20-30$](https://www.alibaba.com/product-detail/NFC-Reader-ISO-14443-type-A_60302074915.html?s=p) ens computer, kan sidde, og opsnappe enhver forbipassernes dankort oplysning.

En sådan sikkerhed vil få de fleste netbank brugere, til at ligge skrigende i fosterstilling. Og formentlig skifte bank hurtigst muligt.

Der minder mig om da Statens Serum Institut (SSI) sidste år, kom til at blotte 5.3 millioner danske CPR numre.

Bevares, de havde egentlig sendt oplysningerne i et anbefalet brev til Danmarks Statistik. Men det dukkede op hos den kinesiske visummyndighed Chinese Visa Application Centre.

### Hvordan afsendes personfølsomme data fra A til B?

Jo, nu skal du høre

1. Du har en CD (Opfundet i 1982), hvor du i bedste stenalder stil skriver de knap 5.280.000 personfølsomme data på. (OBS: Lad vær med at kryptere dem. Det tager så lang tid)

2. Du finder en almindelig konvolut. Typisk lavet af papir. Der 9/10 gange kan åbnes uden brug af skærebrænder eller koben.

3. På konvolutten sørger du for at nedskrive den rette modtager. Dog behøver du ikke tænke for meget over det, da dit sendte materiale alligevel ikke kan bruges af andre. Det går nok.

4. Efter afsendelse tager du en velfortjent kop kaffe. Job's done.

Kilde: http://www.b.dk/nationalt/det-flossede-personnummer

## WordPress

Min pointe i overstående, er egentlig blot. At sikkerhed angår os alle. At store multinationale selskaber som Nets, så ikke har styr på det. Betyder ikke at du ikke, med ret simple midler. Kan få styr på det.


WordPress har tidligere været i miskredit, grundet dets ringe sikkerhed. Det faktum at 26,4% af internettet er baseret på WordPress skaber et kæmpe incitament til at finde sikkerhedshuller i netop WordPress.

For at få kontrol over en WordPress installation, kræves det tre parametre at få kontrol over en WordPress installation. Ligesom der kræves tre parametre til at få adgang til din e-boks eller netbank. 

Så langt så godt, tre parametre burde vel være rigeligt for enhver? Bestemt! Med mindre, du dagligt bevæger dig rundt med en sølvpapirshat.

I modsætning til din netbank, hvor de tre parametre er dit 10 cifrede CPR nummer, en selvvalgt kode, og slutteligt det NemID du har liggende i skuffen.

I den sammenhæng skal du lige huske at ifølge Digitalitaliseringsstyrelsen selv er 86 pct. af danskerne tilfredse eller meget tilfredse med NemID. Ifølge dem selv, selvfølgelig.

Ligeledes kan det nævnes at 98,3 pct. Er tilfreds, eller super tilfredse med mit arbejde igennem de sidste mange år.

Kilde: Mig og Digitaliseringsstyrelsen: https://www.digst.dk/It-loesninger/NemID/NemID-naeste-generation

WordPress kræver ligeledes tre parametre.

URl’en hvor loginnet skal indtastes (normalt: /wp-admin), brugernavnet der som udgangspunkt er Admin. Og slutteligt, kodeordet til din side.

Her efterlader det faktum at WordPress oprindelige intention er som blogging platform en række problematikker. Da man som udgangspunkt, ved at tilgå domæne.com/?author=1 bliver redirected til /author/brugernavn, og dermed kender man brugernavnet tilhørende administrator loginet.

Dermed vil man i løbet af ganske få sekunder, have mulighed for at indledningsvist tilgå /?author=1, og dernæst tilgå /wp-admin. For derefter enten at forsøge et Dictionary attack med en række kendte passwords, eller et simpelt Brute force attack hvor en række tilfældige værdier benyttes.

For at undgå disse sikkerhedsbrister indførte jeg derfor en række forholdsregler, for at omgås WordPress ringe opbygning i forhold til sikkerhed.

Indledningsvist valgte jeg derfor at lave en simpel redirect baseret på et RegEx pattern, for på denne måde ikke at tilkendegive brugernavnet. Der hvis den besøgende forsøger at tilgå /?author samt en værdi mellem 0-9, vil blive redirected til en simpel 404 side. I stedet for at kunne tilgå brugernavnet der er angivet på siden. Ligeledes redirects /author med en efterfølgende parametre ligeledes. Da nogle bots i stedet tilgår /author/admin/ for at klarlægge om siden, benytter admin som brugernavn.

````
RewriteCond %{REQUEST_URI} ^/$
RewriteCond %{QUERY_STRING} ^/?author=([0-9]*)
RewriteRule ^(.*)$ http://siden.dk/author/? [L,R=301]
````

For at undgå at en bot blot kan tilgå /wp-admin og forsøge at gætte løs. Benytter jeg WPS Hide Login. Der laver en redirect fra /wp-login.php samt /wp-admin til en side du selv specificerer - Fx. det mere danskklingende /logind

Slutteligt flyttede vi ligeledes wp-config.php filen fra public_html mappen til den overliggende mappe, der i tilfældet med en Debian baseret Lamp-Stack som Høks benytter er var/www/, da filen dermed ikke kan tilgås direkte fra en http request.

Da de fleste WordPress installationer hackes udelukkende for at opnå SMTP credentials der står i denne wp-config fil, for på denne måde at sende tusindvis af spam mails, via disse credentials. 
En fremgangsmåde, som ejeren af siden sjældent opdager, før domænet er blevet blacklistet af Google. 


# Noter

https://wordpress.org/plugins/better-wp-security/




```html
<a href="http://www.breitlingonlineshop.com/" target="_blank" rel="nofollow">Cheap Replica Breitling</a>
<a href="http://www.uswatchesbuy.org/" target="_blank" rel="nofollow">cheap replica cartier watches</a>
````

