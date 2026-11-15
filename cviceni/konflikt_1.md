
# Git cvičení – text s konfliktem

> max 30 minut

---

Ve svém home adresáři na serveru TuX založte Git repozitář `konflikt1`.

---

**1. Vytvoření souboru**

Vytvořte soubor `sport.txt`:

```
Fotbal
Basketbal
Hokej
```

⬆️ Commit: "základní seznam sportů"

---

**2. Vytvoření nové větve**

Vytvořte větev `upravy` a přepněte se na ní.

--- 

**3. Úprava ve větvi `upravy`**

V souboru `sport.txt` nahraďte řádek `Basketbal` textem:

```
Basketbal (hala)
```

⬆️ Commit: "úprava basketbalu"

---

**4. Úprava v hlavní větvi (povede ke konfliktu)**

Přepněte na větev `main`. Upravte stejný řádek v souboru `sport.txt`, ale jinak:

```
Basketbal – týmová hra
```

⬆️ Commit: "jiná úprava basketbalu"

---

**5. Merge (s konfliktem)**

Proveďte:

```bash
$ git merge upravy
```

Git nahlásí konflikt v souboru `sport.txt`.

Úkol: ručně vyřešte konflikt a vytvořte výslednou verzi řádku například takto:

```
Basketbal (hala, týmová hra)
```

Poté dokončete merge:

```bash
$ git add sport.txt
$ git commit ...
```
---

**Dokončení** 

- Pro kontrolu si vypište log commitů. 
- Výsledek si zkontroluji přímo na serveru TuX. Nikam nic neposílejte.


