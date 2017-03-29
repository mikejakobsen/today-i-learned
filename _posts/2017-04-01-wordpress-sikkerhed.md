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

Her efterlader det faktum at WordPress oprindelige intention er som blogging platform en række problematikker. Da man som udgangspunkt, ved at tilgå domæne.com/?author=1 bliver ledt videre til /author/brugernavn.

Det var altså to af parametrene. Kunne du forestille dig at have en netbank, udelukkende med en kode? Nej vel..

En person med skidte intensioner, vil dermed kunne få hans computer til at crawle nettet. Søgende efter sider, med noget på /wp-admin. Prøv det selv, du vil blive overrasket over hvor store sider, der bruger WordPress og ikke har sk
nket sikkerhed en tanke.

Nååh' ja, men jeg har jo min kode.

De fleste bliver overrasket over hvor hurtigt, man kan nedbryde den sidste hindring, kodeordet. Et forholdsvist simpelt **Dictionary attack** med fx. Hydra. Tager ofte kun 20-30 minutter om at finde koden til siden. Et **Dictionary attack** er som navnet så fint hinter, et lang liste med udvalgte kodeord. Der så bliver fyret af imod din side. Din egen kode, er højst sansingligt imellem [Seclist](https://github.com/danielmiessler/SecLists/tree/master/Passwords) mange millioner koder.

Jeg vender snart tilbage med en guide til hvordan du udførrer netop et sådan **dictionary attack**, da det på ingen måde kræver nogen nævneværdige it-skills.

## Jamen.. Hva' gør jeg så?

Det tager vitterligt kun 3 minutter at sikre sig.

Der er 3 simple ting, jeg vil råde dig til. Der hverken kræver en programmør, eller mere end 5 minutter af din tid.

### Trin 1 - Flyt login siden.

Finder de bots der netop nu crawler nettet intet på */wp-admin*. Er de hurtigt videre til det næste, og meget nemmere mål.

Så lad os starte med at flytte login siden til fx. *minside.dk/logind/*

Start med at hente [Move Login pluginet](https://da.wordpress.org/plugins/sf-move-login/)

Her kan du så vælge, hvad du vil kalde adressen.

![Move login](http://i.imgur.com/5ksvtxw.png)

Du behøver på ingen måde, at være lige så kreativ som overstående. Jeg er selv stor tilhænger af at benytte */log-ind/*.

### Trin 2 - Lad os gemme dit brugernavn

Det her trin, kan godt virke en lille smule nørdet.

Den eneste måde at gemme dit brugernavn for besøgende, er ved simpelthen at sparke dem ud, hvis de skulle forsøge at finde det.

Jeg har lavet tre linjer kode herunder, der gør netop det.

```
RewriteCond %{REQUEST_URI} ^/$
RewriteCond %{QUERY_STRING} ^/?author=([0-9]*)
RewriteRule ^(.*)$ http://siden.dk/author/? [L,R=301]
````

Det eneste du skal gøre er at skifte *siden.dk* ud med navnet på din hjemmeside. Og indsætte de tre linjer et sted i din *.htaccess* fil.

*.htaccess* filen finder du i den første mappe du går ind i, på din server. Ofte *public_html*.

### Trin 3 - Få dig en ordentlig kode klovn

Du bruger den samme kode til alt ik? Hvor mange brugere har du rundt på nettet? 20-50?

Bliver din kode hacket i en af de mange leaks der dagligt er rundt på nettet, vil skumle typer hurtigt kunne forsøge din email og det hackede kodeord rundt omkring på nettet.

Prøv at tjek din mail på [HaveIBeenPwned](https://haveibeenpwned.com/). Jeg kan nævne at mine data, har været indblandet i tre lækager. 

Det bedre råd er derfor at få dig en password manager som [LastPass](www.lastpass.com) eller [1Password](www.1password.com). Der laver et tilfældigt kodeord til dig, til hver side.
Og smart nok, husker det for dig. Du behøver altså aldrig mere at huske en kode.


### Tips til dig der sidder med en sølvpapirshat på.

*Flyt wp-config.php filen*

Ofte bliver sider hacket, udelukkende for at sende tusindivs af spam-mails ud fra den tilknyttede mail. Ofte uden at ejeren aner uråd.
Symptomerne kommer først, når Google har blacklistet domænet. Hvilket i såfald betyder, ingen organiske besøgende via Google. 

Et godt råd er derfor at flytte *wp-config.php* filen en mappe længere ud, da personen der evt. får adgang til siden. Ikke vil kunne indhente FTP/SMTP logins, og dermed ikke har mulighed for at udrette så stor skade.

Så flyt du blot, den fil en mappe tilbage, ligesom hvis du skulle flytte en fil fra dit Skrivebord til Dokumenter.

*Gør det umuligt at redigere i filer direkte fra WordPress*

Nu vi alligevel har fat i *wp-config.php* filen, er der lige en ting mere. Under *Editor* på de fleste WordPress sider, er det muligt at redigere i alle filerne.
Hvilket også gør det muligt for personer med dårlige intensioner, bare at slette løs.

Defore søg efter *DISALLOW_FILE_EDIT* i *wp-config.php* filen og sikre dig, at denne står til true og ikke false.

Ligesom herunder.

```
define( 'DISALLOW_FILE_EDIT', true );
```

*Installer Better WP Security*

Better WP Security er et glimrende plugin.

http://wordpress.org/plugins/better-wp-security/
