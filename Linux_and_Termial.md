
# Co je to GNU/Linux?
 ## Linux
- Linux je jenom jádro systému (**kernel** = low level jádro systému, který nám umožnuje komunikovat s hardwarem), zprostředkovává rozhraní mezi hardwarem a dalšími programy a poskytuje nad nimi úroveň abstrakce.
- Dále má na starosti správu dostupných prostředků (paměť, disky...) a procesů. 
- Na jádru se následně staví různé programy a utilitity
## GNU
- Ve většině distribucích jsou k samotnému jádru (kernelu) dodány GNU utility, init systémy (systemd, openrc...), bootloadery (grub, systemd-boot), window servery (xorg, wayland...), desktop environmenty (DE - Gnome, XFCE...), windows managery (WM - Sway, Hyprland...) a programy, které používáme na denní bázi (prohlížec, textový editor, přehrávač hudby a videa...).
- Tyto komponenty jde nahradit za jiné, podle Vašeho vkusu a uvážení (- jsou tím, co spolutvoří výsledný operační systém/distribuci, ale nejsou pevně dané)



# Jak vznikl Linux?

- Jádro linux vzniklo jako projekt Linuse Torvaldse, který se po vzoru systému MINIX rozhodl napsat vlastní UNIXové jádro Linux (Linus + UNIX). 
- Linux byl jeho vysokoškolský projekt a Linus ani nepředpokládal, že by se jeho jádro mohlo nějak více uchytit.
- Původně se Linux měl jmenovat Freax (Free + freak + x [jako uniX]), ale když jeho spolupracovník viděl tento název na jejich FTP server, tak se rozhodl ho přejmenovat na Linux 
- V roce 1984 se GNU snažilo pracovat na kompletním Unix-like systému. Když Linus přišel se svým jádrem byl GNU systém skoro dokončen - až právě na jádro (the GNU hurd). 
- Přirozeně, uživatelé hledali software, který k novému jádru přidružit, a GNU utility byli "nejvhodnější".
 


# Proč zrovna linux?
- Linux používáme, protože je opensource a umožňuje nám dělat věci co bychom nemohli udělat na Windows nebo MacOS.
- Linux je kompatibilní skoro s každým hardwarem a hlavně funguje dobře na starších zařízeních.
## Filozofie linuxu
- Vše je **soubor** – uživatel může jednoduše systém přenastavit, i disky a procesy jsou reprezentovány pomocí souborů.
- Opensource - uživatel se může podívat na kód a zjistit, jak funguje.


# Linux Filesystem

```
/ # root 
├── bin/ 
├── dev/ 
├── etc/ 
├── usr/ 
│   ├── bin/
│   ├── man/
│   ├── lib/
│   ├── local/
│   └── share/
├── home/ 
├── lib/ 
├── sbin/ 
├── tmp/ 
└── var/ 
    ├── log/
    ├── lock/
    └── tmp/
```

# Jak fungují soubory v Linuxu?
## Rozlišování soborů
- Ve Windows se typy souborů určují podle přípon (.png, .jpg...).
- V Unixových systémech se typ souboru určí pomocí **headeru**, což je pár prvních bajtů v souboru.
- V headeru souboru uložené tzv. **magic numbers**, podle kterých můžeme určit typ souboru.
## Pohybování po systému
- Linuxu máme dva typy cest **relativní** a **absolutní**, všechny příkazy berou oba typy cest.
- **Absolutní** cesta = celá cesta z **root** adresáře.
- **Relativní** cesta = cesta z aktuálního pracovního/specificky definovaného (**~** pro /home/, **-** pro předchozí cestu kde jsme byli...) adresáře do cílového adresáře
## Opravnění souborů
- V Linuxu se oprávnění souborů liší od Windows
- Určujeme oprávnění pro vlastníka, skupinu a ostatní
-  Pro každého lze určit 3 práva:
>- **r** = číst (read)
>- **w** = psát (write)
>- **x** = spustit (execute)
- Tyto oprávnění můžeme zapsat pomocí čísel:
>- **4** = číst (read) 
>- **2** = psát (write)
>- **1** = spustit (execute)
> Tyto čísla se nakonec sčítají > vyjde finální číslo, např. **6** = číst, psát ale ne spustit 
>- Na zapamatování, znám krásnou báseň od našeho učitele kybernetiky:
>>"r,w,x
>> 4,2,1" - Nathan

