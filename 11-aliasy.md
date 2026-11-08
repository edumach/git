
# Aliasy

Opakované psaní delších (složitějších) příkazů si můžete **zjednodušit vytvořením aliasů** - zástupných příkazů. Jejich vytvoření je snadné:


```bash
git config --global alias.st "status"
git config --global alias.lo "log --oneline"
git config --global alias.ll "log --oneline --all --graph"
```

Použití:

```bash
git st
git lo
git ll
```

Zkratky `st`, `lo` a `ll` nejsou zvolené náhodou. Platí zavedené konvence (nepsaná pravidla), že se tyto aliasy jmenují právě tak.

⚠️ **POZOR!** Stejně jako jméno a e-mail se i tato nastavení nepřenáší. Na každém počítači si musíte aliasy nejprve vytvořit.