
# Řešení konfliktů

Co je konflikt? Konflikt nastane, když Git nedokáže automaticky sloučit změny ze dvou verzí téhož souboru. To se může stát i jednomu uživateli při slučování vlastní větve do hlavní větve. Příklad:

Nejprve vytvoříme novou větev:

```bash
git checkout -b nova-funkce
```

Ve větvi upravíme soubor a změnu uložíme:

```bash
git add -A
git commit -m "Úprava nadpisu"
```

Poté se vrátíme do hlavní větve:

```bash
git checkout main
```

Ve stejném souboru upravíme **stejný řádek jiným způsobem** a vytvoříme commit:

```bash
git add -A
git commit -m "Jiná úprava nadpisu"
```

Nyní se pokusíme větve sloučit:

```bash
git merge nova-funkce
```

Git oznámí konflikt.

Jak vypadá konflikt v souboru?
```
<<<<<<< HEAD
<h1>Školní projekt</h1>
=======
<h1>Nová verze webu</h1>
>>>>>>> nova-funkce
```
část mezi `<<<<<<< HEAD` a `=======` je aktuální verze,
část mezi `=======` a `>>>>>>>` je verze z připojované větve.

Vyřešení konfliktu:

Uživatel rozhodne, který obsah má zůstat, například:

```
<h1>Školní projekt 2026</h1>
```

a odstraní všechny konfliktní značky:

```
<<<<<<<
=======
>>>>>>>
```

Dokončení sloučení:

```bash
git add index.html
git commit -m "Vyřešen konflikt"
```

Zrušení slučování:

Pokud chceme merge zcela zrušit:

```bash
git merge --abort
```

Konflikt není chyba. Git pouze potřebuje, aby uživatel rozhodl, která verze obsahu má být zachována.
