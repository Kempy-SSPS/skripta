# Kryptografie
- Obor zabývající se šifrováním
- V kontextu kybernetické bezpečnosti využívána k ochraně dat - zašifrování dle vybraného algoritmu

## Šifrování vs Kódování
- Oboje transformace dat do jiné podoby
- Ačkoliv se to tak může zdát, opravdu se nejedná o stejnou věc

## Šifrování
- Pro přeměnu dat využíván klíč
- Klíč je dle druhu algoritmu buď symetrický nebo asymetrický
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
## Algoritmizace
- sadu pokynů, kterými se program řídí
- Bez schopnosti tvorby algoritmů nemůžeme napsat kvalitní kód.
- Jednoduchý algoritmus napsaný v pseudokódu:
    ```python
    Vstup: heslo
    Pokud heslo == 1234:
        Vypiš "Správné heslo"
    Jinak:
        Vypiš "Špatné heslo"
    ```

## Datové typy
- každý programovací jazyk má v sobě zabudované základní datové typy
- nejzákladnější datové typy:
	
    ```
    int - celá čísla
	
    double - desetinná čísla
	
    string - textové řetězce
	
    char - jeden znak
	
    bool - true/false
    ```
## Syntaxe
- **Syntaxe** - sada pravidel, při jejímž porušení nebude program fungovat (např. v C# vše musí končit ";")
- Jednoduchý kód pro vypsání textu do konzole 
  - v jazyce Python
  
    ```python
    print("Hello, World!") 
    ```
  
  - v jazyce C#
  
    ```c#
    Console.WriteLine("Hello world");
    ```

## Komentáře

- Část kódu, která se nevykonává, ale slouží k vysvětlení kódu, jeho zpřehlednění, či k zapsání poznámek (např. TODO)
- Komentáře v Pythonu

    ```python
    # Toto je   komentář

    """
    Toto je komentář
    na více řádků
    """
    ```

- Komentáře v C#

    ```c#   
    // Toto je komentář
    
    /*
    Toto je komentář
    na více řádků
    */
    ```

- Jednoduchý program, který bude zdravit uživatele
  - v jazyce Python
  
    ```python
    name = input("Zadej své jméno: ")
    print("Ahoj " + name)
    ```
  
  - v jazyce C#

    ```c#
    Console.WriteLine("Zadej své jméno: "); //Požádá uživatele o zadání jména
    string name = Console.ReadLine(); //Načte jméno do proměnné name
    Console.WriteLine("Ahoj " + name); //Napíše "Ahoj " a obsah proměnné name
    ```

## Podmínky (if/else statements)
- Umožňují vykonat část kódu, pokud je splněna určitá podmínka
- Příklad if/else statementu
  - v jazyce Python

    ```python
    # if, else if, else
    age = 18
    if age >= 18:
        print("Jsi dospělý")
    else if age > 65:
        print("Jsi důchodce")
    else:
        print("Jsi dítě")
    ```

  - v jazyce C#

    ```c#
    int age = 18;
    if (age >= 18)
    {
        Console.WriteLine("Jsi dospělý");
    }
    else if (age > 65)
    {
        Console.WriteLine("Jsi důchodce");
    }
    else
    {
        Console.WriteLine("Jsi dítě");
    }
    ```

## Cykly (for/while loops)
### For loop
- Umožnuje opakovat stejnou část kodu po stanovenou dobu
- Příklad for loopu
  - v jazyce Python

    ```python
    for i in range(10):
        print(i)
    ```

    - v jazyce C#

    ```c#
    for (int i = 0; i < 10; i++)
    {
        Console.WriteLine(i);
    }
    ```

### While loop
- Opakuje část kódu, dokud je splněna určitá podmínka
- Příklad while loopu
  - v jazyce Python

    ```python
    i = 0
    while i < 10:
        print(i)
        i += 1
    ```

    - v jazyce C#

    ```c#
    int i = 0;
    while (i < 10)
    {
        Console.WriteLine(i);
        i++;
    }
    ```

## Pole (arrays)
- Umožňuje ukládat více hodnot do jedné proměnné
- Příklad pole
  - v jazyce Python

    ```python
    pole = [1, 2, 3, 4, 5]
    print(pole[0]) #Vypíše první prvek pole
    print(pole[3]) #Vypíše čtvrtý prvek pole
    print(len(pole)) #Vypíše délku pole
    ```

    - v jazyce C#

    ```c#
    int[] pole = {1, 2, 3, 4, 5};
    Console.WriteLine(pole[0]); //Vypíše první prvek pole
    Console.WriteLine(pole[3]); //Vypíše čtvrtý prvek pole
    Console.WriteLine(pole.Length); //Vypíše délku pole
    ```

## Metody/funkce
- Kus kódu, který lze využívat opakovaně (stačí ji zavolat a ona se vykoná, zavolat ji lze opakovaně)
- Program pozdravení s využitím metody/funkce
    - v jazyce Python

    ```python
    def pozdrav(name):
        print("Ahoj " + jmeno)
    
    print("Zadej své jméno: ")
    name = input()
    pozdrav(name)
    ```

    - v jazyce C#

    ```c#
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


## Jednoduchá kalkulačka
- V jazyce Python

```python
while True: #Program se bude stále opakovat- Jednoduchá kalkulačka za použití while loopu a if/else statementů
    print("Kalkulačka V1")
    print("Chcete sčítat (+) nebo odčítat (-)?")
    input = input() #Načte uživatelský vstup

    if input == "+": #Pokud je uživatelný vstup roven "+", čísla se budou sčítat
        numberOne = input("Zadejte první číslo: ")
        numberTwo = input("Zadejte druhé číslo: ")
        result = int(numberOne) + int(numberTwo) #Sečte proměnné a výsledek zapíše do proměnné result
        print("Výsledek součtu čísel je: " + str(result)) #Vypíše výsledek a vrátí se na začátek

    elif input == "-": #Pokud je uživatelný vstup roven "-", čísla se budou odčítat
        numberOne = input("Zadejte první číslo: ")
        numberTwo = input("Zadejte druhé číslo: ")
        result = int(numberOne) - int(numberTwo) #Odečte proměnné a výsledek zapíše do proměnné result
        print("Výsledek rozdílu čísel je: " + str(result)) #Vypíše výsledek a vrátí se na začátek

    else:
        print("Neplatný vstup") #V případe, že by uživatel zadal něco jiného než "+" nebo "-", bude jeho vstup vyhodnocen jako neplatný a vrátí se na začátek

```

- V jazyce C#


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
