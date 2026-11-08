
# Fork cizího GitLab repozitáře

Při práci s cizími repozitáři se často setkáte se dvěma pojmy: **klon** a **fork**. Přestože spolu souvisejí, znamenají odlišné věci.

**Klon**

Klonování je proces, při kterém si příkazem `git clone` stáhnete cizí vzdálený repozitář do svého počítače. Vznikne tím **lokální repozitář**, se kterým můžete pracovat, ale **nemáte oprávnění odesílat změny zpět** do původního projektu.

U veřejných repozitářů navíc klonování nevyžaduje ani přihlášení uživatele.

**Fork** 
  
Fork je proces, při kterém si na svém účtu vytvoříte **vlastní vzdálenou kopii** cizího repozitáře. Tato kopie se nachází na stejném serveru jako původní projekt a je s ním logicky provázaná. Z tohoto důvodu lze fork provádět pouze v rámci jednoho serveru, například `gitlab.panska.cz`, `gitlab.com` nebo `github.com`.

Forkovaný repozitář je plnohodnotný projekt, do kterého můžete odesílat vlastní změny. Tyto změny lze později **nabídnout autorovi původního repozitáře**, typicky pomocí **merge requestu**.

Další podmínkou forku je **viditelnost projektu**. V našem školním prostředí jsou projekty označeny jako **Public** nebo **Internal**, což forkování umožňuje.

**Shrnutí:**

- klon = lokální kopie bez práv zápisu
- fork = vlastní vzdálená kopie po vaším účtem


## Fork projektu

V této části si fork vyzkoušíme v praxi na jednoduchém cvičném projektu.

Přihlaste se do školního GitLabu a otevřete adresu
[https://gitlab.panska.cz/machac/git-fork](https://gitlab.panska.cz/machac/git-fork).

V pravé části stránky klikněte na tlačítko **Fork**. GitLab se vás zeptá, kam má být projekt forkován – do pole **Select a namespace** zadejte svůj uživatelský účet.

Dále můžete zvolit, které větve se mají forkovat (tento projekt obsahuje pouze jednu větev `main`) a nastavit viditelnost projektu. Ponechte **Internal** a proces dokončete kliknutím na tlačítko **Fork project**.

Po dokončení se ve vašem účtu objeví **vlastní vzdálená kopie projektu**.

## Klonování vlastního forku

Abyste mohli s projektem pracovat, je potřeba si nyní **naklonovat svůj fork do počítače**.

Na stránce vašeho forkovaného projektu zkopírujte jeho **git adresu** a v terminálu spusťte:

```bash
$ git clone git@gitlab.panska.cz:10XPrijmeniJ/git-fork.git
```

Tímto příkazem vznikne lokální repozitář, který je propojen s vaším vzdáleným forkem.

Do tohoto repozitáře již můžete vytvářet commity a změny **odesílat** pomocí `git push`.


