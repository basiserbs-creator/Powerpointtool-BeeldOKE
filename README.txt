BEELDOKE · POWERPOINTMAKER · TESTVERSIE 0.8.7

WIJZIGINGEN IN 0.8.7
- De standaardtemplate staat niet meer als base64 in index.html maar als losse
  assets/templates/uitvaartpresentatie-basis-v3-21082026.pptx.
- Nieuwe templates worden herkend via BeeldOKE_Hoofdfoto, BeeldOKE_Seriefoto en
  BeeldOKE_Muziekstart; oudere isPhoto-templates blijven als terugval ondersteund.
- Een hoofdfotodia wordt altijd handmatig gemaakt. Fototijden en muziekduur worden
  bij iedere presentatie opnieuw berekend uit het fotoaantal en de gekozen muziek.
- Het startbestand heet nu index.html en kan rechtstreeks vanuit de hoofdmap
  door GitHub en Netlify worden gepubliceerd.
- De ondernemerslogo's zijn vervangen door kusters-logo-1200x540.png en
  ruiver-logo-1200x540.png; oude bestanden en ingebedde oude klantlogo's zijn verwijderd.
- De PowerPointgeneratie uit ZIP en .beeldoke is ongewijzigd behouden.
- Standaard toont uitsluitend de algemene muzieklijst uit de eenvoudige v0.7.3-opzet.
- Fotoreekskaarten, timingkeuzes, trim, fades en vaste fototijd zijn uitsluitend
  zichtbaar in Uitgebreid.
- Zowel de woorden Standaard en Uitgebreid als de schakelaar zijn klikbaar.
- De header volgt de randloze driedelige BeeldOKE-opbouw: Ookwood links, het
  ondernemerslogo in het midden en het nieuwe groen-zwarte BeeldOKE-logo rechts.
- Het Ookwood-logo is klikbaar en opent Ookwood Gedenken in een nieuw tabblad.
- Terug naar BeeldOKE en Uitloggen staan compact en zonder logo-overlap rechtsboven.
- Het oude donkerblauwe logo wordt nergens gebruikt en is niet meegeleverd.

Deze map is direct geschikt voor Git en Netlify. Omdat de standaardtemplate als
los bestand wordt geladen, moet de map via Netlify of een lokale webserver worden
geopend; rechtstreeks dubbelklikken op index.html is voor deze webbuild niet bedoeld.
Deze testbuild toont na openen een knop “Testmodus openen”. In de latere geïntegreerde
productiebouw wordt STANDALONE_TEST_BUILD op false gezet en is een ondernemerssessie verplicht.

1. Publiceer de volledige map via Git/Netlify en open de Netlify-URL.
2. Voeg de toegestane ZIP-bestanden of BeeldOKE-projecten toe en bepaal de volgorde.
3. Kies één hoofdfoto. Deze verschijnt vóór, tussen en na de fotoreeksen.
4. De tool start altijd in Standaard. Voeg muziek toe en wijzig de volgorde met de
   pijlen; muziek 1 hoort bij fotoreeks 1, muziek 2 bij fotoreeks 2, enzovoort.
   Schakel naar Uitgebreid voor meerdere nummers per reeks, trimmen, fades en een
   vaste tijd per foto.

De driedelige header gebruikt links Ookwood, in het midden het logo uit de
gevalideerde ondernemerssessie en rechts BeeldOKE. De favicon is gelijk aan die
van het fotoplatform.
5. Klik op “Maak presentatie” en daarna op “Genereer PowerPoint”.

Bij ieder gekozen bronbestand toont de tool direct hoeveel foto's of projectbeelden
het bevat. Het eindoverzicht vermeldt dit aantal ook afzonderlijk per fotoreeks.

Onder “Naam van de PowerPoint-presentatie” kan een eigen bestandsnaam worden ingevuld.
Als dit veld leeg blijft, gebruikt de tool automatisch:
Uitvaartpresentatie [volgnummer] [ddmmjjjj].pptx
Het volgnummer loopt lokaal op na iedere geslaagde presentatie met de standaardnaam.

Elk ZIP-bestand of BeeldOKE-project vormt een eigen fotoreeks. Het aantal fotodia’s
van iedere reeks wordt automatisch aangepast aan het aantal foto’s in die bron.

De tool leest per reeks de gekozen muziekfragmenten en deelt hun gezamenlijke duur exact
door het aantal foto's. Bij een fragment van 2:33 en 36 foto's wordt iedere fotodia
4,25 seconden getoond.
Afrondingsmilliseconden worden verdeeld, zodat alle diatijden samen exact gelijk zijn
aan de muziekduur. Als 'vaste tijd per foto' wordt gekozen, blijft die fototijd leidend
en wordt het samengestelde muziekblok op de benodigde totale duur gebracht.

Alleen muziek die de gebruiker zelf koppelt wordt gebruikt. Templatemuziek wordt altijd
verwijderd. Een reeks kan stil blijven, één nummer gebruiken of meerdere nummers achter
elkaar afspelen. Voor een stille reeks geldt de vaste gekozen tijd of standaard 4 seconden.

BeeldOKE-projecten worden automatisch herkend als oud JSON-project of als het nieuwe
v4.5.16-containerformaat met project.json en losse foto's. De ondernemer kan de
toegestane soorten bronbestanden niet in deze tool wijzigen; dit hoort bij het beheer.

Muziek wordt rechtstreeks binnen de gewenste fotoreeks toegevoegd. Ieder nummer heeft
een eigen contrastrijke speler met een blijvend zichtbare positie op tienden van seconden.
Gebruik desgewenst de huidige pauzepositie als begin of einde. Fade-in en fade-out zijn
afzonderlijk instelbaar van 0 tot 10 seconden en zijn direct hoorbaar in de preview.

Foto’s uit BeeldOKE-projecten volgen dezelfde zoom-, positie- en collageberekening als
het fotoplatform. Staande foto's worden passend geplaatst; liggende foto's vullen het
beeld. Hoofdfotodia’s gaan uitsluitend na een klik verder.
De hoofdfoto wordt vóór plaatsing lokaal genormaliseerd, zodat EXIF-camerarotatie niet
kan leiden tot een gedraaide of uitgerekte foto in PowerPoint.

De losse standaardtemplate is Uitvaartpresentatie template BASIS V3- 21082026.pptx.
Een andere PPTX of POTX kan worden gekozen als deze dezelfde herkenbare structuur gebruikt.

Alles gebeurt lokaal in de browser; de bestanden worden niet geüpload.

De oude hulplabels “eerste foto” en “laatste foto” uit de testtemplate worden niet in
de gegenereerde presentatie opgenomen.
