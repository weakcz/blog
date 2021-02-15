---
title: "Jak nainstalovat LAMP (Apache, MySQL, PHP) v Arch Linuxu"
date: 2021-02-13
description: "V tomto návodu si ukážeme jak nainstalovat server Apache, databázi MariaDB a PHP v Arch Linuxu"
draft: false
showTOC: true
stitek:
- apache
- php
- mariadb
- návod
- instalace
kategorie:
- Návody
---

LAMP je akronym **L**inux **A**pache **M**ySQL a **P**hp. V tomto tutoriálu si ukážeme, jak nainstalovat LAMP v Arch Linuxu.

<!--more-->

## Update systému

Nejdříve provedeme update systému. Do terminálu zadejte

```bash 
pacman -Syu
```

  ## Instalace Apache

Po updatu nainstalujeme server Apache

```bash
pacman -S apache
```

Otevřete si v textovém editoru **/etc/httpd/conf/httpd.conf**

```bash
nano /etc/httpd/conf/httpd.conf
```

najděte

```text
[...]
#LoadModule unique_id_module modules/mod_unique_id.so
[...]
```

a odstraňte **#** před na začátku řádku. Soubor uložte.

Nastavíme server, tak aby se spouštěl při bootu systému.

```bash
systemctl enable httpd
systemctl restart httpd
```

Ověříme si, zda server opravdu jede

```bash
systemctl status httpd
```
Pokud se zobrazí tohle, tak server jede v pořádku

![Server status](/obrazky/prispevky/instalace-lamp/01-server-status.png)

### Otestujeme Apache

Vyzkoušíme, zda server opravdu funguje. Do hlavního adresáře serveru **/srv/http/** vytvoříme soubor pomocí příkazu

```bash
nano /srv/http/index.html
```

do souboru vložíme tohle:

```html
<html>
 <title>Test</title>
  <body>
   <h2>Test Apache serveru</h2>
  </body>
</html>
```

pak soubor uložte.

Nyní si v prohlížeči otevřete adresu **http://localhost** a měli byste vidět tohle:

![localhost](/obrazky/prispevky/instalace-lamp/02-apache-test.png#center)

## Instalace MariaDB

```bash
pacman -S mysql
```

MariaDB je oficiální hlavní implementace mySQL v Arch Linuxu. Proto z nabídnutých možností vyberte MaraDB.

Než spustíme MariaDB, tak se musíme databázi napřed zinicializovat.

```bash
mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

 Nyní nastavíme databázi, tak aby se spouštěla při startu systému

```bash
systemctl enable mysqld
systemctl restart mysqld
```

Otestujeme, zda databáze funguje.

```bash
systemctl status mysqld
```

Pokud se zobrazí tohle, tak vše jede, tak jak má.

![Mysql status](/obrazky/prispevky/instalace-lamp/03-mysql-status.png)

### Nastavíme hlavní heslo k MariaDB

Doporučuje se nastavit root heslo k MariaDB. To provedeme pomocí příkazu:

```bash
mysql_secure_installation
```

spustí se průvodce instalací. Instalace se bude ptát na různé otázky, tak odpovězte podle tohoto:

```text
Enter current password for root (enter for none): Zmáčkněte Enter
Switch to unix_socket authentication [Y/n]: Zadejte n
Change the root password? [Y/n]: potvrďte Enterem
New password: Zadejte Vaše heslo
Re-enter new password: Znovu zadejte heslo pro potvrzení
Remove anonymous users [Y/n]: potvrďte Enterem
Disallow root login remotely? [Y/n]: opět Enter
Remove test database and access to it [Y/n]: opět Enter
Reload privilege tables now? [Y/n]
```

Datbáze by měla být nastavená a připravená k používání.

## Instalace PHP

K instalaci PHP v Arch Linuxu spusťte

```bash
pacman -S php php-apache
```

Po instalaci PHP musíme nastavit PHP modul na serveru. Otevřete soubor *httpd.conf*

```bash
nano /etc/httpd/conf/httpd.conf
```

Najděte následující řádek a odstraňte a přidejt **#** na začátek řádku, pokud už tam není.

```text
#LoadModule mpm_event_module modules/mod_mpm_event.so
```

a odstraňte **#** z

```bash
LoadModule mpm_prefork_module modules/mod_mpm_prefork.so
```

a na konec sekce kde jsou **LoadModule** přidejte

```text
LoadModule php_module modules/libphp.so
AddHandler php-script .php
```

A na konec souboru přidejte

```text
Include conf/extra/php_module.conf
```

Teď jenom restartujeme server

```bash
systemctl restart httpd
```

### Otestujeme PHP

vytvoříme soubor

```bash
nano /srv/http/test.php
```

a do souboru vložte 

```php
<?php
 phpinfo();
?>
```

soubor uložte.

Nyní když půjdete v prohlížeči na **http://localhost/test.php** mělo by se vám zobrazit tohle:

![Php Info](/obrazky/prispevky/instalace-lamp/04-php-info.png)

A to je celá instalace Apache PHP a Mysql.