---
# Distribuce
- Každý kdo někdy používal Linux pozná některé známé distribuce jako Ubuntu, Debian nebo Arch. Existují stovky různých distribucí a každý si najde vlastní, která mu sedne.
- Vzhledem k tomu, že Linux je pouze jádro a instalace softwaru je náročná pro uživatele, využíváme tzv. package managery (apt, pacman, dnf).
- Package managery se liší podle distribuce, nedají se v distribuci změnit, na rozdíl od ostatních věcí v distribuci.
- Z tohoto důvodu je potřeba si vybrat distribuci, která se nám líbí. (nebo kvůli sociálnímu statutu, např. arch uživatelé)
- Distribuce jsou verze Linuxu s předinstalovanými a přednastavenými nástroji a aplikacemi.

---
# Instalace
- Pokud nechceme instalovat Linux, nebo jiný operační systém přímo na náš počítač, je možné ho virtualizovat, k tomu nám pomohou programy jako je **VMware**  a **VirtualBox**.
- Instalace je rozdílná podle distribuce, kterou jsme si vybrali.
- Pokud budeme instalovat systém s automatizovaným instalačním procesem (cokoliv kromě **Arch Linuxu** apod.), tak se nás bude ptát na následující věci:
>- Uživatele a jejich hesla
>- Rozdělení disku na oddíly – swap, root, boot
>- **Swap** = oddíl na disku, který se používá při zaplněnífyzické paměti RAM, ve windows známé jako pagefile

---
# Terminál
- Terminál je program (ve windows známý jako command prompt), ve kterém spouštíme shell.
- Shell je interpreter příkazů pro kernel, zvládne udělat všechno co jde udělat skrze normální aplikaci.
- V terminálu můžeme používat shell redirection, což je způsob, jak v terminálu zacházet s daty
 ## Piping
 Při pipingu se používá operátor `|`, který přesměruje výstup jednoho příkazu do jiného
 ## Writing
 Pokud chceme zapsat výstup příkazu do souboru, můžeme použít operátor `>` a za něj napsat jméno souboru. Pokud už soubor existuje, přepíše ho.
## Appending

Dělá to samé jako writing, ale když použijete operátor `>>` se jménem souboru, který už existuje, tak výstup přidá na konec existu

