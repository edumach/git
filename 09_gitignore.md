
# Soubor `.gitignore`

Soubor `.gitignore` určuje, které soubory Git **nebude sledovat**. Typické použití je pro:

- dočasné soubory,
- logy,
- výsledky kompilace,
- nastavení editorů,
- velké automaticky generované adresáře.

Příklad souboru:

```
# komemtář
*.log
*.tmp
poznamky.tex
zalohy/
```

Po vytvoření souboru:

```bash
touch .gitignore
```

uložíme:

```bash
git add .gitignore
git commit -m "Přidán gitignore"
```

---

V souboru `.gitignore_global` je seznam souborů a jejich masek, které se verzovat nikdy nebudou. Další jdou pro konkrétní repozitář přidat do `.gitignore`. 

Příklad mého `~/.gitignore_global`:

```
.DS_Store
._*
desktop.ini
```

