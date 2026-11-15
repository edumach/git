## Čtení historie projektu

```
git show
```


Příkaz:

```bash
$ git show
```

Příkaz zobrazí informace o commitu a také změny, které commit provedl oproti **předchzí verzi** projektu.

Ukázka:

```diff
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

Výpis lze číst po jednotlivých řádcích.

### Název souboru

```diff
--- a/index.html
+++ b/index.html
```

Písmeno `a` označuje starší verzi souboru.

Písmeno `b` označuje novější verzi souboru.

V tomto případě Git porovnává dvě verze souboru `index.html`.

### Přidané řádky

Řádky začínající znakem `+` byly přidány:

```diff
+<title>Ukázkový web</title>
```

Commit přidal značku `<title>`.

### Odebrané řádky

Řádky začínající znakem `-` byly odstraněny:

```diff
-<html>
+<html lang="cs">
```

Git ukazuje, že starý řádek byl nahrazen novým.

### Nezměněné řádky

Řádky bez speciálního znaku slouží pouze jako kontext:

```html
<!DOCTYPE html>
<html lang="cs">
<head>
```

Pomáhají určit, kde se změna nachází.

### Co znamená @@ -1,6 +1,7 @@

Tento řádek bývá pro začátečníky matoucí:

```diff
@@ -1,6 +1,7 @@
```

Udává, ve které části souboru se změna nachází.

```text
-1,6
```

Ve staré verzi se zobrazí 6 řádků od řádku 1.

```text
+1,7
```

V nové verzi se zobrazí 7 řádků od řádku 1.

Protože byl přidán jeden nový řádek (`<title>`), zvýšil se počet řádků z 6 na 7.

Pro běžnou práci není nutné tento zápis detailně studovat. Většinou stačí sledovat řádky označené znaky `+` a `-`.

### Shrnutí symbolů

| Symbol | Význam |
|---------|---------|
| `+` | přidaný řádek |
| `-` | odstraněný řádek |
| bez symbolu | nezměněný kontext |
| `@@` | umístění změny v souboru |


## Praktický postup při hledání změn

Nejprve si zobrazte historii:

```bash
git log --oneline
```

Například:

```text
e566ffc Přidaný titulek webu
d5777d1 Vytvoření externího CSS
e20ee59 Lokalizace webu do CZ
d747969 První verze webu
```

Poté můžete zobrazit detail konkrétního commitu:

```bash
git show e566ffc
```

Git vypíše:

- autora změny,
- datum a čas vytvoření,
- zprávu commitu,
- seznam změněných souborů,
- přidané a odstraněné řádky.

To je často nejrychlejší způsob, jak zjistit:

- kdo změnu provedl,
- kdy ji provedl,
- proč ji provedl,
- které části projektu upravil.


