# Git

<img src="img/git-logo.png" width="100">

## Co je Git?

Git je **distribuovaný** verzovací systém.

Umožňuje ukládat historii změn v projektu a kdykoliv se vrátit k dřívější verzi souborů.

Nejčastěji se používá při vývoji softwaru, ale lze jej využít téměř pro jakýkoliv projekt obsahující soubory:

- webové stránky,
- dokumentaci,
- školní práce,
- prezentace,
- technické projekty,
- skripty,
- konfigurační soubory.

Díky Gitu už není potřeba vytvářet složky nebo soubory typu:

```
projekt
projekt-final
projekt-final-oprava
projekt-final-oprava-opravdu-final
```

Veškerou historii uchovává Git.

## Proč Git používat?

Git umožňuje:

- ukládat jednotlivé verze projektu,
- vracet se ke starším verzím,
- porovnávat provedené změny,
- experimentovat bez rizika ztráty práce,
- spolupracovat s dalšími lidmi.

Při větších projektech se Git velmi rychle stane nepostradatelným nástrojem. Mnoho vývojářů po několika týdnech práce s Gitem říká:

> „Jak jsem bez Gitu mohl vůbec fungovat?“

## Jak Git funguje?

Git si lze představit jako časovou osu projektu. Každé významnější změně vytvoříte tzv. "commit" (snímek projektu).

```
A ──> B ──> C ──> D ──> E ...
```

Pokud zjistíte, že jste něco pokazili, můžete se vrátit například ke stavu `B` nebo `C`.

Na rozdíl od běžného kopírování složek:

```
projekt-v.1
projekt-v.2
projekt-v.3
projekt-v.4
```

má Git historii přehledně na jednom místě.

## Lokální práce

Jednou z největších výhod Gitu je, že většinu operací provádí přímo na vašem počítači. Můžete:

- vytvářet commity,
- prohlížet historii,
- přepínat mezi verzemi,

i bez připojení k internetu.

Server je potřeba až ve chvíli, kdy chcete projekt sdílet nebo zálohovat online.

## Git není GitLab

<img src="img/git-gitlab.png" width="500">

Je důležité rozlišovat:

| Nástroj | Účel |
| --- | --- |
| Git | verzování souborů |
| GitLab / GitHub | ukládání a sdílení Git projektů |


Git umí fungovat úplně bez GitLabu a GitHubu. GitLab a GitHub pouze umožňují projekty sdílet, zálohovat a spravovat online.

---


## Shrnutí

Git:

- ukládá historii projektu,
- umožňuje bezpečný návrat ke starším verzím,
- pomáhá při spolupráci (GitLab / GitHub),
- funguje i bez internetu,
- není určen pouze pro programátory.

Git je univerzální nástroj pro správu rozsáhlejších projektů a jejich historie.

## Zajímavosti

### Jak vznikl Git

Od roku 1992 vyvíjeli programátoři operační systém Linux. Pro správu zdrojových kódů používali jiný verzovací systém, ale ten přestal být pro jejich potřeby dostupný. Tvůrce Linuxu, *Linus Torvalds*, se proto v roce 2005 rozhodl vytvořit **[vlastní nástroj](https://git.kernel.org/pub/scm/git/git.git/)**. Jeho cílem bylo navrhnout systém, který bude:

- rychlý,
- spolehlivý,
- schopný pracovat s velmi rozsáhlými projekty,
- vhodný pro spolupráci velkého množství vývojářů.

Během několika týdnů tak vznikl Git, který se postupně stal **nejpoužívanějším verzovacím systémem na světě**. Dnes jej používají jednotlivci, školy i firmy všech velikostí.

Git vznikl původně pro **[vývoj Linuxu](https://github.com/torvalds/linux)**, ale dnes se používá při správě téměř jakéhokoliv projektu obsahujícího soubory. Může pomoci při tvorbě webových stránek, maturitních prací, technické dokumentace, školních projektů, poznámek v Markdownu, prezentací nebo například při vývoji her a jejich modifikací.


### Proč se jmenuje Git?

Když *Linus Torvalds* vytvářel Git, nebyl název myšlen úplně vážně. Slovo "git" je v britské angličtině mírně hanlivý výraz pro nepříjemného, hloupého nebo otravného člověka. Něco jako "trouba", "blbec" nebo "idiot". Sám Linus k tomu s typickým humorem uvedl něco ve smyslu:

*"Git znamená nepříjemný člověk. Jsem sobec a všechny své projekty pojmenovávám po sobě. Nejprve Linux, teď Git."*

Linus Torvalds zvolil název spíše jako recesi než jako odborný termín. Podobný technický humor je v unixovém světě běžný. Také názvy GNU, Bash, Apache, less, nano, pico, zombie, daemon, kill a řada dalších vznikly jako slovní hříčky.

To je mimochodem důvod, proč většina učebnic vznik názvu raději vůbec neřeší 😄.

