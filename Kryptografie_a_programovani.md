# Kryptografie
- Obor zabývající se šifrováním
- V kontextu kybernetické bezpečnosti využívána k ochraně dat - zašifrování dle vybraného algoritmu

## Šifrování vs Kodovani
- Oboje transformace dat do jiné podoby
- Ačkoliv se to tak může zdát, opravdu se nejedná o stejnou věc

## Šifrování
- Pro přeměnu dat využíván klíč
- Klíč dle druhu algoritmu buď symetrický nebo asymetrický
	- **Symetrický**
    	- Jeden klíč pro šifrování a dešifrování
    	- Příklady symetrických algoritmů: AES, Caesarova šifra, Vigenèrova šifra
	- **Asymetrický**
    	- 2 klíče - veřejný (sloužící k zašifrování) a soukromý (sloužící k dešifrování)
    	- Příklady asymetrických algoritmů: RSA, Lizard, ECC

## Kódování
- Reprezentace dat dle předem stanoveného kódu
- Při kódování není zadáván žádný klíč -> velmi jednoduché zjistit původní obsah
- Text "SSPS" zakódovaný pomocí Base64:

	```
	U1NQUw==
	```

- Nástroje pro kódování a dekódování: 
    - https://gchq.github.io/CyberChef/
    - https://www.dcode.fr/en


## Hashovací funkce
- Jednosměrná matematická funkce
- Hash
  - Výsledek hashovací funkce po zadání vstupních dat
  - Jedná se tzv. o “Otisk prstu” dat
  - Neměnný a unikátní (může se však stát tzv. kolize)
  - Kolize - jeden hash náleží dvěma různým vstupním datům (stává se zřídka)
- Příklady hashovacích funkcí: md5, SHA512, Blake2
- Příklady využití: integrita dat, zabezpečení hesel
- Nelze dešifrovat, ale lze ho prolomit pomocí takzvaných "rainbow tables" (dlouhý seznam slov, která se zahashují a výsledný hash je porovnán)
- Příklad hashe MD5: ```769ef95f8741c399409e69b409e7f808``` (vstupní data - slovo "SSPS" )
- Nástroje na prolomení (cracknutí) hashů: Hashcat, JohnTheRipper, https://crackstation.net/


# Programování
- **Algoritmizace** - sadu pokynů, kterými se program řídí
- Bez schopnosti tvorby algoritmů nemůžeme napsat kvalitní kód.
- Jednoduchý algoritmus napsaný v pseudokódu:
```python
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

- **Syntaxe** - sada pravidel, při jejímž porušení nebude program fungovat (např. v C# vše musí končit ";")
- Jednoduchý příkaz na vypsání textu do konzole v C#:

	```c#
	Console.WriteLine("Hello world");
	```

- Nyní si zkusíme vytvořit velmi jednoduchý C# program, který bude zdravit uživatele
	 - **//** = V C# značí komentář

```c#
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

```c#
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
- **For loop**
- For loop umožnuje opakovat stejnou část kodu. Počet opakování je takový, jaký si naprogramujete.
- Nyní si napíšeme jednoduchý program, který vypíše 10 čísel od 0-9
  
```
for (int i = 0; i < 10; i++)
            {
            Console.WriteLine(i);
            }
```
- **Metody**
- Metoda je kus kódu, který lze využívat opakovaně, takže zjednodušeně řečeno nemusím psát furt ten stejný kód dokola, mohu pouze vyvolat metodu.
- Nyní si zkusíme napsat stejný zdravící program jako víše, ale s využitím metod
```
using System;

namespace Zdravic
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Zadej své jméno: ");
            string name = Console.ReadLine();
            Pozdrav(name);
            Console.ReadKey();
        }

        static void Pozdrav(string jmeno)
        {
            Console.WriteLine("Ahoj " + jmeno);
        }
    }
}

```
