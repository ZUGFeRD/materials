# ZUGFeRD/Factur-X/Order-X/Deliver-X Frequently Asked Questions 
## Stand B2B
Vermittlungsausschuss vgl https://dip.bundestag.de/vorgang/gesetz-zur-st%C3%A4rkung-von-wachstumschancen-investitionen-und-innovation-sowie-steuervereinfachung/303318?term=Wachstumschancengesetz&f.wahlperiode=20&rows=25&pos=1
Details und Hintergründe https://www.heise.de/hintergrund/Pflicht-zur-E-Rechnung-im-XML-Format-Das-ist-der-Status-quo-9593920.html (kostenpflichtig) oder https://medium.com/@jochen.staerk/why-and-how-germany-bans-b2b-paper-invoices-a4c7977f314a

## Abkürzung: Was heißt eigentlich ZUGFeRD?
ZUGFeRD hieß mal Zentraler User Guide Forum elektronische Rechnung Deutschland.
Das "ZUG" im Name war möglicherweise eine Hommage an die MUG, die Message User Group, die 
CWA erarbeitete und damit definierte welche Teilmenge bspw. von CII für den
europäischen Gebraucht wichtig ist: USt bspw, ja, Nordamerikanische Sales tax bspw. nein.
Der internationale Name wurde Factur-X. 
Aus historischen Gründen wurde Factur-X 1 released als ZUGFeRD gerade Version 2 erreichte,
ZUGFeRD 2 entspricht also Factur-X 1.

