

# Odeslání projektu na GitLab

Vše se provádí uvnitř repozitáře:

```bash
cd test
```

Než lokální repozitář propojíte s GitLabem, je dobré si ověřit, zda už k nějakému vzdálenému repozitáři připojený není.

```bash
$ git remote -v
```

Pokud příkaz nic nevypíše, lokální repozitář zatím není připojen k žádnému vzdálenému úložišti.

---

Další kroky se odvíjí podle toho, zda odesíláte váš vlastní Git repozitář nebo jiný naklonovaný z jiného vzdáleného repozitáře (GitHub, GitLab).

---


## Varianta 1: Vlastní lokální repozitář


(1) Přidání vzdáleného repozitáře:

```bash
$ git remote add origin git@gitlab.panska.cz:10XPrijmeniJ/test.git
```

1. Pamatujte, že `origin` není název větve, ale název vzdáleného repozitáře. Tento název je pouze konvence, ale používá se velmi často.

2. Všimněte si, že na konci adresy je kromě vašeho `Username` také název vzdáleného repozitáře s příponou `.git`. Je vhodné, aby se název lokálního a vzdáleného repozitáře shodoval.

3. Do vzdáleného úložiště se odesílá vždy jen jedna větev, nejčastěji `main`. Kontrola:

```bash
$ git remote -v
```

(2) Kontrola stavu lokálního repozitáře před odesláním. **Musí vypsat `working tree clean`**. JInak nepůjde repozitář odeslat.

```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

(3) První odeslání. Parametr `-u` nastaví výchozí vzdálenou větev:

```bash
git push -u origin main
```


(4) Další odeslání. Větev musí být vždy "čistá" (viz bod 2):

```bash
git push
```

## Varianta 2: Repozitář klonovaný odjinud

Tato situace nastává tehdy, pokud jste repozitář nejprve stáhli pomocí `git clone` (např. z GitHubu nebo z cizího GitLabu) a chcete jej následně nahrát do vlastního repozitáře na GitLabu.

Takový repozitář už má vzdálený repozitář nastavený (obvykle pod názvem `origin`), proto jej nelze přidat znovu. 

Nejprve je nutné původní propojení odstranit:

```bash
$ git remote remove origin
```

Teprve poté připojte repozitář ke svému GitLabu:

```bash
$ git remote add origin git@gitlab.panska.cz:10XPrijmeniJ/nazev.git
```

Tím dojde pouze ke změně cílového vzdáleného repozitáře. Veškerá historie, commity i větve zůstávají beze změny.


> **Poznámka:** Git umožňuje pracovat i s více vzdálenými repozitáři současně (např. GitHub a GitLab paralelně). V běžné školní praxi však vystačíme s jedním vzdáleným repozitářem, který je obvykle pojmenován `origin`.

