

# Soubor `.gitconfig`

> Windows nemají `~`, ale `%USERPROFILE%`.  Příklad:
> Linux/macOS: `~/.gitconfig`
> Windows: `%USERPROFILE%\.gitconfig`

Všechna nastavení vytvořená příkazem `git config` se ukládají do souboru `~/.gitconfig`. 

Příklad mého `.gitconfig`:

```bash
[user]
    name = Jiří Machač
    email = machac@panska.cz
[alias]
    lo = log --oneline
    st = status
    ll = log --oneline --all --graph
[core]
    excludesfile = ~/.gitignore_global
    editor = nano      # Linux/macOS
    #editor = notepad  # Windows
    fileMode = false
[safe]
    directory = ’*’
```
- `fileMode = false` .. způsobí, že Git ignoruje změny oprávnění souborů a sleduje pouze změny jejich obsahu. Hodí se při střídání systémů Windows a Linux/macOS.
-  `directory = ’*’` .. říká Gitu, aby považoval všechny repozitáře za důvěryhodné a neprováděl kontrolu jejich vlastníka. Používá se hlavně tam, kde tato kontrola zbytečně překáží.
