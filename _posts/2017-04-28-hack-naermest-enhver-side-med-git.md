---
title: Hack nærmest enhver side med hjælp fra Git
layout: post
date: 2017-04-28 23:21:29
category: Git, Hacking
tags: [Git, Hacking]
---

Enhver udvikler med respekt for sig selv, benytter selvfølgelig *Git*, under udvikling. Eller en anden form for version control. Men har de mon husket at fjerne git filerne igen?

En meget udbredt fejl disse udviklere laver, er at efterlade deres *.git* repo filer. Når de uploader deres arbejde til serveren.

Når man finder et sådan repository efterladt online via fx. en web scanner. Er det overraskende nemt at clone det pågældende *Git* repository. For dernæst at søge det igennem, og finde sensitiv information, eller restore tidligere versioner af det udvikleren har lavet.

Git repositoriet findes ofte som en *.git* mappe, i roden af domænet.

```
(Eksempel: 216.58.211.142/.git/)
```

Vi kan dermed clone hele *Git repoet* ved at køre en rekursiv wget på *./git* mappen på domænet.

```
wget -r www.google.com/.git/
cd www.google.com
```

Nu har vi så klonet hele *Git repoet* til vores egen computer. Vi kan derfør køre en række helt almindelig *Git commands* for at gennemgå de nuværende, og endnu mere spændende, tidlivere versioner af siden.

Udviklere gemmer ofte hemmelig data i deres kode, for senere at flytte det til *.env* filer, der ikke overføres til git. Man kan derfor ofte finde database samt login informationer, i et helt almindeligt *git repository*.

Indledningsvist kan du starte med at skrive..
```
git status
```

For at se, at du rent faktisk har adgang til den pågældende sides *git* informationer.

Dernæst kommer du langt med en kombination af *git log* og *git diff*.

Med lidt held, vil du hurtigt støde på et git output. I stil med *.env added*

Og du kan dernæst køre en *git diff* og se hvor de følsomme informationer denne *.env* fil indeholder, stammer fra.

Til slut kan du køre en *git reset --hard*.

