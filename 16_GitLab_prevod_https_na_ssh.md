
# Převod repozitáře z HTTPS na SSH

Pokud byl repozitář naklonován přes HTTPS, ale chceme používat SSH autentizaci, změníme adresu vzdáleného repozitáře:

1. Zjistíme aktuální nastavení:
   ```bash
   git remote -v
   ```

2. Změníme adresu `origin` na SSH:
   ```bash
   git remote set-url origin git@gitlab.panska.cz:10XPrijmeniJ/repozitar.git
   ```
   Místo `repozitar` zapíšeme skutečný název.

3. Ověříme změnu:
   ```bash
   git remote -v
   ```

   Výsledek bude například:
   ```text
   origin  git@gitlab.panska.cz:10XPrijmeniJ/repozitar.git (fetch)
   origin  git@gitlab.panska.cz:10XPrijmeniJ/repozitar.git (push)
   ```

Od této chvíle bude Git používat SSH klíč pro komunikaci s GitLabem.


### Doporučený postup:

Před každým odesláním:

```bash
git fetch
git pull
git add -A
git commit -m "Popis změny"
git push
```

Zapamatovat si: fetch → pull → commit → push
