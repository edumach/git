
# Odesílání jednoho repozitáře na GitLab i GitHub

Git umožňuje propojit jeden lokální repozitář s více vzdálenými úložišti. Můžeme tak stejný projekt udržovat současně na školním GitLabu i na GitHubu.

V tomto příkladu budeme používat:
- `origin` – školní GitLab
- `github` – osobní GitHub

## Postup

**(1) Kontrola současného propojení**

Uvnitř lokálního repozitáře vypíšeme nastavená vzdálená úložiště:

```bash
$ git remote -v
```

Předpokládáme, že již máme nastavený školní GitLab:

```bash
origin  git@gitlab.panska.cz:10XPrijmeniJ/test.git (fetch)
origin  git@gitlab.panska.cz:10XPrijmeniJ/test.git (push)
```

**(2) Vytvoření repozitáře na GitHubu**

Na GitHubu nejprve vytvoříme nový vzdálený repozitář (např. `test`).

Při jeho vytváření nezaškrtáváme README, `.gitignore` ani licenci.

**(3) Přidání druhého vzdáleného úložiště**

Přidáme nové propojení s GitHubem. Na rozdíl od původního `origin` jej pojmenujeme `github`:

```bash
$ git remote add github git@github.com:Username/test.git
```

**(4) Kontrola obou propojení**

```bash
git remote -v
```

Nyní by měl výpis obsahovat obě úložiště:

```bash
origin  git@gitlab.panska.cz:10XPrijmeniJ/test.git (fetch)
origin  git@gitlab.panska.cz:10XPrijmeniJ/test.git (push)
github  git@github.com:Username/test.git (fetch)
github  git@github.com:Username/test.git (push)
```

**(5) První odeslání na GitHub**

```bash
git push -u github main
```

**(6) Další odesílání na obě úložiště**

Při každém odesílání změn je nutné provést dva příkazy:

```bash
$ git push origin main
$ git push github main
```

## Důležité

- Obě úložiště obsahují samostatnou kopii projektu.
- Commity se vytvářejí pouze lokálně a následně se odesílají na obě úložiště.
- Git automaticky neodesílá změny na obě místa současně.
- Je vhodné odesílat změny na obě úložiště pravidelně, aby jejich obsah zůstal shodný.

**Zapamatujte si:** Jeden lokální Git repozitář může mít více vzdálených úložišť. Jejich názvy (`origin`, `github` apod.) jsou pouze označení, která si můžeme zvolit podle potřeby.