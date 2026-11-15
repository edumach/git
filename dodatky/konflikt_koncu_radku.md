
# Konce řádků v různých operačních systémech

Operační systémy používají různé znaky pro ukončení řádku:

| Systém | Označení | Znak |
|---------|---------|---------|
| Windows | CRLF | `\r\n` |
| Linux | LF | `\n` |
| macOS | LF | `\n` |

Pokud na jednom repozitáři pracují uživatelé různých operačních systémů, může Git hlásit změny i v případě, že se skutečný obsah souboru nezměnil. Změnily se pouze konce řádků.

---

## Doporučené řešení

V kořenovém adresáři projektu vytvořte soubor `.gitattributes`:

```text
* text=auto
```

Git pak při ukládání a načítání souborů automaticky převádí konce řádků podle použitého operačního systému.

Toto nastavení je vhodné pro většinu projektů a eliminuje problémy při spolupráci mezi uživateli Windows, Linuxu a macOS.

## Nastavení Gitu ve Windows

Ve Windows se doporučuje:

```bash
$ git config --global core.autocrlf true
```

Git při checkoutu převede soubory do formátu CRLF a při commitu je uloží jako LF.


## Nastavení Gitu v Linuxu a macOS

V Linuxu a macOS se doporučuje:

```bash
$ git config --global core.autocrlf input
```

Git ponechá lokální soubory ve formátu LF a při commitu zajistí správné uložení do repozitáře.


## Kontrola nastavení

Aktuální konfiguraci zobrazíte příkazem:

```bash
$ git config --global core.autocrlf
```

---

## Doporučení

Pokud na projektu spolupracují uživatelé různých operačních systémů:

1. vytvořte soubor `.gitattributes`,
2. použijte:

    ```text
    * text=auto
    ```

3. ve Windows nastavte:

    ```bash
    $ git config --global core.autocrlf true
    ```

4. v Linuxu a macOS nastavte:

    ```bash
    $ git config --global core.autocrlf input
    ```

Tím se vyhnete zbytečným změnám souborů způsobeným pouze rozdílným formátem konců řádků.

## Shrnutí

Přidejte do projektu soubor `.gitattributes` s obsahem `* text=auto` a dál problém neřešte.