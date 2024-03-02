# Témata workshopů
- Úvod do KBB - 24. 2. 2024
- Linux a terminál - 2. 3. 2024
- Sítě - 9. 3. 2024
- Kryptografie a programování - 16. 3. 2024
- Kybernetické útoky - 23. 3. 2024



# Jak vypadají otázky ve školním KBB testu u přijímacího řízení?
```
1) Jaký politický systém je v České republice?

a) konstituční monarchie
b) prezidentská republika
c) parlamentní republika
d) poloprezidentská republika
```



# Úvod do KBB
- Z větší části znalost technologií, z menší části znalost bezpečnosti
## Whitehat X grayhat X blackhat
- whitehat = identifikuje a opravuje zranitelnosti a jedná tak **se svolením** nebo na žádost organizace, do jejíž systémů se nabourává (také nazýváni jako etičtí hackeři)
- grayhat = hacker, který nemá kriminální nebo zlovolné úmysly jako blackhat, ale také nemá předchozí vědomí nebo souhlas těch, do jejichž systémů se nabourává
- blackhat = **kyberzločinec**, který se nelegálně snaží nabourat do systémů se zlým nebo kriminálním úmyslem
## Týmy entických hackerů
- red team - útočící tým (hledání zranitelností s cílem dostat se do systému)
- blue team - obraný tým (forenzní analýza, monitorování sítě atd.)
- purple team - tým řešící komunikaci mezi red a blue týmem



# Malware
- škodlivý software, který v počítači provádí činnost, se kterou uživatel nesouhlasí nebo by s ní nesouhlasil, kdyby o ní věděl
## Druhy malwaru
- virus - program, který se dokáže šířit bez vědomí uživatele, pro množení se vkládá do jiných spustitelných souborů či dokumentů
- červ - šíří se prostřednictvím počítačových sítí, za využití zranitelností operačních systémů ,
- trojský kůň - program, který se tváří užitečně (například hra, spořič obrazovky nebo nějaký jednoduchý nástroj), ale ve skutečnosti jde o malware
- adware - malware zahlcující počítač reklamními okny, což také často znepříjemňuje práci uživatele
- ransomware - vyděračský malwaru, který zašifruje obsah disku napadeného zařízení a vyžaduje od oběti uhrazení výkupného 
- spyware - získává data o činnosti uživatele např. záznamem stisknutých kláves (keylogger) nebo pořizováním snímků obrazovky (screenlogger) 

    ![příklad adwaru na pc s OS Windows XP](https://www.startpage.com/av/proxy-image?piurl=http%3A%2F%2Fenglish474awe.weebly.com%2Fuploads%2F4%2F7%2F1%2F0%2F4710028%2F7256363.jpg%3F341&sp=1709377217T53a17d2c34194c61da0b655670d765df82d7cf3de7d2ba702aff97590031355c)

## Analýza malwaru
- dynamická - analýza chování malwaru při spuštění a běhu v izolovaném a monitorovaném prostředí
- statická - analýza malwaru bez jeho spuštění
## Příklady nástrojů pro analýzu malwaru
- VirusTotal (statická analýza)
- Any.run (dynamická analýza)

    ![příklad statické analýzy Malwaru pomocí nástroje Virustotal](https://kb.stuckinvim.com/assets/static_analysis.png)



# Zranitelnosti
- Exploit - zneužití programátorské chyby (jedná se například o nějaký program, nebo skript)
- CVE - identifikátor známé zranitelnosti
- Zero-day exploit - jedná se o exploit, který není ještě obecně známý



# Social engineering
- způsob manipulace lidí za účelem provedení určité akce nebo získání určité informace
- phishing - příklad social engineeringu, internetový podvod (podvodné maily) používaný k získávání citlivých údajů

    ![příklad phishingu](https://www.startpage.com/av/proxy-image?piurl=https%3A%2F%2Foptima-systems.co.uk%2Fwp-content%2Fuploads%2F2019%2F07%2Fblog_content-phishing-email-from-amazon.png&sp=1709385767T2879431f244a5fca1efca26ab5b7640f953cd803311837b41f4ed97fd6898fbb)


# OSINT
- proces shromažďování informací z veřejně dostupných zdrojů 
- OSINT framework - soubor nástrojů a technik používaných pro OSINT (https://osintframework.com/)
- shodan.io - vyhledávač pro zařízení připojená k internetu
- Google dorking - technika, která využívá pokročilé vyhledávací operátory k odhalení informací na internetu, které nemusí být snadno dostupné
## Příklady Google dorkingu
- níže přehled pár příkladů google dorkingu, existuje jich však daleko více, stačí si vyhledat Google dorking
```
	inurl:ssps.cz ext:pdf
    intitle:"Index of" wp-admin
    filename:config.php dbpasswd
```
