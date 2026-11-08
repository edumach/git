
# Výpis historie commitů a porovnání změn

```
git log
git diff
git show
```

---

## Výpis historie commitů

Pro zobrazení historie commitů v repozitáři můžete použít příkaz:


```bash
git log
```

Výpisy mohou být delší. Pro posun použijte šipky na klávesnici. Pro ukončení klávesu **Q** (Quit).

Každý commit je identifikovaný unikátním 40 znakovým **commit hashem**. Dále je u něj jméno, e-mail autora a časové razítko. Pro jednoznačnou identifikaci **stačí prvních 7 znaků**.

Pro běžné potřeby stačí jednořádkový výpis:

Zkrácená historie:

```bash
git log --oneline
```

Příklad a vysvětlení:

```
macOS ~/Documents/web-git
$ git log --oneline
e566ffc (HEAD -> main) Přidaný titulek webu
d5777d1 Vytvoření externího CSS
e20ee59 Lokalizace webu do CZ
d747969 První verze webu
```


- `HEAD` .. aktuální verze projektu.
- `main` .. název větve.
- `e566ffc` .. prvních 7 znaků commit hashe.

---

## Porovnání změn

### Změny oproti poslednímu commitu

```bash
$ git diff
```

Příklad:

```
diff --git a/style.css b/style.css
index 0a9cefb..68c6455 100644
--- a/style.css
+++ b/style.css
@@ -9,5 +9,5 @@ h1 {

 p {
   font-family: verdana;
-  font-size: 20px;
+  font-size: 22px;
 }
```

Tento příkaz ukazuje změny, které jste provedli, ale ještě nejsou připravené ke commitování.


### Porovnání dvou commitů

Podívejte se, co se změnilo mezi dvěma commity:

```bash
$ git diff <commit1> <commit2>
```


```
macOS ~/Documents/web-git
$ git log --oneline
e566ffc (HEAD -> main) Přidaný titulek webu
d5777d1 Vytvoření externího CSS
e20ee59 Lokalizace webu do CZ
d747969 První verze webu
```

Toto vypsal `git log`. Porovnáme commit `d747969` s commitem `e20ee59` příkazem:

```bash
$ git diff d747969 e20ee59
```

Výsledek může být např. takovýto:

```
diff --git a/README.md b/README.md
index e69de29..be919b5 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,3 @@
+# Projekt web-git
+
+Autor: Jméno Příjmení
diff --git a/web.html b/web.html
index 973d812..2683b51 100644
--- a/web.html
+++ b/web.html
@@ -1,5 +1,5 @@
 <!DOCTYPE html>
-<html>
+<html lang="cs">
 <head>
 <style>
 body {
```

Výpis může být na první pohled poněkud nesrozumitelný. Pro jeho pochopení je nutné si jeho výstup prostudovat řádek po řádku.


\section{Výpis změn v souborech}

```bash
$ git show
```

Pokud potřebujete vidět, k jakým změnám došlo v posledním commitu oproti předchozí verzi, spusťte příkaz `git show HEAD`:

```
macOS ~/Documents/web-git
$ git show HEAD
commit e566ffcc3007ce7f9bf76217a8f963c78095d30e (HEAD -> main)
Author: Jiří Machač <machac@panska.cz>
Date:   Tue Dec 13 15:06:04 2024 +0100

    Přidaný titulek webu

diff --git a/index.html b/index.html
index e818a35..0885129 100644
--- a/index.html
+++ b/index.html
@@ -1,6 +1,7 @@
 <!DOCTYPE html>
 <html lang="cs">
 <head>
+<title>Ukázkový web</title>
 <link rel="stylesheet" href="style.css">
 </head>
 <body>
```
