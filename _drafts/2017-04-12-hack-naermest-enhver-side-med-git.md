---
title: Git
layout: post
date: 2017-04-10 17:21:29
category: WordPress, Hack
tags: [WordPress, Hack]
---

Enhver udvilker med respekt for sig selv, benytter selvfølgelig Git, under udvikling.

En meget udbredt fejl disse udviklere laver, er at efterlade deres *.git* repo filer. Når de uploader deres arbejde.

Når man finder et sådan repository efterladt online via fx. en web scanner. Er det overraskende nemt at clone det pågældende Git repository. For dernæst at søge det igennem, og finde sensitiv information, eller restore tidligere versioner af det udvikleren har lavet.

Git repositoriet findes ofte som en .git mappe, i roden af webhotellet.

(Eksempel: 216.58.211.142/.git/)

Vi kan dermed clone hele *Git repoet*
