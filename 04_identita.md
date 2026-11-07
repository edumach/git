
# Nastavení identity

Nutno provést **na každém počítači**. Bez toho nebude Git fungovat.

```bash
git config --global user.name "Jan Novák"
git config --global user.email "10XNovakJj@student.panska.cz"
```

Kontrola:

```bash
git config --list
```

Kam se konfigurace ukládá:

- Linux/macOS: `~/.gitconfig`
- Windows: `%USERPROFILE%\.gitconfig`

