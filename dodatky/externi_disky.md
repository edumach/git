
# Upozornění detected dubious ownership

Při práci s Git repozitářem se může objevit chybová hláška:

```
fatal: detected dubious ownership in repository
```

Toto upozornění se objevuje od novějších verzí systému Git a nejde o chybu repozitáře ani o špatnou práci uživatele. Jedná se o bezpečnostní kontrolu, kterou Git provádí v případě, že nedokáže ověřit vlastníka souborů. Typickým případem je práce s repozitářem uloženým na:

- USB disku,
- externím disku nebo sdíleném úložišti,
- síťovém disku.

**Řešení:**

Pokud je repozitář uložen na důvěryhodném místě (např. vlastním USB disku), lze jej označit jako bezpečný příkazem:

```bash
$ git config --global --add safe.directory "*"
```

Tímto nastavením Git povolí práci se všemi repozitáři bez ohledu na disk a upozornění se již nebude zobrazovat.

Toto řešení je běžné a doporučené zejména v prostředí, kde se často pracuje s přenosnými médii.
