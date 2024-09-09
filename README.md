# PVA2 - Programování a vývoj aplikací
## Co umím z PVA1

Čas na odevzdání není omezen. Úkoly jsou však jednoduché, a měli by jste je zvládnout do 45 minut.
Potřebujete-li více času, neváhejte se na něj zeptat. Opakování není na známky. Vypracujte jej sami, bez cizí pomoci, bez použití internetu a nástrojů.


## Obsah

# Vstupní data
```python
poptavka = [
    {"nazev": "Firma A", "odvetvi": "automotive", "obrat": 50, "zeme": "CZ", "konference": True, "newsletter": True},
    {"nazev": "Firma B", "odvetvi": "retail", "obrat": 500, "zeme": "SK", "konference": False, "newsletter": True},
    {"nazev": "Firma C", "odvetvi": "automotive", "obrat": 5, "zeme": "DE", "konference": True, "newsletter": False},
    {"nazev": "Firma D", "odvetvi": "retail", "obrat": 1500, "zeme": "FR", "konference": False, "newsletter": False},
    {"nazev": "Firma E", "odvetvi": "automotive", "obrat": "20", "zeme": "CZ", "konference": True, "newsletter": True},
    {"nazev": "Firma F", "odvetvi": "retail", "obrat": 800, "zeme": "SK", "konference": False, "newsletter": True},
    {"nazev": "Firma G", "odvetvi": "automotive", "obrat": 2000, "zeme": "DE", "konference": True, "newsletter": False},
    {"nazev": "Firma H", "odvetvi": "retail", "obrat": 50, "zeme": "FR", "konference": False, "newsletter": False},
    {"nazev": "Firma I", "odvetvi": "automotive", "obrat": "100", "zeme": "CZ", "konference": True, "newsletter": True},
    {"nazev": "Firma J", "odvetvi": "retail", "obrat": 300, "zeme": "SK", "konference": False, "newsletter": True}
    {"nazev": "Firma K", "odvetvi": "finance", "obrat": 200, "zeme": "CZ", "konference": True, "newsletter": True},
    {"nazev": "Firma L", "odvetvi": "healthcare", "obrat": 700, "zeme": "SK", "konference": False, "newsletter": True},
    {"nazev": "Firma M", "odvetvi": "technology", "obrat": 1200, "zeme": "DE", "konference": True, "newsletter": False},
    {"nazev": "Firma N", "odvetvi": "education", "obrat": 300, "zeme": "FR", "konference": False, "newsletter": False},
    {"nazev": "Firma O", "odvetvi": "energy", "obrat": 900, "zeme": "CZ", "konference": True, "newsletter": True}
]
```

# Hodnocení zakázky

Obchodníci v naší softwarové firmě používají jednoduchý systém, aby odhadli šanci na úspěch potenciální zakázky.
  
Každé zakázce přiřadí body od 0 do 10 a platí:
* Pokud má zakázka méně než 5 bodů, šance na záskání je `malá`.
* Pokud má zakázka 6 až 8 bodů, šance na získání je `střední`.
* Pokud má zakázka více bodů, šance na získání je `vysoká`.

Body přidělují podle následujících kritérií:
* Odvětví `odvetvi`: Firma nejlépe prodává do `automotive`, o něco hůře do `retail`.
Pokud potenciální zákazník podniká v `automotive`, přičti 3 body, pokud v `retail`,
   přičti 2 bod, jinak 0.
* Obrat `obrat`: Firma nejlépe prodává zákazníkům se středním obratem. U malých většinou neuspěje,
u velkých občas ano. Pokud má firma obrat menší než 10 mil. Euro, přičti `0` bodů. Pokud je mezi
  10 a 1 000 mil. Euro, přičti `3` body, jinak `1` bod.
* Země `zeme`: Firma je nejúspěšnější v `CZ` Česku a na `SK` Slovensku (2 body), o něco méně v `DE` Německu a ve `FR` Francii (1 bod).
  Ostatním zemím dej `0`.
* Konference `konference`: Firma loni pořádala odbornou konferenci pro zákazníky. Pokud se zákazník konference
účastnil, přičti 1 bod, jinak 0.
* Newsletter `newsletter`: Firma též rozesílá newsletter o svém produktu. Pokud zákazník newsletter odebírá,
přičti 1 bod.
  
Deklaruj funkci `odhad_sance`, které bude mít 5 parametrů, které reprezentují zadaná kritéria. Poslední dvě
kritéria zadej jako nepovinná s výchozí hodnotou `False`. Funkce vrátí šanci na získání zakázky
jako řetězec.

Seznam poptávek nám přepsal juniorní developer. Před použitím dat je třeba je zkontrolovat a případně opravit.

## Výstupy


- Vypočítej šanci na získání zakázky pro všechny firmy v `poptavka` a vypiš je na obrazovku.
- Vypočítejte průměrný počet bodů pro všechny firmy v `poptavka` a vypište ho na obrazovku.
- Jaká firma má největší šanci na získání zakázky? Vypište její název na obrazovku.
- Seřaďte firmy sestupně podle šance na získání a zobrazte první tři.

### Očekávaný výstup
```
Firma Firma A má šanci na získání zakázky: vysoká (body: 10)
Firma Firma B má šanci na získání zakázky: střední (body: 8)
Firma Firma C má šanci na získání zakázky: vysoká (body: 5)
Firma Firma D má šanci na získání zakázky: malá (body: 4)
Firma Firma E má šanci na získání zakázky: vysoká (body: 9)
Firma Firma F má šanci na získání zakázky: střední (body: 8)
Firma Firma G má šanci na získání zakázky: střední (body: 6)
Firma Firma H má šanci na získání zakázky: střední (body: 6)
Firma Firma I má šanci na získání zakázky: vysoká (body: 10)
Firma Firma J má šanci na získání zakázky: střední (body: 8)
Firma Firma K má šanci na získání zakázky: střední (body: 7)
Firma Firma L má šanci na získání zakázky: střední (body: 6)
Firma Firma M má šanci na získání zakázky: malá (body: 3)
Firma Firma N má šanci na získání zakázky: malá (body: 4)
Firma Firma O má šanci na získání zakázky: střední (body: 7)

Průměrný počet bodů pro všechny firmy: 6.73

Firma s největší šancí na získání zakázky: Firma A

První tři firmy seřazené podle šance na získání zakázky:
Firma Firma A má šanci na získání zakázky: vysoká (body: 10)
Firma Firma I má šanci na získání zakázky: vysoká (body: 10)
Firma Firma E má šanci na získání zakázky: vysoká (body: 9)
```