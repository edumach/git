
# Git cvičení – konflikt ve webové stránce

> max 30 minut

---

Ve svém home adresáři na serveru TuX založte Git repozitář `konflikt2`

---

(1) Vytvoření souborů

Vytvořte soubory `index.html` a `styly.css`:

- `index.html`

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>Moje stránka</title>
    <link rel="stylesheet" href="styly.css">
    </head>
    <body>

    <h1>Moje stránka</h1>

    <p class="info">Vítejte na mé webové stránce.</p>

    </body>
    </html>
    ```

- `styly.css`

    ```css
    body {
    font-family: Arial;
    }

    .info {
    color: blue;
    }
    ```

⬆️ Commit: "základní webová stránka"

---

**(2)** Vytvoření nové větve

Vytvořte větev `upravy` a přepněte se na ni.

---

**(3)** Úprava ve větvi `upravy`

Proveďte změny:

- V souboru `index.html` změňte text odstavce:

    ```html
    <p class="info">Vítejte na mé upravené stránce.</p>
    ```

- V souboru `styly.css` změňte barvu:

    ```css
    .info {
    color: green;
    }
    ```

⬆️ Commit: "změna textu a barvy na zelenou"

---

**(4)** Úprava v hlavní větvi (povede ke konfliktu)

Přepněte zpět na hlavní větev.

Proveďte jiné úpravy **na stejném místě**:

- `index.html`

    ```html
    <p class="info">Toto je moje osobní prezentace.</p>
    ```

- `styly.css`

    ```css
    .info {
    color: red;
    }
    ```

⬆️ Commit: "jiná úprava textu a barvy"

---

**(5)** Merge (s konfliktem)

V hlavní větvi proveďte:

```bash
$ git merge upravy
```

Git nahlásí konflikt (typicky v obou souborech).

---

**(6)** Řešení konfliktu

Otevřete konfliktní soubory a upravte je například takto:

- `index.html`

    ```html
    <p class="info">Vítejte na mé osobní upravené stránce.</p>
    ```

- `styly.css`

    ```css
    .info {
    color: purple;
    }
    ```

⬆️ Poté dokončete merge s commitem: "vyřešen konflikt – kombinace úprav"

---

**Dokončení**

* Zkontrolujte historii:

    ```bash
    $ git log --oneline --graph
    ```

* Výsledek zůstává na serveru TuX.

