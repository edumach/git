
#  Nastavení identity

Tyto informace využívá každý Git commit. Bez jména a e-mailu nebude Git fungovat.

Nutno provést **na každém počítači**, kde chcete Git používat. **Nastavení se s projektem nepřenáší**.

```bash
$ git config --global user.name "Jan Novák"
$ git config --global user.email "10XPrijmeniJ@student.panska.cz"
```

Kontrola:

```bash
$ git config -l
```

Pokud uděláte překlep nebo chybu, jednoduše spusťte příkaz znovu se správným údajem. Nové nastavení přepíše to staré.

Nejen tato konfigurace se ukládá do **textového souboru** `.gitconfig` ve vašem domovském adresáři: 

- Linux:   `/home/<jmeno>/.gitconfig` 
- macOS:   `/home/Users/<jmeno>.gitconfig` 
- Windows: `C:\Users\<jmeno>\.gitconfig` 

 