# Příkazy v terminálu
- Jestli chcete používat Linux, tak je dobré znát nějaké základní příkazy, které budete používat na denní bázi.
- K příkazům můžeme přidat i argumenty (v <>), které přidávají doplňující informaci a nastavení příkazu.
## Příkazy:
- **cd** <cílový adresář>
>- cd neboli **c**hange **d**irectory je jeden z nejpoužívanějších příkazů a je nutnost ho znát, jelikož se používá pro přesouvání mezi složkami.
>- Ukázka:
>>```bash
>>student@ssps:~$ cd Desktop
>>student@ssps:~/Desktop$ 
>>```
- **ls** <(agrumenty níže)> 
>- ls neboli **l**i**s**t, nám vypíše soubory a složky v adresáři kde momentálně jsme.
>- Argumenty:
>>- **-l** (long listing) = vypíše více informací o souborech a složkách
>>- **-a** (all) = vypíše všechny soubory a složky (i skryté)
>- Ukázka:
>>```bash
>>student@ssps:~/Pictures$ ls -la 
>>total 15547
>>drwxr-xr-x    5 student student   4096 feb   6 15:12 .
>>drwx--x---+  15 student student   4096 feb  13 16:41 ..
>>-rwx------    1 student student   2506 feb  24 23:36 .cat.jpg
>>-rwxrwx---    1 student student   4849 feb  24 23:36 pes.png
>>```
- **mkdir** <jméno složky>
>- mkdir neboli **m**a**k**e **dir**ectory, nám vytvoří nový adresář
>- Ukázka:
>>```bash
>>student@ssps:~$ mkdir Slozka
>>student@ssps:~$ cd Slozka
>>student@ssps:~/Slozka$ 
>>```
- **rmdir** <jméno složky>
>- rmdir neboli **r**e**m**ove **dir**ectory, nám vymaže prázdnou složku
>- Ukázka:
>>```bash
>>student@ssps:~$ rmdir Slozka
>>student@ssps:~$ cd Slozka
>>cd: no such file or directory: Slozka
>>
>>student@ssps:~$ 
>>```
- **touch** \<soubor>
> - touch nám vytvoří nový soubor
> - využívá se na upravování metadat u souborů, jako je čas poslední úpravy souboru  
- **cat** \<soubor>
>- cat neboli con**cat**enate, nám vypíše soubor
>- Ukázka:
>>```bash
>>student@ssps:~$ cat soubor.txt
>>Ahoj
>>
>>student@ssps:~$ 
>>```
- **cp** \<původní místo> \<cílové místo>
>- cp neboli **c**o**p**y, nám zkopíruje soubor nebo složku
>- můžeme použít switch **-r** aby nám rekurzivně zkopíroval složku, to znamená že nám zkopíruje soubory a adresáře v ní.
>- Ukázka:
>>```bash
>>student@ssps:~$ cp soubor.txt soubor1.txt
>>student@ssps:~$ 
>>```
- **mv** \<původní místo> \<cílové místo>
>- mv neboli **m**o**v**e, nám přesune soubor nebo složku
>- používáme ho i pro přejmenování souborů a složek
>- Ukázka:
>>```bash
>>student@ssps:~$ mv adreasrr adresar
>>student@ssps:~$ 
>>```
- **rm** \<soubor/jméno složky>
>- rm neboli **r**e**m**ove, nám smaže soubory nebo složky
>- používáme hlavně switch **-rf**, který nám smaže složku a věci v ní (funguje i na soubory)
>- Ukázka:
>>```bash
>>student@ssps:~$ rm -rf MyLife/
>>student@ssps:~$ 
>>```
- **tree**
>- Vypíše rozvětvení složek a souborů v nich
>- Ukázka:
>>```bash
>>student@ssps:~$ tree
>>├── Downloads/ 
>>├── Pictures/ 
>>└── Public/ 
>>     ├── obrazek.jpg
>>     └── textak.txt
>>
>>3 directories, 2 files
>>student@ssps:~$ 
>>```
- **pwd**
>- pwd neboli **p**rint **w**orking **d**irectory, nám zobrazí absolutní cestu aktuálního adresáře
>- Ukázka:
>>```bash
>>student@ssps:~$ pwd
>>/home/student/
>>
>>student@ssps:~$ 
>>```
- **nano/micro/vim** (textové editory)
>- Textové editory nám pomáhají upravovat čisté **UTF8/ASCII** soubory, mají speciální funkce, podle toho, které využijeme
>- Nano je nejjednodušší pro uživatele na pochopení a využití.
>- #humor Vim je považován jako nerdovský text editor a uctívá se
>- Ukázka:
>>```bash
>>~
>>~
>>~
>>~
>>~
>>~
>>~
>>~
>>:                                                    0,0-1  All
>>```
- **grep**
>- grep neboli **g**lobal **r**egular **e**xpression **p**rint, nám vyhledá specifický string v souboru
>- Argumenty:
>>- **-r** (rekurzivní) =  vyhledá i v podsložkách
>>- **-i** (ignoruje kapitalizaci) = ignoruje, zda je písmeno velké, či malé
>>- **-E** (regulérní exprese - regex) = pomocí tohoto argumentu nemusíme hledat string, ale regex
>>- Mnoho dalších
- **chmod**
>- chmod neboli **ch**ange **mod**e, nám změní oprávnění složky nebo souboru
>- Příklady použití:
>>- chmod 764 soubor -> nastaví práva rwx pro majitele, rw-pro skupinu a r-- pro ostatní
>>- chmod u+rwx,g+rw,o+r soubor -> vykoná totéž jako předchozí příklad
- **chown**
>- chown neboli **ch**ange **own**ership, nám změní majitele souboru/složky
- **wget**
>- Používá se k nahrávání nebo stahování dat z nebo na server.
>- Zabudované rekurzivní stahování
>- Je vysoce konfigurovatelný
- **curl**
>- Stahuje souborů z internetu
>- Oproti wget podporuje více protokolů, avšak je méně konfigurovatelnější
- **file**
>- Používá **magic numbers** na zjištění typu souboru
>- Ukázka: 
>> ```
>> student@ssps:~$ file word-dokument.docx
>> word-dokument.docx: Microsoft Word 2007+
>>
>>student@ssps:~$ 
>> ```

