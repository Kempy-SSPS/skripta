# Kryptografie

### Co to je kryptografie?
- Kryptografie je obor, jenž se zabývá šifrováním. V kontextu kybernetické bezpečnosti se využívá k ochraně dat a to tak, že data zašifruje dle vybraného algoritmu.
---
## Šifrování vs Kódování
- Obojí je transformace dat do jiné podoby, avšak ačkoliv se to tak může zdát, opravdu se nejedná o stejnou věc.

### Šifrování
- Pro přeměnu dat je využíván klíč, který dle druhu algoritmu může být buď symetrický nebo asymetrický.
	- **Symetrický** -  jeden klíč pro šifrování a dešifrování - příklady symetrických algoritmů: AES, Caesarova šifra, Vigenerova šifra
	- **Asymetrický** - 2 klíče, veřejný a soukromý - příklady asymetrických algoritmů: RSA, Lizard, ECC

### Kódování
- Jedná se o přepsání dat do jiné podoby pomocí vybraného algoritmu. Při kódování nepotřebujete zadávat žádný klíč a proto případně velmi jednoduché zjistit, co bylo původním obsahem.

- Takto vypadá text "SSPS" zakódovaný pomocí algoritmu Base64 

	```
	U1NQUw==
	```



- Text si můžete zkusit dekódovat pomocí nástroje CyberChef, jenž je dostupný na adrese: 
	https://gchq.github.io/CyberChef/

- Případně si můžete zkusit zakódovat nějaký svůj text.

---

## Hashování
- Jednotná přeměna dat dle předem stanoveného algoritmu. Jedná se tvz o “Otisk prstu” pro data. Hash je neměnný a bude vždy stejný. Všechno má svůj vlastní hash. Jde díky němu ověřovat integritu dat. Příklady hashovacích algoritmů: MD5, SHA512, Blake2
- Hash nelze "dešifrovat", ale lze ho prolomit pomocí takzvaných "rainbow tables", jejichž princip spočívá v tom, že máte dlouhý seznam slov, které zahashujete a výsledný hash porovnáváte s tím, který se snažíte prolomit. Pokud budete mít shodu, tak jste slovo prolomili.

- Příklad hashe MD5: ```769ef95f8741c399409e69b409e7f808```
- Hash jako takový sám o sobě nelze dešifovat, můžete ho však prolomit pomocí "rainbow tables", o kterých se zmiňuji výše. Nástroj, tuto možnost prolomení pomocí rainbow tables nabízí je dostupný i ve webovém prostředí je například https://crackstation.net/
- Při zadání výše zmíněného MD5 hashe zjistíte, že pod hashem se krývá slovo "SSPS".


---

### Programování
- V této části probereme základy programování

- **Algoritmizace** - velmi důležitá v programování je algoritmizace. Jedná se o sadu pokynů, kterými se program řídí. Bez schopnosti tvorby algoritmů nemůžeme napsat kvalitní kód.

- jednoduchý algoritmus napsaný v "pseudokódu"
```bash
Vstup: heslo
Pokud heslo == 1234:
    Vypiš "Správné heslo"
Jinak:
    Vypiš "Špatné heslo"
```


- **Datové typy** - každý programovací jazyk má v sobě zabudované základní datové typy, mezi nejzákladnější patří:

	int - celá čísla

	double - desetinná čísla

	string - textové řetězce

	char - jeden znak

	bool - true/false

- **Syntaxe** - každý programovací jazyk má svou syntaxi, jedná se o sadu pravidel, při jejímž porušení nebude program fungovat. Například v programovacím jazyce C# vše musí končit ";" takže jednoduchý příkaz na vypsání textu do konzole bude vypadat takto:

	```c
	Console.WriteLine("Hello world");
	```

- Nyní si zkusíme vytvořit velmi jednoduchý C# program, který bude zdravit uživatele
	 - **//** = V C# značí komentář

```c
Console.WriteLine("Zadej své jméno: "); //Požádá uživatele o zadání jména
string name = Console.ReadLine(); //Načte jméno do proměnné name
Console.WriteLine("Ahoj " + name); //Napíše "Ahoj " a obsah proměnné name
```


- V Pythonu by stejný program vypadal zase takto:

```python
name = input("Zadej své jméno: ")
print("Ahoj " + name)
```

- Toto je velmi jednoduchý program, který pozdraví uživatele. Nyní si vytvoříme kalkulačku ve které si představíme funkci while a if

```c
while (true) //Program se bude stále opakovat
{
    Console.WriteLine("Kalkulačka V1");
    Console.WriteLine("Chcete sčítat (+) nebo odčítat (-)?");
    string input = Console.ReadLine(); //Načte uživatelský vstup

    if (input == "+") //Pokud je uživatelný vstup roven "+", čísla se budou sčítat
    {
        Console.WriteLine("Zadejte první číslo: ");
        string numberOne = Console.ReadLine();
        Console.WriteLine("Zadejte druhé číslo: ");
        string numberTwo = Console.ReadLine();

        double numberOneParsed = Convert.ToDouble(numberOne); //V případě, že bychom proměnou nechali jako datový typ string, tak by výsledkem součtu čísel například 1 + 1 bylo "11". Proto vytvoříme novou proměnou, která bude obsahovat hodnotu jako uživatelský vstup, ale bude typu double
        double numberTwoParsed = Convert.ToDouble(numberTwo);

        double result = numberOneParsed + numberTwoParsed; //Sečte proměnné a výsledek zapíše do proměnné result
        Console.WriteLine("Výsledek součtu čísel je: " + result); //Vypíše výsledek a vrátí se na začátek

    }
    else if (input == "-") //Pokud je uživatelný vstup roven "-", čísla se budou odčítat
    {
        Console.WriteLine("Zadejte první číslo: ");
        string numberOne = Console.ReadLine();
        Console.WriteLine("Zadejte druhé číslo: ");
        string numberTwo = Console.ReadLine();

        double numberOneParsed = Convert.ToDouble(numberOne);
        double numberTwoParsed = Convert.ToDouble(numberTwo);

        double result = numberOneParsed - numberTwoParsed; //Odečte proměnné a výsledek zapíše do proměnné result
        Console.WriteLine("Výsledek rozdílu čísel je: " + result); 
    }
    else
    {
        Console.WriteLine("Neplatný vstup"); //V případe, že by uživatel zadal něco jiného než "+" nebo "-", bude jeho vstup vyhodnocen jako neplatný a vrátí se na začátek
    }
}
```