Nach Order-X und nach Beginn aber vor Abschluss der Arbeiten (an Lieferscheinen, genannt
Deliver-X) wurde ZUGFeRD zur Formatfamilie: Der Begriff wechselte in den Plural,
Zentrale User Guides Forum elektronische Rechnung Deutschland, die Abkürzung blieb
(vgl https://www.ferd-net.de/aktuelles/meldungen/rueckblick-auf-die-sitzung-des-ferd-plenums.html).


## Europa
mit dem EU-Richtlinienentwurf Vat in the Digital Age (ViDA) https://audiovisual.ec.europa.eu/en/topnews/M-009199 arbeitet man dran, zumindest was grenzüberschreitende Geschäfte angeht.

Und ViDA möchte da auf dem B2G-E-Rechnungsstandard EN16931 aufbauen. 

## Was ist ein USt-Meldesystem

Es gibt eine ganze Reihe von möglichen Umsatzsteuermeldesystemtypen (vgl Kollmann https://www.pagero.com/downloads/documents/compliance/Next_Generation_Model-Decentralised_CTC_and_Exchange_v1.pdf S.6: Italien ist Centralized Clearance, EU~Frankreich ist EESPA, i.e. Decentralized CTC and Exchange) und Deutschland versucht schonmal mit der Vorgabe, EN16931 zu benutzen kompatibel zum zukünftigen europäischen System zu werden.


## XRechnung automatisiert
Die Kosit, sozusagen die Behörde für Behördenrechnungen, hat sich dem EDI-Netzwerk Peppol angeschlossen und den API-Zugriff aufs ZRE eingestellt. Das bedeutet die einzige Möglichkeit Behördenrechnungen in Deutschland komplett automatisiert einzureichen ist über Peppol. Man muss die Peppol-Rechnung nicht nur weiterhin ans richtige Portal addressieren, man muss sich wohl auch bei jedem Portal vorher kurz (immerhin automatisiert) freischalten.

## PDF
Converting any PDF input to PDF/A-3 is out of scope for the mustangproject tool&library, because it is too complex, you can not just filter out some things, usually you need to completely rebuild a valid pdf/a, ghostscript  is a very good and AFAIK the only open source solution which can handle that (see https://github.com/ZUGFeRD/mustangproject/issues/164#issuecomment-640046774).

Please note that it's out of scope for the tool&library does not mean that it's out of scope for mustang server, which could use ghost4j for that, actually I do have some ghost4j-questions.

## Ghostscript, general

Ghostscript did an amazing work years ago already and implemented the functionality (Ext_Metadata https://www.ghostscript.com/doc/VectorDevices.htm#Extensions) which was required to generate proper ZUGFeRD PDFs. They did not announce it very much but https://bugs.ghostscript.com/show_bug.cgi?id=696472 gives you a start in case you are interested.

## Netto

§6.4.3.1.1

## EN16931-1

https://www.beuth.de/en/standard/din-en-16931-1/314992770

## Gutschrift

echte kaufmännische Gutschrift: irgendein nicht-380er typecode, kein Minus ABER Stornorechnung (und das ist was 90% mit Gutschrift meinen): negative Menge->negativer Preis, negative USt also praktisch alles Minus. Typecode bei Stornorechnung ich meine 384, es gibt ein offizielles ZUGFeRD-Beispiel.


## XR Version gültig

https://www.xoev.de/xrechnung-16828

## Schematron
if you e.g. want to check the CEN schematron you might have to get that schematron, java, saxon, and the "ISO Schematron" transformation and run saxon with the ISO Schematron to create a XSLT-File from the schematron file and then run this generated XSLT file on your input. There is a description for mac on  https://blog.eight02.com/2011/05/validating-xml-with-iso-schematron-on.html

## XRechnung Referenzprofil CII
XRechnung für UBL und UN/CEFACT definiert ist, ZUGFeRD aber selbst im Referenzprofil XRechnung ausschließlich ein UN/CEFACT-Format ist. Im Review hielt man die entsprechende Erwähnung (Abschnitt 3.2.4 auf S.13) für ausreichend.

## Nachkommastellen
Meines Wissens dürfen Mengen und Preise zwar vierstellig sein (vgl. die englische Factur-X Spezifikation 1.0.50, Kap 7.1.5), die Position muss dann aber auf zweistellige Summen gerundet werden - und die Summe der Positionen mit demselben Umsatzsteuersatz führt zum zweistelligen Umsatzsteuerbetrag für diesen Satz. Siehe auch EN16931-1 Kap. 6.5.12, dort sind nettopreise interessanterweise zweistellig notiert.


## Order-X
Public review 1 https://www.ferd-net.de/aktuelles/meldungen/public-review-des-entwurfs-fuer-order-x-hat-begonnen-und-laeuft-bis-ende-september-2020.html

## B2B
Italien https://ec.europa.eu/cefdigital/wiki/download/attachments/68331443/CEF%20eInvoicing_2018-12-04%20Stanziale%20-%20Brussels%20%285%29.pdf

Frankreich https://www.edicomgroup.com/en_US/news/13617-france-prepares-for-mandatory-b2b-e-invoicing.html


Deutschland https://www.verband-e-rechnung.org/pdfs/VeR-Studie_Clearance_2020.pdf


## OpenSource
I have tried to document other open source solutions on https://www.zugferd.org/

## HATE
Rechnung

1x123,45  19%

1x123,45  19%

Netto 246,90

Ust-Betrag  ?

Brutto  ?


Vertikal (IMO richtig) addiert man die netto preise zusammen zu 246,90-> *0,19=46,911 gerundet 46,91 USt -> also 293,81 brutto

1x123,45  19%

1x123,45  19%

Netto 246,90

Ust-Betrag ~46,91

Brutto 293,81


Macht man den Fehler und rechnet pro Zeile 123,45 netto *0,19 bekommt man 23,4555->23,46 Ust pro Zeile, das heißt ein einzelner Posten 123,45 kostet brutto 141,91. Addiert man dann allerdings versehentlich die Rundungsfehler bekommt man
*** FALSCH ***
1x123,45  19% (brutto ~146,91)

1x123,45  19% (brutto ~146,91)

Netto 246,90 (brutto ~293,82)

Ust-Betrag (vermeintlicher brutto minus netto ) 46,92

Brutto 293,82
*** ENDE FALSCH ***

Das ist ein schöner glatter und vor allem runder Bruttobetrag für 2 Positionen, aber IMO eben leider falsch.
Und es steht sogar im kostenlos erhältlichen EN16931-1 https://www.beuth.de/en/standard/din-en-16931-1/314992770 dass es falsch ist, sogar mit einem eigenen (ebenfalls wahrscheinlch zufällig gewähltem) Zahlenbeispiel, s. Seite 119, bei 25% Steuern:

Ust-betrag nettobetrag
35,56    142,25
17,84    71,37
14,96    59,85
10,56    42,25
4,84     19,37
4,84     19,37
ist eben NICHT (***ACHTUNG FALSCH***)
88,60   +354,46= 443,06
SONDERN eben 354,46*0,25=88,615~88,62 also
88,62   +354,46= 443,08


## Schritte neues Attribut

1) create a XML test file which validates, e.g. using an accoring Schema file binding in Intellij and validate with mustang

2) decide if e.g. a string value is sufficient or if a structure needs to be implemented. In your case you will almost for certain need some ExchangeCurrency class because we're talking about multiple attributes like exchange rate and date of the exchange rate

3) add an according unit test

4) implement it in the interface

