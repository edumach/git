
# Návrat k předchozí verzi projektu

```
git checkout
git reset
git reflog
```

Git nám umožňuje "cestovat časem" v našem kódu, což je jedna z jeho největších výhod. Díky tomu se můžeme kdykoliv vrátit k předchozím verzím projektu, ať už chceme opravit chybu, dokonce obnovit i smazaný soubor nebo jednoduše prozkoumat, jak se projekt vyvíjel. Je to jako mít archiv všech verzí našeho kódu, kdykoliv po ruce. 

Git vytváří **zálohy všech verzí**, takže se nemusíme bát o ztrátu dat.

## Dočasný návrat

```bash
$ git checkout <hash>
```

například

```bash
git checkout 4d13f71
```

Přepnete se do vybraného commitu, změny se neuloží trvale.

Návrat zpět na nejnovější verzi (commit):

```bash
$ git checkout main
```

nebo `master`, podle toho jak se vaše větev jmenuje. Pokud si název nepamatujete, vypište si jej příkazem `git branch`.


## Trvalý návrat

```bash
$ git reset --hard <hash>
```

například 

```bash
$ git reset --hard a68fb03
```

Vrátí se do zadaného commitu a "odstraní" všechny následné změny. Tímto krokem se **zruší všechny změny po zadaném commitu!**


## Zrušení návratu

I po trvalé změně verze je možné se vrátit na nejnovější verzi. Git si všechny změny stále pamatuje. Příkazem

```bash
$ git reflog
```

zjistěte hash posledního (nejnovějšího) commitu a vraťte se:

```bash
$ git reset --hard f0d19fb
```
