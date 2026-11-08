
#  Nastavení identity

Tyto informace využívá každý Git commit. Bez jména a e-mailu nebude Git fungovat.

Nutno provést **na každém počítači**, kde chcete Git používat.

```bash
$ git config --global user.name "Jan Novák"
$ git config --global user.email "10XPrijmeniJj@student.panska.cz"
```

Kontrola:

```bash
$ git config --list
```

Pokud uděláte překlep nebo chybu, jednoduše spusťte příkaz znovu se správným údajem. Nové nastavení přepíše to staré.

Kam se konfigurace ukládá:

- Linux/macOS: `~/.gitconfig`
- Windows: `%USERPROFILE%\.gitconfig`

