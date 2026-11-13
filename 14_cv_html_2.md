

# Git: cvičení HTML 2 (TuX)

> max 30 minut

**⚙️ Příprava** 

- Přihlaste se na server Tux. 
- Vytvořte adresář `~/www/git_html1`.
- Přesuňte se do něj.
- Další činnosti provádějte v tomto adresáři.

---

Vytvořte z něho Git repozitář.

---


**(1)** Základní struktura

Vytvořte soubor `index.html` s následujícím obsahem:

```html
<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <title>Moje Vizitka</title>
</head>
<body>
    <h1>Jan Novák</h1>
    <p>Vítejte na mé digitální vizitce. Jsem studentem střední školy.</p>
</body>
</html>
```
⬆️ Vytvořte první commit s komentářem: "založení vizitky".

---

**(2)** Dokumentace a styly
- Přidejte soubor `README.md` s obsahem:
   ```
   # Osobní vizitka
   Tento projekt je ukázkou základní HTML stránky s využitím Gitu.
   ```
- Přidejte soubor `design.css` s obsahem:
   ```css
   body {
       font-family: Arial, sans-serif;
       background-color: #f0f0f0;
       color: #333;
   }
   h1 {
       color: darkgreen;
       border-bottom: 2px solid darkgreen;
   }
   ```
⬆️ Vytvořte commit s komentářem: "přidání info a css souborů".

---

**(3)** Propojení souborů

Do souboru `index.html` přidejte pod řádek s titulkem odkaz na kaskádové styly:

```html
<link rel="stylesheet" href="design.css">
```

⬆️ Vytvořte commit s komentářem: "propojení s design.css".

---

**(4)** Rozšíření obsahu HTML

Do souboru `index.html` přidejte pod stávající odstavec seznam svých zájmů:

```html
<ul>
    <li>Programování</li>
    <li>Sport</li>
    <li>Hudba</li>
</ul>
```
⬆️ Vytvořte commit s komentářem: "přidání seznamu zájmů".

---

**(5)** Aktualizace informací

Do souboru `README.md` přidejte na konec sekci s kontaktem (nahraďte skutečnou adresou):

```
## Kontakt
Email: 10XPrijmeniJ@student.panska.cz
```

⬆️ Vytvořte commit s komentářem: "aktualizace kontaktu v README".


---

**Dokončení** 

- Pro kontrolu si vypište log commitů. 
- Výsledek si zkontroluji přímo na serveru TuX. Nikam nic neposílejte. 
