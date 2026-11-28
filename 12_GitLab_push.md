

# Odeslání projektu na GitLab

Vše se provádí uvnitř repozitáře:

```bash
cd nazev
```

Než lokální repozitář propojíte s GitLabem, je dobré si ověřit, zda už k nějakému vzdálenému repozitáři připojený není.

```bash
$ git remote -v
```

Pokud příkaz nic nevypíše, lokální repozitář zatím není připojen k žádnému vzdálenému úložišti.

---

Další kroky se odvíjí podle toho, zda odesíláte váš vlastní Git repozitář nebo jiný naklonovaný z jiného vzdáleného repozitáře (GitHub, GitLab).

---


## Varianta A: Vlastní lokální repozitář


**(1)** Přidání vzdáleného repozitáře:

```bash
$ git remote add origin git@gitlab.panska.cz:10XPrijmeniJ/test.git
```

GitLab na rozdíl od GitHubu podporuje odeslání změn i protokolem HTTPS. GitHub pouze pomocí SSH. V GitLabu bude tedy fungovat i

```bash
$ git remote add origin https://gitlab.panska.cz/10XPrijmeniJ/test.git
```

Je však lepší si zvyknout a používat SSH.


1. Pamatujte, že `origin` není název větve, ale název vzdáleného repozitáře. Tento název je pouze konvence, ale používá se velmi často.

2. Všimněte si, že na konci adresy je kromě vašeho `Username` také název vzdáleného repozitáře s příponou `.git`. Je vhodné, aby se název lokálního a vzdáleného repozitáře shodoval.

3. Do vzdáleného úložiště se odesílá vždy jen jedna větev, nejčastěji `main`. Kontrola:

```bash
$ git remote -v
```

**(2)** Kontrola stavu lokálního repozitáře před odesláním. **Musí vypsat `working tree clean`**. JInak nepůjde repozitář odeslat.

```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

**(3)** První odeslání. Parametr `-u` nastaví výchozí vzdálenou větev:

```bash
git push -u origin main
```


**(4)** Další odeslání. Větev musí být vždy "čistá" (viz bod **2**):

```bash
git push
```

## Varianta B: Repozitář klonovaný odjinud

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

## Názvy větví

⚠️ Toto se často plete!

**main**, **master**

Jsou to názvy větví. Nic víc.
- `master` - původní historický "Linusův" název hlavní větve v Gitu.
- `main` - novější, dnes doporučovaný název hlavní větve. Změna se týká jen defaultního názvu, Git jako takový se nijak nezměnil. tento název používá defaultně GitHub (od 2020) i GitLab (od 2021). Staré repozitáře zůstávají na `master`, dokud si je autor sám nepřejmenuje. Není to v žádném případě povinné!


**origin**

- `origin` není větev, ale **název vzdáleného repozitáře**. Je to alias (přezdívka) pro URL serveru.
- I tento název vymyslel Linus Torvalds a naštěstí nikmu nevadí, takže se nezměnil.
- `origin` je `https://gitlab.panska.cz/jmeno/projekt.git`

Když napíšete `git push origin main` znamená to: "Pošli větev `main` na vzdálený repozitář jménem `origin`.

**origin/main**


-  `main` je moje lokální větev.
-  `origin/main` je kopie hlavní větve na serveru.

Vysvětlení: `origin/main` je informace, jak vypadá `main` na serveru. Nelze do ní přímo commitovat, je to jen "zrcadlo".

**Shrnutí:**

- `main` je moje větev, 
- `origin` je server,
- `origin/main` je to, co na něm vidím já (nebo i ostatní).


---

# ⚠️ Rozdíl při prvním odeslání repozitáře na GitHub

Při odesílání lokálního repozitáře na GitHub je postup téměř stejný jako u školního GitLabu. Hlavní rozdíl je v tom, že na GitHubu musíte vzdálený repozitář nejprve vytvořit prostřednictvím webového rozhraní Samotný příkaz `git push` nový repozitář na GitHubu nevytvoří.

## Postup

**(1) Vytvoření vzdáleného repozitáře**

1. Přihlaste se na [GitHub](https://github.com/).
2. Klikněte na tlačítko **New repository**.
3. Zadejte název repozitáře (např. `test`).
4. Zvolte viditelnost repozitáře (Public nebo Private).
5. Klikněte na **Create repository**.

**Důležité:** Pokud již máte vlastní lokální repozitář, při vytváření nového vzdáleného repozitáře nezaškrtávejte vytvoření README, `.gitignore` ani licence. Obsah repozitáře odešlete ze svého počítače.

**(2) Připojení lokálního repozitáře ke GitHubu**

Adresa vzdáleného repozitáře má následující podobu:

```bash
$ git remote add origin git@github.com:Username/test.git
```

Místo `Username` použijte své uživatelské jméno na GitHubu.

**(3) Kontrola propojení**

```bash
$ git remote -v
```

**(4) První odeslání**

```bash
$ git push -u origin main
```

Parametr `-u` nastaví výchozí vzdálenou větev. Při dalších odesíláních již stačí použít:

```bash
$ git push
```
---

## Shrnutí

U našeho školního GitLabu lze vytvořit vzdálený repozitář prvním odesláním. GitHub vyžaduje, abyste vzdálený repozitář nejprve založili.


