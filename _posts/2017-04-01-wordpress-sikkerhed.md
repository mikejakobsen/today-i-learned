---
title: Sådan sikrer du din WordPress side mod indbrud
layout: post
date: 2017-04-01 23:21:29
category: WordPress
tags: [WordPress]
---

Indledningsvist vil jeg starte med at undskylde clickbait overskriften. Men i modsætning til den gængse clickbait rundt på nettet, er der noget at hente her.


```html
<a href="http://www.breitlingonlineshop.com/" target="_blank" rel="nofollow">Cheap Replica Breitling</a>
<a href="http://www.uswatchesbuy.org/" target="_blank" rel="nofollow">cheap replica cartier watches</a>
````

WordPress har tidligere været i miskredit, grundet dets ringe sikkerhed. Det faktum at 26,4% af internettet er baseret på WordPress skaber et kæmpe incitament til at finde sikkerhedshuller i netop WordPress.

For at få kontrol over en WordPress installation, kræves det tre parametre at få kontrol over en WordPress installation. URl’en hvor loginnet skal indtastes (Std: /wp-admin), brugernavnet der som udgangspunkt er Admin. Og slutteligt, kodeordet. 

Her efterlader det faktum at WordPress oprindelige intention er som blogging platform en række problematikker. Da man som udgangspunkt, ved at tilgå domæne.com/?author=1 bliver redirected til /author/brugernavn, og dermed kender man brugernavnet tilhørende administrator loginnet.

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
