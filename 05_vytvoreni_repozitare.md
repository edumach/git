
# Založení repozitáře

⚠️ "repozitář" = "projekt" = "adresář" (složka)

Nový projekt:

```bash
mkdir nazev
cd nazev
git init
```

V adresáři `nazev` vznikne skrytá složka `.git`. Ta obsahuje **celou historii** repozitáře.

Přidání prvního souboru:

```bash
echo "# Můj projekt" > README.md
git add README.md
git commit -m "První commit"
```

## Odstranění repozitáře

Git si všechny změny ukládá do adresáře `.git` v adresáři s projektem. Stačí jej smazat. 

⚠️ Pozor! Operace je nevratná.

```bash
cd projekt
rm -rf .git
```
