
# Propojení s počítačem (SSH klíče)

Pro plnohodnotnou spolupráci mezi lokálním Git repozitářem a GitLab serverem je potřeba si nejprve vygenerovat šifrovací klíče.

⚠️ Pro správnou funkčnost **musí být e-mail lokálního Git repozitáře stejný s GitLabem** - tedy váš školní. Před pokračováním zkontrolujte, popř. nastavte školní. Jinak nebude propojení na GitLab fungovat! Tento požadavek platí i pro GitHub.

Na počítači si vygenerujte **pár šifrovacích klíčů** (dva textové soubory). Jeden je **privátní** - zůstává uložený v počítači, druhý je **veřejný**. Ten se nakopíruje na server. GitLab podporuje [několik typů klíčů](https://docs.gitlab.com/18.6/user/ssh/). My použijeme preferovaný typ **ED25519**. Používá jej i GitHub.

Vygenerování klíče:

```bash
$ ssh-keygen -t ed25519 -C "10XPrijmeniJ@student.panska.cz"
```
Všechny otázky potvrďte klávesou **Enter**, heslo ke klíči nevytvářejte.

Výchozí umístění:

```
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

Zobrazení veřejného klíče:

Linux/macOS (v terminálu):
```
cat ~/.ssh/id_ed25519.pub
```
Windows (v PowerShellu):
```
type ~/.ssh/id_ed25519.pub
```

Přidání klíče do GitLabu:

1. GitLab: **Profile** → **Preferences** → **SSH Keys**
2. Vložit obsah souboru `id_ed25519.pub`
3. Do pole **Title** je dobrí zapsat název počítače/učebny
4. Kliknout na **Add Key**

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

🔐 ssh klíč typu `ed25519` používá i GitHub. Stejný veřejný klíč (`id_ed25519.pub`) můžete použít i tam.

---

