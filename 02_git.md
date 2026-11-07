# Git

<img src="img/git-logo.png" width="100">

## Stručná historie

Tak jako mnoho velkých věcí v lidské historii se i systém Git zrodil z kreativní destrukce a vášnivého sporu. Jádro Linuxu je software s otevřeným kódem a širokou škálou využití. V letech 1991 – 2002 bylo jádro Linuxu spravováno formou záplat a archivních souborů. V roce 2002 začal projekt vývoje linuxového jádra využívat komerční systém DVCS s názvem **Bit-Keeper**.

V roce 2005 se zhoršily vztahy mezi komunitou, která vyvíjela jádro Linuxu, a komerční společností, která vyvinula BitKeeper, a společnost přestala tento systém poskytovat zdarma. To přimělo komunitu vývojářů Linuxu (a zejména Linuse Torvaldse, tvůrce Linuxu), aby vyvinula vlastní nástroj, založený na poznatcích, které nasbírala při užívání systému BitKeeper. 

Mezi požadované vlastnosti systému patřily zejména:

- rychlost;
- jednoduchý design;
- silná podpora nelineárního vývoje (tisíce paralelních větví);
- plná distribuovatelnost;
- schopnost efektivně spravovat velké projekty, jako je linuxové jádro (rychlost a objem dat).

Od svého vzniku v roce 2005 se Git vyvinul a vyzrál v snadno použitelný systém, který si dodnes uchovává své prvotní kvality. Je extrémně rychlý, velmi efektivně pracuje i s velkými projekty a nabízí skvělý systém větvení pro nelineární způsob vývoje.

Hlavním rozdílem mezi systémem Git a všemi ostatními systémy VCS (včetně Subversion a jemu podobných) je způsob, jakým Git zpracovává data. Většina ostatních systémů ukládá informace jako seznamy změn jednotlivých souborů. Tyto systémy (CVS, Perforce, Bazaar atd.) chápou uložené informace jako sadu souborů a seznamů změn těchto souborů v čase.

Git zpracovává data jinak. Chápe je spíše jako sadu snímků (snapshots) vlastního malého systému souborů. Pokaždé, když v systému zapíšete (uložíte) stav projektu, Git v podstatě „vyfotí“, jak vypadají všechny vaše soubory v daném okamžiku, a uloží reference na tento snímek. Pokud v souborech nebyly provedeny žádné změny, Git v zájmu zefektivnění práce neukládá znovu celý soubor, ale pouze odkaz na předchozí identický soubor, který už byl uložen.

## Téměř každá operace je lokální

Většina operací v systému Git vyžaduje ke své činnosti pouze lokální soubory a zdroje a nejsou potřeba informace z jiných počítačů v síti. Celou historii projektu máte uloženou přímo na svém lokálním disku.

Pokud chcete například procházet historii projektu, Git kvůli tomu nemusí vyhledávat informace na serveru – načte ji jednoduše přímo z vaší lokální databáze. Znamená to, že se historie projektu zobrazí téměř neprodleně. Pokud si chcete prohlédnout změny provedené mezi aktuální verzí souboru a týmž souborem před měsícem, Git vyhledá měsíc starý soubor a provede lokální výpočet rozdílů, aniž by o to musel žádat vzdálený server nebo stahovat starší verzi souboru ze vzdáleného serveru a poté provádět lokální výpočet.

To také znamená, že je jen velmi málo operací, které nemůžete provádět offline nebo bez připojení k síti. Jste-li v letadle nebo ve vlaku a chcete pokračovat v práci, můžete beze všeho zapisovat nové revize. Ty se načtou ve chvíli, kdy se opět připojíte k síti. Jestliže přijedete domů a zjistíte, že připojení k síti nefunguje, stále můžete pracovat. V mnoha jiných systémech je takový postup nemožný nebo přinejmenším obtížný. 

> Například v systému Perforce toho lze bez připojení k serveru dělat jen velmi málo, v systémech Subversion a CVS můžete sice upravovat soubory, ale nemůžete zapisovat změny do databáze, neboť ta je offline. Možná to vypadá jako maličkost, ale divili byste se, jaký je to velký rozdíl.

## Git pracuje důsledně

Než je v systému Git cokoli uloženo, je nejprve proveden kontrolní součet, který je potom používán k identifikaci dané operace. Znamená to, že není možné změnit obsah jakéhokoli souboru nebo adresáře, aniž by o tom Git nevěděl. Tato funkce je integrována do systému Git na nejnižších úrovních a je v souladu s jeho filozofií. Nemůže tak dojít ke ztrátě informací při přenostu dat nebo k poškození souboru, aniž byto byl Git schopen zjistit.

Mechanismus, který Git k tomuto kontrolnímu součtu používá, se nazývá otisk SHA-1 (SHA-1 hash). Jedná se o řetězec o 40 hexadecimálních znacích (0–9; a–f) vypočítaný na základě obsahu souboru nebo adresářové struktury systému Git. Otisk SHA-1 může vypadat například takto:

```
24b9da6552252987aa493b52f8696cd6d3b00373
```

S těmito otisky se budete setkávat ve všech úložištích systému Git, protože je používá opravdu často. Neukládá totiž soubory podle jejich názvu, ale ve své databázi podle otisku (hashe) jeho obsahu.

## Git většinou jen přidává data

Jednotlivé operace ve většině případů jednoduše přidávají data do Git databáze. Přimět systém, aby udělal něco, co nelze vzít zpět, nebo aby smazal jakákoli data, je velice obtížné. Stejně jako ve všech systémech VCS můžete ztratit nebo nevratně zničit změny, které ještě nebyly zapsány. Jakmile však jednou zapíšete snímek do systému Git, je téměř nemožné ho ztratit, zvlášť pokud pravidelně zálohujete databázi do jiného repozitáře.

Díky tomu vás bude práce se systémem Git bavit. Budete pracovat s vědomím, že můžete experimentovat, a neriskujete přitom nevratné zničení své práce.

---

Tento text a další věci najdete ve zdarma dostupné knize **Pro Git** autora Scotta Chacona (2010)
[https://www.root.cz/knihy/pro-git/](https://www.root.cz/knihy/pro-git/)

