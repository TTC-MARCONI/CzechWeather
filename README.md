# CzechWeather
CzechWeather je meteorologický portál, který spojuje všechny amatérské měřiče ovzduší.

>Portál je veden čistě jako hobby platforma, která se pomalu rozvíjí. Může vykazovat různé chyby či výpadky.

![image](https://user-images.githubusercontent.com/50009854/141790289-914f2f40-d3a3-4cef-b386-50ff5119908c.png)


# Jak se připojit?
### Registrace
Není nic jednoduššího, než se zaregistrovat na stránkách www.czechweather.cz/profile a přihlásit svou hobby meteorologickou stanici.

### Po registraci
Po zaregistrování na svém profilu uvidíš záložku "Stanice". Po rozkliknutí zjistíš, že tam zatím žádné nemáš. Ikonkou podle obrázku níže si jí ale můžeš ihned přidat.

![image](https://user-images.githubusercontent.com/50009854/141759664-9ed7ca84-78cb-47a0-9e0a-a3ac19580cfd.png)

Po jejím pojmenování a stisknutím tlačítka "Přidej" získáš přístupový klíč, který slouží k přístupu do systému při zasílání dat.

![image](https://user-images.githubusercontent.com/50009854/141760780-31d331e7-1955-45dc-be08-c38d8e85cae4.png)

Tvá stanice je přidána a nastavena v testovacím režimu. To znamená, že každá zaslaná zpráva bude označena jako testovací a nebude zobrazována na veřejném přehledu ani započítána do analytických funkcí. Ty však tento záznam můžeš vidět ve výpisu.

![image](https://user-images.githubusercontent.com/50009854/141761752-2a8e07a8-9dfb-4745-9131-d82b1411d822.png)

Ovládání stanice je naprosto jednoduché.

![image](https://user-images.githubusercontent.com/50009854/141762567-e341a227-73c1-4747-887c-90dc0535e888.png) Editace jména, přístupového klíče a test režimu.

![image](https://user-images.githubusercontent.com/50009854/141766884-bbef9fa3-16e3-4f4c-a99a-7e37c95b1016.png) Výpis zaslaných hodnot a jejich smazání.

![image](https://user-images.githubusercontent.com/50009854/141767160-ad7264ab-5fcd-4bed-802c-d7a0a2af50d2.png) Smazání stanice (při odebrání zanikne stanice i její záznamy).

Časem jiste přibudou další, ale všechno chce čas :) 

### Zasílání měření
Portál využívá univerzálního REST API rozhraní. Jediné co musíš je dodržet správný JSON formát zasílaných zpráv a klíč uložený v hlavičce.
> Adresa pro využití rozhraní je https://czechweather.cz/api/MeteoStation/InsertData

##### Hlavička
> Content-type: application/json

##### Formát Klíče v hlavičce
> stationkey: váš vygenerovaný klíč

##### JSON formát
>{"Latitude":double,"Longitude":double,"Temperature":double,"Humidity":double,"Pressure":double}

>Příklad: {"Latitude":49.0636,"Longitude":13.3985,"Temperature":3.4,"Humidity":85.0,"Pressure":1021.0}

##### Celá zpráva vypadá následovně.
![image](https://user-images.githubusercontent.com/50009854/141772347-3f1a4758-d319-4241-925a-a14b5a6a24d3.png)

##### Omezení
Přijímání zpráv je omezeno na jednu zprávu za 60 minut. Pokud v budoucnu usoudíme, že je potřeba sbírat vrozky častěji, jistě vám dáme vědět :)

# Závěrečné unstanovení
- CzechWeather je plně zdarma a veden za účelem sjednocení hobby meteorologů.
- Snažte se zasílat data co nejpřesnější a periodicky.
- Při zjištění velkého výskytu nereálných hodnot v netestovacím režimu si CzechWeather vyhrazuje právo údaje smazat či účet úplně uzavřít.
- Poskytnuté údaje jsou využívány jen pro účel funkce portálu či zaslání důležitých změn. Nejsou poskytovány třetím stranám.
- Zaslaná měření se stávají majetkem CzechWeather a může s nimi být nakládáno bez souhlasu zasílatele.
