# Intrinsieke Veiligheid binnen systeemarchitectuur
Over Cyber Security wordt veel gepraat. Iedereen ziet de noodzaak, heeft er behoefte aan maar heeft ook veel vragen. Wat is nu de oplossing? Wat moeten we concreet doen?

Ondanks dit bewustzijn bestaan er nog veel systemen met databases waar wachtwoorden in platte tekst zijn opgeslagen. Hiervan zijn we ons bewust dat dit niet handig is en dus wordt het ook niet vereist door klanten. Dat is wel het laatste. Maar wel zien we dat klanten technische keuzes (bv. architectuur) voorschrijven die lijnrecht staan tegenover een maatschappelijk verantwoord en gemeenschappelijk doel, veilige systemen.

Een oplossing is bijvoorbeeld intrinsieke veiligheid. Wat betekent dat eigenlijk? Intrinsiek staat voor ‘als iets uit jezelf komt’. Intrinsieke veiligheid is een systeem creëren waarbij veiligheid binnen ieder deelsysteem zelfstandig wordt gecreëerd. Hiervoor is het nodig om gebruik te maken van decentrale intelligentie. Dat houdt in dat systemen eigen intelligentie (_besturing_) hebben en tezamen een samengesteld veilig systeem realiseren.

> Een oplossing is bijvoorbeeld intrinsieke veiligheid

Traditioneel kiezen we in de infra of industrie bij grote installaties zoals een tunnel voor één of enkele zware besturingen (_PLC_) die de gehele tunnel of een tunnelbuis aansturen. De meeste deelinstallaties (_LFV / Logische Functie Vervuller_) worden gekoppeld aan deze centrale besturingen via remote IO en bevatten zelf geen intelligentie. Deze systeem architectuur wordt veelal voorgeschreven en ook gebruikt in andere branches. Een traditionele keuze daar vroeger besturingen met intelligentie een kostbaar onderdeel uitmaakte van de installatie en er dus zo min mogelijk besturingen aanwezig waren. Maar is dat tegenwoordig nog zo?

Met het oog op veiligheid schermen we dit gehele systeem hermetisch af naar de buitenwereld. Het is niet gekoppeld aan internet of afgeschermd met dikke firewalls en andere techniek. We denken daarmee veilig te zijn. Maar hoe veilig zijn we nu echt?

In de praktijk blijkt dat hackers altijd wel een weg vinden om op je netwerk actief te geraken. Zij het door toegang via normale gebruiker accounts met behulp van wachtwoorden verkregen via phishing of andere systemen met verouderde beveiliging zoals de onbeveiligde wachtwoorden. Zelfs de beveiliging van een ‘niet aan internet’ gekoppeld systeem valt te betwijfelen. Een hacker heeft toegang nodig tot dit netwerk en die vinden we via een vrije netwerkpoort, wifi router of een minder beveiligd deelsysteem in het netwerk. Kortom, binnen komen is de eerste drempel die wel genomen kan worden.

> In de praktijk blijkt dat hackers altijd wel een weg vinden om op je netwerk actief te geraken

En dan is er meestal geen belemmering meer. Industriële systemen zijn gekoppeld via modbus, profibus of andere bus systemen. Computers zitten allemaal in één netwerk of we hebben zelfs maar één besturing ingezet. Zijn we binnen op het netwerk dan hebben we gelijk toegang tot de meeste, zo niet alle, systemen op dit netwerk. Via bus communicatie kunnen we het gehele netwerk uitlezen en aansturen.

Eigenlijk is dit vreemd. Een goed beveiligd gebouw bestaat ook niet alleen uit een toegangspoort bij de ingang. Ben je binnen moet je voor beschermde ruimtes opnieuw toegang verkrijgen. We denken nu aan pasjes en dergelijk, maar denk ook eens aan de gewone sleutel. Iedere kamer sluiten we netjes achter ons af zodat anderen van buiten niet naar binnen kunnen. De kamer is intrinsiek beveiligd, van binnenuit met een sleutel. Waarbij jij als persoon de toegang regelt. Wellicht door iemand anders een sleutel te geven die daarmee ook naar binnen kan.

