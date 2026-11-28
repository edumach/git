
# Založení repozitáře


---

⚠️ Pamatujte: "repozitář" = "projekt" = "adresář" (složka)

- **projekt** (*project*) je obecné označení "složky" se souvisejícím obsahem,
- **adresář** (*directory*) je unixových systémech tradiční název pro složku,
- Název **složka** (*folder*) zavedl Microsoft kvůli snadnějšímu zapamatování jejího významu běžnými uživateli,
- **repozitář** (*repository*) je v Gitu zavedený název pro "složku" s Git projektem.

---

**(1)** Založení nového projektu:

```bash
mkdir nazev
cd nazev
git init
```

V adresáři `nazev` si Git vytvoří skrytý adresář `.git`. Ten obsahuje **celou historii** repozitáře a vše co si Git potřebuje ukládat. Její obsah si Git řídí sám. Vůbec si jí nemusíte všímat.

Díky tomu je celý projekt přenositelný na libovolný jiný počítač. Stačí na něm mít naistalovaný Git a v konfiguraci zapsané jméno a e-mail (viz kapitola *identita*).

⚠️ Poznámka: Nedoporučuji Git projekt (složku) ukládat na OneDrive nebo jiné cloudové úložiště. K tomu slouží GitLab nebo GitHub.

---

**(2)** Přidání prvního souboru:

```bash
echo "# Můj projekt" > README.md
```

---

**(3)** Přidání souboru ke sledování (`add`) a uložení stavu projektu (`commit`): 

```bash
git add README.md
git commit -m "První commit"
```


---

## Odstranění repozitáře

Git si všechny změny ukládá do adresáře `.git` v adresáři s projektem. Stačí jej smazat. 

⚠️ Pozor! Operace je nevratná.

```bash
cd projekt
rm -rf .git
```
