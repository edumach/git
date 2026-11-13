# Rychlý tahák Git

## Nejdůležitější pojmy

| Pojem | Význam |
|---------|---------|
| repozitář | složka spravovaná Gitem |
| commit | uložený stav projektu |
| větev (branch) | samostatná vývojová větev |
| merge | sloučení větví |
| origin | vzdálený repozitář |
| push | odeslání změn na server |
| pull | stažení změn ze serveru |
| GitLab | server pro ukládání Git repozitářů |


## Nejčastější postup

```bash
$ git status
$ git add -A
$ git commit -m "Popis změny"
$ git push
```

---

## Vytvoření repozitáře

```bash
$ cd projekt
$ git init
```

---

## Kontrola stavu

```bash
$ git status
```

---

## Přidání souborů do commitu

Všechny změny:

```bash
$ git add -A
```

Jeden soubor:

```bash
$ git add soubor.txt
```

---

## Vytvoření commitu

```bash
$ git commit -m "Popis změny"
```

---

## Výpis změn oproti předchozímu stavu 

```bash
$ git show
```

---

## Historie projektu

Stručně:

```bash
$ git log --oneline
```

Podrobně:

```bash
$ git log
```

---

## Zrušení neuložených změn

Jeden soubor:

```bash
$ git restore soubor.txt
```

Všechny soubory:

```bash
$ git restore .
```

---

## Větve

Výpis větví:

```bash
$ git branch
```

Vytvoření a přepnutí:

```bash
$ git switch -c nova-vetev
```

Přepnutí:

```bash
$ git switch main
```

Sloučení větve:

```bash
$ git merge nova-vetev
```

---

## Vzdálený repozitář

Kontrola propojení:

```bash
$ git remote -v
```

Stažení změn:

```bash
$ git pull
```

Odeslání změn:

```bash
$ git push
```

---

## SSH

Test připojení:

```bash
ssh -T $ git@gitlab.panska.cz
```

---

## Základní workflow při spolupráci

Před zahájením práce:

```bash
$ git fetch
$ git pull
```

Po dokončení práce:

```bash
$ git add -A
$ git commit -m "Popis změny"
$ git push
```
