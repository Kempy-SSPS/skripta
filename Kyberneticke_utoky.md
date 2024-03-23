# Kybernetické útoky

## Varování
 - Tento dokument slouží pouze pro vzdělávací účely
 - Není určen k použití v reálných útocích
 - Útoky na cizí systémy bez povolení jsou nelegální
 - Dodržujte zákony vaší země

## Úvod
### Co to je kybernetický útok?
 - Kyberútok je útok, ktérý se z pohledu útočníka odehrává v kyberprostoru.
 - Pokud si dá ůtočník dá záležet a nezanechává po sobě silné stopy, může být velmi těžké zjistit, kdo za útokem stojí.
#### Důvody k útoku
 - Osobní
 - Krimalní
 - Politické

### Zranitelnosti - vulnerability
#### CVE(Common Vulnerabilities and Exposures)
 - Označení různých zranitelností pomocí ID
 - Např. log4shell je [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)

#### CVSS(Common Vulnerability Scoring System)
 - Různé verze - aktuální verze 4.0
 - List softwarových a hardwarových zranitelností
 - Označuje závažnost zranitelnosti
 - Např. [CVSS:4.0/AV:L/AC:L/AT:P/PR:L/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N](https://www.first.org/cvss/calculator/4.0#CVSS:4.0/AV:L/AC:L/AT:P/PR:L/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N)

## Typy útoků

### Phishing
 - Útočník se snaží získat citlivé informace od oběti
 - Většinou se jedná o hesla, čísla kreditních karet, ...
 - Útočník vydává se za někoho jiného (např. banku), aby získal důvěru oběti
 - Většinou se jedná o e-maily, které vypadají, že jsou od známé společnosti
 - Jdou rozeznat podle domény, ze které e-mail přišel, např `@gmail.com` místo domény banky
 - https://аpple.com/

### DoS/DDoS
 - Útočník se snaží zahlcovat server velkým množstvím požadavků
 - Server se pak nemůže dostatečně věnovat legitimním požadavkům
 - Server může spadnout nebo být velmi pomalý
 - Útočník může použít botnet, což je síť počítačů, které ovládá
 - Proti botnetu se dá špatně bránit, protože útočník může mít k dispozici velké množství počítačů

### Nedostatečná sanetizace uživatelského vstupu - XSS, SQLi, ...
 - Útočník se snaží vložit do aplikace škodlivý kód
 - Kód může být například JavaScript, který se spustí v prohlížeči oběti - XSS
 - Útočník může získat citlivé informace, například cookies na webové stránce
 - XSS (Cross Site Scripting) je útok, kdy útočník vloží do webové stránky škodlivý kód, který se spustí v prohlížeči oběti
 - SQLi (SQL Injection) je útok, kdy útočník vloží do SQL dotazu škodlivý kód
 - Útočník může získat citlivé informace, např hesla

### Google dorking
 - Útočník se snaží najít citlivé informace pomocí vyhledávače
 - Útočník používá speciální vyhledávací dotazy, které umožňují najít citlivé informace
 - Například `site:example.com filetype:pdf` najde všechny PDF soubory na doméně `example.com`
 - `inurl: .git` najde všechny stránky, které obsahují `.git` v URL, kde bývá zdrojový kód webové stránky
 - [Cheatsheet](https://gist.github.com/sundowndev/283efaddbcf896ab405488330d1bbc06)

### Malware(malicious software)
 - Škodlivý software, který se snaží způsobit škodu
 - Viry se šíří pomocí souborů
 - https://www.virustotal.com/

#### Typy malwaru
 - Worm
 - Trojan
 - Ransomware
 - Spyware
 - Adware


## Ochrana
 - Aktualizace softwaru
 - Antivirový software
 - Firewall
 - Bezpečná hesla - password manager
 - Dvoufaktorová autentizace
 - Požívat bezpečné a moderní frameworky


## Nástroje

### BurpSuite
 - Program pro analýzu webových aplikací
 - Využívá se pro testování webových aplikací
 - Umožňuje jednoduše upravovat HTTP požadavky a odpovědi


### Wireshark, tcpdump
 - Programy pro analýzu síťového provozu
 - Umožňují zachytávat a analyzovat síťový provoz
 - Wireshark má grafické rozhraní
 - tcpdump je příkazový nástroj

### Nmap/Rustscan
 - Programy pro skenování sítě
 - Nmap je starší a známější
 - Rustscan je novější a rychlejší
 - Umožňují zjistit, které porty jsou otevřené na cílovém stroji
 - Na základě toho lze zjistit, které služby běží na cílovém stroji

### Metasploit
 - Nástroj pro testování zranitelností
 - Umožňuje provádět různé typy útoků
 - Obsahuje velkou databázi zranitelností
 - Umožňuje jednoduše spouštět exploity

### Hydra
 - Nástroj pro útoky typu brute force
 - Umožňuje jednoduše spouštět útoky na hesla
 - Podporuje mnoho protokolů (HTTP, FTP, SSH, ...)
 - Většinou používáme dictionary attack

### Hashcat/John the Ripper
 - Umožňují útoky na hashovaná hesla
 - Podporuje mnoho typů hashů
 - Umožňuje útoky typu brute force, dictionary attack, ...


## Jak si to v rámci zákona vyzkoušet?

### CTF soutěže
 - Capture The Flag
 - Soutěže, kde se účastníci snaží najít řešení různých úkolů
 - Jedná se o simulaci reálných útoků
 - Účastníci se snaží získat vlajku (flag) z cílového stroje
 - Flag je obvykle nějaký textový řetězec (např. `flag{1233456789abcdef}`)

#### Kategeorie
 - Web
 - Crypto
 - Forensics
 - Pwn
 - Reversing
 - Misc