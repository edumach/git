
# Propojení s počítačem (SSH klíče)

Vygenerování klíče:

```bash
ssh-keygen -t ed25519 -C "10XPrijmeniJ@student.panska.cz"
```

⚠️ Pro správnou funkčnost **musí být e-mail lokálního Git repozitáře stejný s GitLabem** - tedy váš školní. Před pokračováním zkontrolujte, popř. nastavte školní. Jinak nebude propojení na GitLab fungovat! Tento požadavek platí i pro GitHub.


Výchozí umístění:

```
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

Zobrazení veřejného klíče:

- Linux/macOS: `cat ~/.ssh/id_ed25519.pub`
- Windows: `type %USERPROFILE%\.ssh\id_ed25519.pub`

Přidání klíče do GitLabu:

1. GitLab: **Profile** → **Preferences** → **SSH Keys**
2. Vložit obsah souboru `id_ed25519.pub`
3. Kliknout na **Add Key**

Test spojení:

```bash
ssh -T git@gitlab.panska.cz
```

První spuštění na daném počítači může vyvolat potřebu klíč verifikovat:

```
$ ssh -T git@gitlab.panska.cz
The authenticity of host 'gitlab.panska.cz (2a02:b20:100:217::11)' can't
be established.
ED25519 key fingerprint is SHA256:YFpk0s/GcyP9gDFxgicZ534O9Ehy0T37pWMi8.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Zapište **yes** a potvrďte.

Druhé (a další) musí vypsat toto:

```
$ ssh -T git@gitlab.panska.cz
Welcome to GitLab, @10XPrijmeniJ!
```

---

🔐 ssh klíč typu `ed25519` používá i GitHub. Stejný veřejný klíč (`id_ed25519.pub`) můžete použít i tam. Nemusíte generovat nový.

---

## ⚙️ Možný problém: SSH se ptá na heslo

Při příkazu `ssh -T git@gitlab.panska.cz` je uživatel vyzván k zadání hesla, přestože má na GitLabu uložený SSH klíč a při jeho generování heslo nezadával.

Proč k tomu dochází: Počítač se při připojování snaží použít všechny dostupné klíče uložené v `~/.ssh`. Pokud jich je víc nebo **proběhlo více neúspěšných pokusů**, GitLab další klíče odmítne a požádá o heslo.

Jednorázový test: Tímto příkazem řekneme počítači, aby použil pouze správný klíč:

```bash
$ ssh -o IdentitiesOnly=yes -i ~/.ssh/id_ed25519 -T git@gitlab.panska.cz
```

Pokud se zobrazí hláška `Welcome to GitLab @10XPrijmeniJ!`, je vše v pořádku a klíč funguje správně.

Doporučené trvalé řešení: Aby se problém neopakoval, je potřeba nastavit, jaký klíč se má pro GitLab používat vždy. Vytvořte nebo upravte soubor `~/.ssh/config` a vložte do něj následující řádky:

```bash
Host gitlab.panska.cz
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes
```

Poté již stačí používat běžný příkaz:

```bash
$ ssh -T git@gitlab.panska.cz
```
a přihlášení proběhne bez dotazu na heslo.

