---
title: "5 věcí, které si lidé myslí o Linuxu"
date: 2021-02-16
description: "5 věcí, které si lidé myslí o Linuxu"
draft: false
showTOC: true
showSidebar: false
stitek:
- linux
- pověry
kategorie:
- Linux
---
Rozhodl jsem se sestavit takový seznam věcí, které si lidé, kteří nejsou zase až tak obeznámeni s počítačem, mohou myslet o Linuxu. Jako dlouholetý uživatel Windows jsem některým z těchto věcí věřil také.
<!--more-->

## 1. Linux je těžký na ovládání

Tohle už nemusí být zase až taková zásadní věc. Různá desktopová prostředí, jako je KDE Plasma, XFCE, Gnome, existují již dlouho. Takže ovládání je stejné jako na Windows nebo MacOS. 

## 2. Linux je jen pro hackery a technicky zaměřené lidi

Tohle možná bývalo pravdou, ale v dnešní době už to není. S příchodem Ubuntu, jenž bylo vytvořeno právě za účelem snadného používání Linuxu normálními uživateli, se to změnilo.

## 3. Pro Linux je málo programů

To že pro Linux není dostupné Microsoft Office nebo produkty od Adobe, neznamená, že je málo programů, za každý program existuje náhrada. Za MS Office je LibreOffice a za Adobe Photoshop je třeba Gimp. Takovýchto příkladů bych tu mohl najít hodně.

### 3.1 Instalace programů je složitá

Právě, že není! Každá distribuce má správce balíčků, které se starají právě o instalaci programů. Ať už přes terminál, nebo nějaký GUI program.  

Instalace programů je díky balíčkům daleko jednodušší. Například pokud chcete do Windows nainstalovat Firefox, tak musíte jít na stránku firefoxu, kliknout na odkaz ke stažení, počkat až se program stáhne. Potom si otevřít adresář a spustit instalační soubor.

V Linuxu nic takového nehrozí. Stačí otevřít program jako je Správce Softwaru v Ubuntu nebo Pamac v Arch Linuxu a v něm si najít Firefox a pak stačí dát instalovat.

Druhou možností je instalace pomocí terminálu. Například v Ubuntu nebo na Ubuntu založených distribucích stačí do terminálu napsat: 

```bash
sudo apt install firefox
```

nebo v Arch Linuxu a na Arch Linuxu založených distribucích:

```bash
sudo pacman -S firefox
```



## 4. Pro Linux neexistují hry

Je fakt, že pro Linux neexistuje moc nativních her (hry přímo pro Linux). To ale zachraňují programy jako je Wine (umožní spouštět programy určené pro Windows) a DXVK (překládá grafické instrukce DirectX pro Vulkán) a hlavně technologie od Valve implementovaná do Steamu s názvem Proton.  

Proton je vlastně již zmíněné Wine a DXVK uzpůsobené pro Steam, tak aby hráči na Linuxu nemuseli složitě všechno nastavovat. Stačí pouze aktivovat Proton v  nastavení a o všechno se postará Steam klient. Například Doom z roku 2016 běhá pod Linuxem stejně dobře jako na Windows.

## 5. Linux je Ubuntu

Když jsem v okolí řekl, že jsem z Windows přešel na Linux, tak jsem zaregistroval 2 reakce.

1. nechápavé áha, kdy bylo z výrazu tváře jasně čitelné, že vůbec neví, co to ten linux vlastně je.
2. Ty sis nainstaloval Ubuntu?

U první reakce se zastavovat ani nebudu. Pro tyto případy jsem vytvořil tento blog, kde se lidé mohou o linuxu dozvědět zajímavé věci.

Druhá reakce je pochopitelnější. I spousta netechnických médií sem tam přinese nějakou zprávu o Linuxu a právě Ubuntu je v těchto zprávách zmíněno nejčastěji. Proto si lidé spojují Linux a Ubuntu do jednoho celku. Je to stejné jako když se řekne, že američané udělali to nebo tohle, tak se lidi řídí rovnicí Amerika = USA. Přitom je v (Severní) Americe ještě Kanada a Mexiko. A přesně to samé platí u některých lidí - Linux = Ubuntu, ale tak to není.   
Existuje spousta jiných distribucí. Například Fedora, OpenSuse, Debian, Arch linux.

