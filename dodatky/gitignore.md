
# Soubor `.gitignore`

Soubor `.gitignore` určuje, které soubory Git **nebude sledovat**. Typické použití je pro:

- dočasné soubory,
- logy,
- výsledky kompilace,
- nastavení editorů,
- velké automaticky generované adresáře.



```sh
# Příklad souboru
# ---------------

# Ignoruje soubor 
poznamky.txt

# Ignoruje všechny soubory s příponou .log
*.log

# Ignoruje adresář modules a veškerý její obsah
modules/

# Ignoruje všechny soubory s příponou .log kdekoli
# v repozitáři (v kořenu i v jakékoliv zanořeném adresáři)
**/*.log

# Ignoruje adresář modules a veškerý její obsah na libovolné úrovni
# zanoření (např. modules/, src/modules/, a/b/modules/)
**/modules/
```

Po vytvoření souboru:

```bash
$ touch .gitignore
```

uložíme:

```bash
git add .gitignore
git commit -m "Přidán gitignore"
```


## Důležitá poznámka

Soubor `.gitignore` **nepůsobí zpětně**. To znamená, že pokud už je nějaký soubor v repozitáři verzovaný (byl commitnut), jeho pozdější přidání do `.gitignore` nezpůsobí jeho automatické odstranění z verzování. Git jej bude nadále sledovat a verzovat. 

**Jak přestat verzovat již sledovaný soubor:**

Jako příklad mějme soubor `poznamky.txt`, který autor projektu používá pro interní poznámky, ale omylem jej commitnul do repozitáře. Je nutné jej nejprve odebrat z indexu, ale zároveň jej ponechat v adresáři s projektem:

1. Odebereme soubor z verzování (bez smazání z disku):

```bash
$ git rm --cached poznamky.txt
```

2. Provedeme commit změn:

```bash
$ git commit -m "Odebrání poznamky.txt z verzování a přidání do .gitignore"
```

Od této chvíle Git soubor `poznamky.txt` nebude sledovat a jeho další úpravy se již neobjeví ve výpisu `git status`.



---

## Soubor `.gitignore_global`

V souboru `.gitignore_global` je seznam souborů nebo jejich masek, **které se verzovat nikdy nebudou**. Další jdou pro konkrétní repozitář přidat do `.gitignore`. 

Příklad mého `~/.gitignore_global`:

```
.DS_Store
._*
desktop.ini
```
