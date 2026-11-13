
# Spolupráce na sdíleném projektu


## Pozvat spolupracovníka

Na GitLabu přizvat spolupracovníky vždy u konkrétního projektu. Nejčastější postup je tento:

1. Otevřete projekt.
2. V levém menu otevřete na **Manage** $\to$ **Members**.
3. Klikněte na **Invite members** (pozvat členy). V okně zadejte:

    - Uživatelské jméno nebo e-mail (spolupracovníků jde zvolit více najednou). Všichni musí mít účet na tomto GitLabu.
    - roli (viz níže).
    - Nastavte datum expirace přístupu.
    - Potvrďte tlačítkem **Invite**.


Role (od nejnižších oprávnění):


- **Guest** - číst issues a wiki, přidávat komentáře.
- **Reporter** - číst repozitář, exportovat data, sledovat issues
- **Developer** (nejčastější) - commitovat do větví, vytvářet větve, push, posílat Merge Requesty, komentovat.
- **Maintainer** - vše, co Developer, navíc správa projektu, členů a nastavení.
- **Owner** (jen u skupin) - plná kontrola nad skupinou a všemi jejími projekty

**Tip:** Nejčastěji se u projektů používá **Developer**, protože umožňuje pracovat s kódem a posílat "Merge Requesty", aniž by bylo možné měnit nastavení projektu nebo přidávat nové členy.


## Merge Request

Termín merge request pochází z prostředí GitLab a označuje situaci, kdy autor změn požádá správce originálního repozitáře, aby vzal jeho změny a začlenil je do hlavní větve projektu. Na platformě GitHub se pro totéž používá výraz pull request.

Git jako takový žádný příkaz "merge request" nebo "pull request" nezná - jde o funkce, které poskytuje webová nadstavba repozitářů (GitLab a GitHub).

Zjednodušeně:
- Merge request je v prostředí GitLabu varianta pull requestu.
- Slouží k tomu, aby autor změn mohl navrhnout jejich začlenění do hlavní větve projektu.
- Není to přímý Git příkaz, ale workflow (pracovní postup), který probíhá přes webové rozhraní repozitáře.

**Proč se používá:** V týmech, kde pracuje více vývojářů, je důležité mít kontrolu nad tím, co a kdy se dostane do hlavní větve projektu. Merge/pull requesty poskytují:

- možnost kontroly a revize kódu před jeho začleněním,
- prostor pro diskusi o změnách mezi autory a recenzenty,
- možnost řešit konflikty nebo drobné úpravy ještě před spojením do hlavní větve,
- dokumentaci a historii toho, co bylo navrženo a jak bylo schváleno.

## Typický workflow (GitLab / GitHub)

Představte si následující postup:

1. Vytvoříte **branch** (větev) z hlavní větve `main` (nebo `master`) a pojmenujete ji podle toho, co řešíte (např. `feature-login`).
2. Pracujete v této větvi - upravujete kód, testujete, commitujete změny.
3. Pushujete tuto větev do vašeho vzdáleného repozitáře (forku nebo projektu).
4. Přes web rozhraní GitLabu nebo GitHubu vytvoříte merge/pull request. Zvolíte, ze které větve se má změna začlenit do které (např. z `feature-login` do `main`).
5. Ostatní (např. správci projektu) si prohlédnou změny, mohou diskutovat nebo požádat o úpravy.
6. Po schválení správce mergene (sloučí) změny do hlavní větve.

Tento proces tak slouží jako žádost o začlenění změn a jako forma spolupráce mezi autory.

## Rozdíly od `git pull` nebo `git push`


1. `git pull` je Git příkaz, kterým si do lokálního repozitáře stáhnete aktuální změny z určité větve vzdáleného repozitáře. Tento příkaz nijak nevytváří žádost o začlenění změn, jen synchronizuje vaše lokální soubory s tím, co je na serveru.
2. Merge/pull request je naopak webové workflow, které upozorňuje správce repozitáře, že máte hotový funkční kus kódu, který chcete začlenit.
3. Merge/pull request tedy neslouží k synchronizaci repozitářů, ale k koordinaci a kontrole změn mezi vývojáři.


## Shrnutí

- Pull/merge requesty se nepoužívají přímo z příkazové řádky Git, ale přes webové rozhraní GitLabu nebo GitHubu.
- Umožňují recenzi kódu a diskusi před tím, než se změny dostanou do hlavní větve projektu.
- Jsou klíčové pro bezpečnou spolupráci většího týmu, protože zachovávají historii a umožňují zpětné sledování rozhodnutí.

## Stručný příklad pracovního toku

```bash
# přepnutí do nové větve
git checkout -b feature/nova-funkce

# úprava souborů a commit změn
git add -A
git commit -m "Přidána nová funkce"

# push změn na vzdálený server
git push origin feature/nova-funkce

# následně na webu GitLabu vytvoříte Merge Request
```

Po vytvoření merge requestu ostatní vidí rozdíly mezi tím, co máte vy a co je v cílové větvi. Pokud je vše v pořádku, projektový tým nebo vy sám (jste-li vlastníkem) může změny sloučit (`merge`) do hlavní větve.

