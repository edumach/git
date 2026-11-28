
# Odeslání/stažení všech větví na/z GitLab

⚠️ Základní pravidlo: před `push` nebo `pull` musí `status` vypsat "Working tree clean"!

## Push

Příkaz

```bash
$ git push -u origin main
```
odešle na GitLab pouze větev `main` (`-u` zapamatuje si "do `origin` odešli `main`"). Poté už stačí:

```bash
$ git push
```

Toto už známe. Jsou situace, kdy je potřeba odeslat všechny větve, například pro možnost pokračovat v projektu na jiném počítači. K tomu stačí přidat přepínač `--all`:

```bash
$ git push --all origin
```

Do `origin` odešle všechny lokální větve. Připomínám, že `origin` je jen "alias" cesty repozitáře na GitLabu/GitHubu.

## Pull

Opačně to nefunguje. Nejde najednout stáhnou všechny větve. Pokud chcete aktualizovat všechny větve do lokálního repozitáře, musíte to provést postupně:

```bash
$ git fetch

$ git switch main
$ git pull

$ git switch vetev-2
$ git pull

$ git switch vetev-3
$ git pull

...
```


## Shrnutí

| Příkaz | Co dělá |
| --- | --- |
| `git push` | odešle aktuální větev |
| `git push --all` | odešle všechny lokální větve |
| `git fetch` | stáhne informace o všech vzdálených větvích |
| `git pull` | aktualizuje pouze aktuální větev |