> Een goed beveiligd gebouw bestaat ook niet alleen uit een toegangspoort bij de ingang

Intrinsieke veiligheid in de systeem architectuur werkt hetzelfde. Dit is niet nieuw en wordt binnen de IT al jaren toegepast. Dit werkt als volgt.

We werken met een sleutel ofwel toegangscode (_access_token_). Dit is een tekst die beschrijft waar de eigenaar toegang toe heeft (_scope_) op een gestandaardiseerde manier (_Jason Web Token_ ofwel _JWT_). Deze sleutel bevat een handtekening. Deze handtekening kan alleen gecontroleerd worden door het systeem zelf met een geheime code (_client_secret_) die alleen het systeem zelf kent. Is de sleutel aangepast dan klopt de bijbehorende handtekening niet en wordt een malafide aanroep gelijk geblokkeerd vanuit het systeem zelf. Dit wordt ook gelijk gemeld waardoor iedereen op de hoogte is van malafide praktijken en actie kan ondernemen. Zonder juiste sleutel heeft dus niemand toegang tot het systeem ook al heeft hij toegang tot het netwerk.

Deze aanpak is de “sleutel” naar een veilig systeem. Geef deelsystemen, hoe klein en eenvoudig ook, lokale intelligentie. Er is geen argument dit niet te doen. Kijk om je heen en zelfs de knuffel van je kind of je koelkast kan een processor bevatten. We noemen dit IoT ofwel Internet of Things.

Kijk nu eens naar een tunnel met een tunnelbuis. Stel je nu eens voor dat een verkeerslicht, toegangsdeur of hulppost ieder hun eigen besturing hebben. Je kunt ze in dat geval plug and play aansluiten op het netwerk van de tunnelbuis en ze doen hun werk. Je kunt ze ook op internet aansluiten en afzonderlijk testen. Alles op een veilige manier. Iedere hacker die op het netwerk komt kan daar verder niets doen want deze systemen zijn intrinsiek beveiligd. Zonder juiste sleutel kan je ze niet bekijken of aansturen.

> Deze aanpak is de “sleutel” naar een veilig systeem

Een juiste keuze denkt u wellicht. Maar is het allemaal zo eenvoudig? Ja, daar zorgen we met zijn allen voor als we open staan, gaan samenwerken en afspraken maken. We hoeven het wiel niet opnieuw uit te vinden, dat hebben anderen al gedaan. Een veilig proces is nodig voor het overdragen van deze sleutels. Dat proces bestaat al in de vorm van OAuth. Alle systemen praten met elkaar op een afgesproken standaard manier (protocol) vastgelegd als OData. De invulling per systeem leggen we vast conform de Open API Standaard 3.0.

Nu is dit voor velen veel informatie, is er ook een kant en klare oplossing? Ja, die is er en deze wordt steeds verder uitgebreid. Open source, voor iedereen toegankelijk. Gebaseerd op Websocket, HTTP en SOAP techniek. Compleet uitgewerkte communicatie inclusief beveiliging werkend op Windows of Linux gebaseerd op PHP, Node, Javascript, hogere programmeertalen of PLC’s die HTTP ondersteunen.

De oplossingen zijn er dus wel. We moeten alleen niet kletsen maar doen. De markt moet openstaan voor IT techniek. Zolang we oude oplossingen voorschijven en niet open staan voor moderne techniek worden deze moderne oplossingen geblokkeerd. De cyber criminaliteit houdt zich niet aan traditie en oude techniek, ze misbruiken deze juist. En daar worden we mee geconfronteerd als het te laat is en we het niet meer kunnen voorkomen. Als we kennis en nieuwe techniek niet omarmen zal dat gebeuren, de vraag is dan alleen wanneer.

**Max van Kampen**  
Architect bij Alicon, ontwikkelaar van het Automation Integration Management Framework
