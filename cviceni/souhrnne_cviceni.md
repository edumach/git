
# Zkouška Git a GitLab

- Prostředí: servery `tux.panska.cz` a `gitlab.panska.cz`
- Cíl: Vytvořit repozitář Git, odeslat jej na GitLab a provést jejich obousměrnou synchronizaci.
- Délka: max. 50 minut
- Počet dílčích úloh: 13 (každá 0, 1 nebo 2 body). 
- Celkem: max. 26 bodů.

---

## Požadavky na zkoušku

- Linux a Git v terminálu
- Běžné činnosti v terminálu bash (ls, cd, mkdir, nano)
- Nastavení údajů uživatele
- Vytvoření Git repozitáře
- stage
- commity
- Výpis stavu a logů GitLab (na `gitlab.panska.cz` i v terminálu)
- ssh klíče
- remote, push, pull


---

# Git

Ve svém home adresáři na serveru TuX založte nový git repozitář s názvem `rostliny`. 

**(1)** Vytvořte soubor `stromy.txt` s tímto obsahem:

```
Dub
Buk
Javor
```

⬆️ Dokončete commitem: „Založení projektu“

---

**(2)** Vytvořte soubor `README.md` s tímto obsahem:

```
# Rostliny
Tento tento repozitář obsahuje seznam rostlin:
```

⬆️ Dokončete commitem: „Přidání README“

---

**(3)** Vytvořte soubor `kvetiny.txt` s následujícím obsahem:

```
Růže
Slunečnice
Tulipán
```

⬆️ Dokončete commitem: „Přidání seznamu květin“

---

**(4)** Vytvořte soubor `rostliny.txt` a přidejte tento obsah:

```
Seznam rostlin
--------------
- stromy
- květiny
```

⬆️ Dokončete commitem: „Vytvoření souhrnného seznamu“

---

**(5)** Do souboru `README` přidejte na konec tento text (vaše jméno a příjmení):

```
Autor: Jméno Příjmení
Dokončete commitem: „Doplnění README“
```

---

**(6)** Do souborů `stromy` i `kvetiny` připište další tři položky.

⬆️ Dokončete commitem: „Doplnění seznamů“

---

**(7)** Vytvořte adresář `img` a stáhněte do něj tento soubor:

```
$ wget https://obrazky.edumach.cz/tulips.jpg
```

Zkontrolujte, zda tam je: `~/rostliny/img/tulips.jpg`

⬆️ Dokončete commitem: „Přidán obrázek tulipánu“

---

**(8)** Do souboru README přidejte text a odkaz na obrázek:

```
## Obrázek tulipánu
![Tulipán](https://obrazky.edumach.cz/tulips.jpg)
```

⬆️ Dokončete commitem: „Do README přidán obrázek tulipánu“


# GitLab (`gitlab.panska.cz`)


**(9)** Napojte tento repozitář (rostliny) na svůj GitLab repozitář a pod stejným názvem jej tam odešlete. Ověřte si na svém GitLabu.

Pozn: e-mail lokálního i vzdáleného repozitáře musí být stejný!

---

**(10)** Do souboru README pod svůj podpis  nepište dnešní datum

⬆️ Dokončete commitem: „Do README přidán datum“

---

**(11)** Aktualizujte (odešlete) změny repozitáře i na GitLab

---

**(12)** Editujte soubor `README` na GitLabu (*Edit → Edit single file*) a na jeho konec přidejte text:

```
---
Upraveno na GitLabu
Uložte s Commitem „Úprava na GitLabu“ 
```

---

**(13)** Aktualizujte lokální repozitář o změny provedené na GitLabu.

---

## Odevzdání a hodnocení: 

Oba repozitáře nechte tam, kde jsou.

```
24 – 26 bodů .. 1
19 – 23 bodů .. 2
13 – 22 bodů .. 3
8 – 12 bodů ..  4
0 – 7 bodů ..   5
```