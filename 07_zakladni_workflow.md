
# Základní workflow

Všchny činnosti se provádějí **vždy v adresáři s repozitářem**!!!

```bash
cd nazev_repozitae
```

Kontrola stavu:

```bash
git status
```

Krátká verze:

```bash
git status -s
```

Nejčastější stavy:

- `??` .. nový nesledovaný soubor
- `A` .. přidaný soubor
- `M`	.. upravený soubor
- `D` .. smazaný soubor
- `R` .. přejmenovaný soubor

Přidání změn do **Stage**:

Jeden soubor:

```bash
git add index.html
```

Všechny soubory:

```bash
git add -A
```

Vytvoření **commitu** (verze, revize):

```bash
git commit -m "Přidána úvodní stránka"
```

Základní workflow:

```bash
git status
git add -A
git commit -m "Popis změn"
```

Zapamatovat si: upravím → add → commit
