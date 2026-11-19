
# Markdown

<img src="img/markdown-logo.png" width="100">

Markdown je jednoduchý značkovací jazyk pro formátování prostého textu. Umožňuje snadno vytvářet nadpisy, seznamy, odkazy, tabulky nebo části kódů.

V Gitu se používá hlavně v souboru `README.md`, který slouží jako **dokumentace projektu**. Na GitLabu či GitHubu se automaticky zobrazuje na hlavní stránce repozitáře. Dle zvyklostí se jeho název píše velkými písmeny. 

Přípona markdown souboru je `.md`.

- 🌐 Dokumentace: [https://markdowncheatsheet.com/reference](https://markdowncheatsheet.com/reference)
- 🌐 Online editor: [https://stackedit.io/app#](https://stackedit.io/app#)


Ukázka:

```md
# Hlavní nadpis
## Menší podnadpis
### Ještě menší nadpis

Vlastnosti textu: **tučně**, *kurzíva* a ‘neproporcionální‘.

- toto
- je nečíslovaný
- seznam

1. toto
2. je číslovaný
3. seznam

Odstavce se oddělují

prázdným řádkem. Na délce řádků nezáleží.

Odkaz na [školní GitLab](https://gitlab.panska.cz)

Vodorovná linka jsou tři pomlčky:

---

Programový kód:

‘‘‘c
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
  return 0;
}
‘‘‘
```

