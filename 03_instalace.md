
# Instalace Gitu

## Kontrola instalace

Pokud se zobrazí číslo verze, je Git nainstalovaný a připraven k použití.

```bash
git --version
```

Pokud ne, je potřeba jej nainstalovat:

## Windows

Git vznikl pro Linux a používá unixové příkazy. **Git Bash** je takový **malý Linux ve Windows** – poskytuje prostředí pro práci s běžnými terminálovými příkazy, včetně editoru nano. Díky němu můžeme ve Windows používat stejné příkazy jako v Linuxu.

<img src="img/git-bash-logo.png" width="100">

Stáhnout a nainstalovat [https://git-scm.com/download/win](https://git-scm.com/download/win). Během instalace lze ponechat výchozí nastavení. Po instalaci spustit aplikaci **Git Bash**.

**Git Bash je užitečný i mimo Git**

Git Bash není **jen nástroj pro práci s Gitem**. Poskytuje ve Windows prostředí unixového terminálu, ve kterém můžeme používat běžné příkazy pro práci se soubory, adresáři a textem. Můžeme v něm například procházet adresáře, vytvářet a mazat soubory, kopírovat je, hledat v jejich obsahu, pracovat s přesměrováním výstupu a rourami, spouštět skripty nebo upravovat text pomocí editoru nano.

## Linux

- Debian, Ubuntu, Mint: 
  ```bash
  $ sudo apt install git
  ```
- Fedora:
  ```bash
  $ sudo dnf install git
  ```

## macOS

```bash
% xcode-select --install
```

Případně stáhnout z [https://git-scm.com/download/mac](https://git-scm.com/download/mac)

Příoadně, pokud používáte `brew`, nainstalovat jej pomocí něho:

```bash
% brew install git
```


