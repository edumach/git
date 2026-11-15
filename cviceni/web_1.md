
# Git: cvičení HTML 1 (TuX)

> max 30 minut

**⚙️ Příprava** 
- Přihlaste se na server Tux. 
- Vytvořte adresář `~/www/git_html1`.
- Přesuňte se do něj.
- Další činnosti provádějte v tomto adresáři.

---

Vytvořte z něho Git repozitář.

---

**(1)** Vytvořte soubor `index.html` s tímto obsahem: 

```html
<!DOCTYPE html>   
<html lang="cs">   
<head> 
	<meta charset="UTF-8"> 
	<title>Git projekt</title> 
</head> 
<body>   
	<h1>Vítejte v mém Git projektu</h1> 
	<p>Tento projekt slouží k procvičení základů verzování.</p> 
</body> 
</html> 
```

⬆️️ Vytvořte první commit s komentářem “založení projektu”. 

---

**(2)** Přidejte soubor `README.md` s obsahem: 

```
# Můj Git projekt 
Tento projekt slouží k procvičení základních operací s Gitem. 
```

---

**(3)** Přidejte soubor `styly.css` s obsahem: 

```css
body {   
	background-color: lightblue;   
}
h1 {
	color: navy;
	margin-left: 20px;
}
```

⬆️ Vytvořte commit s komentářem “přidání souboru se styly”. 

---

**(4)** Do souboru `index.html` přidejte řádek s odkazem na soubor se styly (pod řádek s titulkem): 

```html
<link rel="stylesheet" href="styly.css"> 
```

⬆️ Vytvořte commit (komentář: “link na styly”) 

---

**(5)** Do souboru `index.html` přidejte další odstavec: 

```html
<p>Nový řádek v mém souboru!</p> 
```

⬆️ Vytvořte commit (komentář: “doplnění souboru index”) 

---

**(6)** Do souboru `README.md` přidejte na konec tento text: 

```
## Autor 
Jméno Příjmení 
```

⬆️ Vytvořte commit (komentář: “doplnění README”) 

---

**Dokončení** 

- Pro kontrolu si vypište log commitů. 
- Výsledek si zkontroluji přímo na serveru TuX. Nikam nic neposílejte. 



