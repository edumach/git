
# Průběžná synchronizace

Tato činnost vyžaduje jistou míru systemtičnosti. Před odesláním změn je **vždy doporučeno nejprve zjistit stav vzdáleného repozitáře**. Předcházíte tím pozdějším konfliktům.

Jako vždy se vše provádí uvnitř repozitáře:

```bash
cd nazev_repozitare
```

Nejprve si stáhněte informace o změnách ze serveru. Příkaz nic neslučuje ani nemění v pracovních souborech:

```bash
git fetch
```

Může nastat jeden ze dvou stavů:

**(1)** lokální i vzdálený repozitář je stejný,

**(2)** vzdálený se od lokálního liší (např. nějakou předchozí synchronizací z jiho počítače). V tomto případě nejprve synchronizujte vzdálený do lokálního. Příkaz `pull` stáhne a sloučí změny:

```bash
git pull
```
nebo

```bash
git pull origin main
```

Teprve pak odešlete vaše lokální commity na server:


```bash
git push
```

nebo

```bash
git push origin main
```

---

## Řešení chyby `non-fast-forward` při `git push`

Při pokusu o odeslání změn pomocí `git push` se může objevit chyba:

```
! [rejected] main -> main (non-fast-forward)
error: failed to push some refs
```

Tato chyba znamená, že vzdálená větev obsahuje novější změny, které nejsou ve vaší lokální kopii. Git proto odmítne změny odeslat, aby nedošlo k přepsání historie.

**Řešení:**

1. Nejprve je potřeba stáhnout a začlenit vzdálené změny:

    ```bash
    $ git pull origin main --rebase
    ```

2. Poté lze změny znovu odeslat:

    ```bash
    $ git push origin main
    ```


### Nastavení chování příkazu `git pull`

Příkaz

```bash
$ git config --global pull.rebase false
```

nastaví, že při použití `git pull` bude Git změny ze serveru začleňovat pomocí sloučení (`merge`), nikoli přepisováním historie
(`rebase`).

Toto nastavení je vhodné zejména pro začátečníky, protože je bezpečnější a předvídatelnější a nevyžaduje řešit složitější situace vznikající při použití `rebase`.



