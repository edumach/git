

# Větve

```
git branch
git switch
git merge
```

<img src="img/branch.png" width="600">

Git podporuje práci ve více větvích. Ty umožní pracovat na různých částech projektu, jako jsou nové funkce nebo opravy chyb.

Typické důvody pro vytvoření větve:

- Vývoj nové funkce
- Oprava chyby
- Experimentování s nápady

**Příklad:** Řekněme, že máte webový projekt většího rozsahu a potřebujete na něm aktualizovat obsah i vzhled. Jak by to fungovalo bez Gitu a s Gitem:

Bez Gitu:

- Vytvoříte si kopie všech souborů, které chcete upravit.
- Začněte pracovat a zjistěte, že kód závisí na kódu v jiných souborech, které je také potřeba změnit!
- Uděláte si také kopie těchto závislých souborů.
- URGENTNÍ OPRAVA! Někde jinde v projektu je nesouvisející chyba, kterou je třeba co nejdříve opravit!
- Uložíte si všechny soubory a poznamenáte si názvy kopií, na kterých jste pracovali.
- Pracujte na nesouvisející chybě a aktualizujte kód, abyste jej opravili.
- Vrátíte se k návrhu a dokončíte práci tam.
- Zkopírujete kód nebo přejmenujete soubory, aby aktualizovaný kód byl v živé verzi.
- Po dvou týdnech si uvědomíte, že nesouvisející chyba nebyla opravena v nové verzi, protože jste soubory zkopírovali před opravou.


S Gitem:

- U nové větve nazvané `novy-vzhled` upravujte kód přímo, aniž byste ovlivnili hlavní větev.
- URGENTNÍ OPRAVA! Někde jinde v projektu je nesouvisející chyba, kterou je třeba co nejdříve opravit!
- Vytvoříte **novou větev** z hlavního projektu nazvanou `mala-oprava`.
- Opravíte nesouvisející chybu a sloučíte větev s malou opravou chyby s hlavní větví.
- Vrátíte se do větve pro nový design a dokončíte tam práci.
- Sloučíte větev nového designu s hlavní (v commitu upozorníte na malou opravu chyby, kterou jste přehlédli).


**Větve vám umožní pracovat na různých částech projektu, aniž byste ovlivnili hlavní větev.**


Výpis větví:

```bash
$ git branch
```

Aktivní větev má před názvem `*`. Výchozí a zatím jedinou větví je `main` (nebo `master`).


Vytvoření větve:

```bash
$ git branch nova-funkce
```

Přepnutí do větve:

```bash
$ git checkout nova-funkce
```

Nebo vše jedním píkazem - vytvoření a okamžité přepnutí:

```bash
$ git checkout -b nova-funkce
```

## Sloučení větví

⚠️ Pravidlo: Vždy se slučuje **jiná větev do aktivní**. V příkladu níže **z** větve `nova-funkce` **do** větve `main`.

<img src="img/merge.png" width="600">


Nejprve přepnutí:

```bash
$ git checkout main
```

Poté sloučení:

```bash
$ git merge --no-ff nova-funkce
```

Přepínač `--no-ff` (*No fast-forward* - vysvětlení je níže) je vhodný pro naše výukové účely. Zachová viditelnost ve výpisu historie `git log`.

## Smazání větve

```bash
$ git branch -d nova-funkce
```

## Log včetně grafu větví

```bash
$ git log --oneline --graph --all
```
Ukáže vývoj větví a jejich spojování.


# Tři možné stavy slučování

Příkaz `git merge` vždy skončí **jedním** z těchto tří stavů:

1. **Fast forward** - Změny byly provedeny pouze ve vedlejší větvi. Sloučením se pouze posune ukazatel `HEAD` podle nejnovějšího commitu.

2. **True merge** - Změny byly provedeny jak v hlavní, tak vedlejší větvi. Sloučení je spojí - zahrne změny z obou větví.

3. **Aborted merge** - Změny byly provedeny jak v hlavní, tak vedlejší větvi. Sloučení ovšem selže, neboť minimálně jedna změna se týká **stejného řádku kódu souboru jak v hlavní, tak vedlejší větvi**. Git nemůže rozhodnout, kterou z těch změn má zachovat a kterou zahodit. Tím vznikne tzv. "konflikt" **Konflikt není chyba**. Git pouze potřebuje, aby uživatel rozhodl, která verze obsahu má být zachována.




Co s tím je v další kapitole.
