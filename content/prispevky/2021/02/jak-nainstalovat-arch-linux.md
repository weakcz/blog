---
title: "Jak nainstalovat Arch Linux"
date: 2021-02-07
image: obrazky/prispevky/michelles-meteor-memento/michelle_s_meteor_memento_nahled.png
description: "Young woman finds strange seed on walkway and she keeps it as a memonto for meteor crash."
draft: false
showSidebar: false
stitek:
- arch
- linux
- instalace
kategorie:
- Arch Linux
serial: "Jak na Arch Linux"
---
V tomto článku vám ukážu jak nainstalovat Arch Linux.
<!--more-->
## Varování !
**Zde popsaný postup vymaže všechna data na disku. Proto doporučuji zkusit napřed instalaci ve virtuálním počítači (Virtualbox).**


## Požadavky

Napřed se podíváme na požadavky pro instalaci Arch Linuxu

-   x86_64 (64 bit) kompatibilní počítač
-   Minimálně 512 MB RAM (doporučených je minimálně 2 GB)
-   Asi tak 2 GB volného místa (doporučuje se 20 GB pro základní použití s desktopovým přostředím)
-   Aktivní připojení k internetu
-   USB zařízení s minimální velikostí 2 GB
-   Základní znalost Linuxového příkazového řádku


## Co budeme potřebovat

Ze všeho nejdříve budeme potřebovat instalační ISO Arch Linuxu. To si stáhneme [odtud](https://archlinux.org/download/).

Pokud budete zkoušet instalaci ve virtualním počítači. Tak je to vše, co budete potřebovat. Pokud budete chtít instalovat
Arch Linux na skutečném PC, tak si budete muset ISO "vypálit" na USB. Já používám [balenaEtcher](https://www.balena.io/etcher/).

## Vypálení na USB

pro vypálení na USB používám, jak už jsem zmínil, `balenaEtcher`

{{< figure src="/obrazky/prispevky/jak-nainstalovat-arch-linux/balenaEtcher.png" title="balenaEtcher" >}}

Použití je jednoduché. V prvním sloupci si vyberete stažené ISO Arch Linuxu. V druhém sloupci si vyberete USB zařízení, kam se ISO vypálí. A třetí je tlačítko, které zahají vypalování.


## Instalace

### Rozdělení disku

Pro rozdělení disku použijeme program cfdisk. Do terminálu napište:

```bash
cfdisk
```

```bash
fdisk -l
``` 