5) add according code to the ZUGFeRD2pullprovider to generate the according XML

6) add accrding methods in the invoice class


## How can I write
### Requirements
### How can I check
## What is the content-difference between ZUGFeRD/Factur-X and XRechnung 

## Where can I ask questions
## How can I read

## Where do I get examples

## Mustang effort

My aim is to provide tools which, at least for SMEs, understand invoices and help e.g. SMEs implement their e-invoices and then they can choose if they want a XRechnung, a Factur-X or maybe sometimes a FatturaPA or a UBL.

https://www.openhub.net/p/mustangproject/estimated_cost  estimates I invested 653,000€ in Mustangproject . I would say that's enough but I'm still contributing. Also owed to the fact that other people contributed. My total revenue until now is probably not even five digits. And these 650k€ do not even count how much time I invest in the (community work, e.g. the homepage and) governance, e.g. I wrote a validator, automated tests and I am currently sitting in a Strasbourgh Hotel because I'm attending a conference where AWVs CC3 and FNFE convene to decide on future factur-x versions and launch Deliver-X.

The fact that Factur-X is based on PDF/A and hardly any tool seems to be capable of exporting valid PDF/A is not really a core concern, e.g. LibreOffice does a very good export and I tried to describe on http://zugferd.org/ what incredibly good job Ghostscript did.

Making e-invoices more accessible: I'm trying my very best, I can't possibly make it more accessible, I'm practically on the verge of bankrupcy for it. We need everybody in the standard bodies (I can introduce you, I can show you around, actually we need three more XML guys in CC3 alone) and I need every contribution to Mustang and Mustangserver. So: May I politely inquire if you plan to contribute? 

## GoBD


Grundsätze zur ordnungsmäßigen Führung und Aufbewahrung von Büchern, Aufzeichnungen und Unterlagen in elektronischer Form sowie zum Datenzugriff

https://ao.bundesfinanzministerium.de/ao/2021/Anhaenge/BMF-Schreiben-und-gleichlautende-Laendererlasse/Anhang-64/anhang-64.html

Muster-Verfahrensdokumentation zum ersetzenden Scannen https://www.bstbk.de/downloads/bstbk/steuerrecht-und-rechnungslegung/fachinfos/BStBK_Muster-VerfD-ersetzendes-Scannen_v2.0-2019-11-29.pdf

Muster-Verfahrensdokumentation für Belegablage https://www.awv-net.de/upload/pdf/Belegablage_V1_20151026.pdf nachschiebe


## Codelisten

https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Registry+of+supporting+artefacts+to+implement+EN16931

## Where do I get schema files/further info
Schema, Schematron, Samples, Spec, Reference and Codelists are available via 
the ZF Infopaket https://www.ferd-net.de/ZUGFeRD-Download



## Was ist der Unterschied zwischen Factur-X und ZUGFeRD
Factur-X 1.0.50 ist der französische und internationale Name von ZUGFeRD 2.1. Der Factur-X-Dateiname (factur-x.xml) und Metadaten (RDF-Metadaten mit dem Namespace Prefix „fx“) sind seit ZUGFeRD 2.1 bevorzugt.

## Ist meine Berechnungsmethode korrekt? 
Die Berechnung von elektronischen Rechnungen ist im Rahmen von EN16931-1 normiert, das kostenlos online bezogen werden kann, in Deutschland im Shop der DIN angegliederten Beuth Verlags.
https://www.beuth.de/en/standard/din-en-16931-1/314992770

## Welche Attributwerte kann ich verwenden?
Die entsprechenden Codelisten werden vom CEF verwaltet und veröffentlicht. Sie sind Teil des ZUGFeRD Infopakets.
Gibt es kostenlose Tools?
Unter http://zugferd.org/ gibt es eine Liste von Open-Source-Tools die direkt oder indirekt mit ZUGFeRD zu tun haben. 

## Kann ich alle PDF-Dateien für ZUGFeRD verwenden?
ZUGFeRD basiert auf archivierbaren (PDF/A) PDFs, die alle zur Darstellung benötigten Daten wie Schriftarten einbetten. Eine kostenlose Möglichkeit „normale“ PDF-Dateien zu konvertieren stellt beispielsweise Ghostscript dar. 

## Wie sieht eine ZUGFeRD-Datei aus
Abgesehen von der Identifikation in den Metadaten ist beispielsweise im Adobe Reader ist eine ZUGFeRD-Datei durch Hinweis auf PDF-A und das Büroklammersymbol mit der eingebetten Datei zugferd-invoice.xml oder factur-x.xml ersichtlich. 


