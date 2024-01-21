
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

## Gartenzaun


Ulrike Linde
am
23. Februar 2020


die Konstruktion der URIs für CIUS und Extensions ist in TR16931-5 Kapitel 6.8 beschrieben. Kapitel 6.9 formuliert Empfehlungen zur Validierung:



The creation of the validation artefacts can be done in two main ways.

- By modifying the validation artefacts from the underlying specification. In this case the invoice
  instance document may be validated with a single set of artefacts in one run.

- By creating an new set of validation artefacts that only tests for the differences that are defined by
  the extension specification.



Although both approaches may be used, their technical feasibility depends on the nature of the extensions. When both approaches are feasible the second one is preferred since the differences between the extension specification and its underlying specification can be better monitored when these two sets are run sequentially. This also reduces the risk that the extension specification that is created, results in not-conformant invoice instances without that being identified until the extension specification is in full production.

( Der Text ist der FprCEN TR 16931-5 entnommen, daher bitte nochmal mit der finalen Version vergleichen.)



Das Argument von Andreas ergibt sich implizit: Er wird nur für Extensions von einer Anpassung der Validierungsartefakte gesprochen. Im Umkehrschluss würde dies bedeuten, dass für alle CIUS derselbe Validierer genutzt werden soll.



Allerdings ist Teil 5 nur ein Technical Report und nicht verbindlich wie die Norm EN16931-1. Wir hatten im CEN schon einmal darüber gesprochen, die Formulierungen aus Abschnitt 6.8 und 6.9 TR19531-5 in Kapitel 7 der EN16931-1 aufzunehmen, aber das geht nur im Rahmen eines Amendments.

## DevSupport
Hi,
First of all: Thanks for your interest in my project you can use for free both commercially and noncommercially.

Even if you forgot to write it, I assume you at least mentally wanted to thank me for that: You are very welcome.

You can book me for commercial support.

For community support (i.e. noncommercial/free support) please refer to https://groups.google.com/g/zugferd, where I also frequently responding to questions.

This does not only help you faster (because other community members may be able to answer some of your questions), it also helps to keep a record of frequently asked questions I need to document better in the future.

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


## Mustangserver
The Java Mustang library and command line tools are open source, but as there were never substantial community contributions to Mustangserver we decided to publish the newer versions proprietary. That will most likely remain like this, unless our internal legal audit tells us otherwise.

If you want to contribute to the initial (open source, Dropwizard based) versions of Mustangserver: the source code is still available on Github. I think it was still called Mustang Rest API at that point.

Otherwise: feel free to subscribe to Mustangserver, if you want I can send you the contract in english (I believe on the website the draft is only german). 


## Mustangserver onboarding

Hi,

Please use username <> with the password <> on  https://api.usegroup.de

A manual is available on https://www.mustangproject.org/files/manual-0.8.0.pdf.

Feel free to use it for some weeks, I attached a draft contract how the final agreement could look like.

Quick start: If you select the most recent version on https://api.usegroup.de, login and select click on the blue "try out" button (not the link in the navigation) on the next page you should be able to click a "get test key" button.

e.g. when you open the "ping" operation and click "try it out" and "execute" you should get a "pong" response.

Of course the whole thing is a openapi/swagger, so you can import it in postman or generate clients for 56 programming languages on https://editor.swagger.io/ .

Is that OK/understandable? Is the performance OK?

Are there any operations you miss?


## Opensource

My aim is to provide tools which, at least for SMEs, understand invoices and help e.g. SMEs implement their e-invoices and then they can choose if they want a XRechnung, a Factur-X or maybe sometimes a FatturaPA or a UBL.

https://www.openhub.net/p/mustangproject/estimated_cost  estimates I invested 653,000€ in Mustangproject . I would say that's enough but I'm still contributing. Also owed to the fact that other people contributed. My total revenue until now is probably not even five digits. And these 650k€ do not even count how much time I invest in the (community work, e.g. the homepage and) governance, e.g. I wrote a validator, automated tests and I am currently sitting in a Strasbourgh Hotel because I'm attending a conference where AWVs CC3 and FNFE convene to decide on future factur-x versions and launch Deliver-X.

The fact that Factur-X is based on PDF/A and hardly any tool seems to be capable of exporting valid PDF/A is not really a core concern, e.g. LibreOffice does a very good export and I tried to describe on http://zugferd.org/ what incredibly good job Ghostscript did.

Making e-invoices more accessible: I'm trying my very best, I can't possibly make it more accessible, I'm practically on the verge of bankrupcy for it. We need everybody in the standard bodies (I can introduce you, I can show you around, actually we need three more XML guys in CC3 alone) and I need every contribution to Mustang and Mustangserver. So: May I politely inquire if you plan to contribute? 

## GoBD


Grundsätze zur ordnungsmäßigen Führung und Aufbewahrung von Büchern, Aufzeichnungen und Unterlagen in elektronischer Form sowie zum Datenzugriff

https://ao.bundesfinanzministerium.de/ao/2021/Anhaenge/BMF-Schreiben-und-gleichlautende-Laendererlasse/Anhang-64/anhang-64.html

Muster-Verfahrensdokumentation zum ersetzenden Scannen https://www.bstbk.de/downloads/bstbk/steuerrecht-und-rechnungslegung/fachinfos/BStBK_Muster-VerfD-ersetzendes-Scannen_v2.0-2019-11-29.pdf

Muster-Verfahrensdokumentation für Belegablage https://www.awv-net.de/upload/pdf/Belegablage_V1_20151026.pdf nachschiebe

## Name

Nach Order-X und nach Beginn aber vor Abschluss der Arbeiten (an Lieferscheinen, genannt
Deliver-X) wurde ZUGFeRD zur Formatfamilie: Der Begriff wechselte in den Plural,
Zentrale User Guides Forum elektronische Rechnung Deutschland, die Abkürzung blieb
(vgl https://www.ferd-net.de/aktuelles/meldungen/rueckblick-auf-die-sitzung-des-ferd-plenums.html).
Aus historischen deutschfranzösischen Freundschaftsgründen
noch Version 1 genannt, ist Factur-X Version 1 jetzt streng genommen das e-Rechnungsformat von ZUGFeRD Version 2.

## Codelisten

https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Registry+of+supporting+artefacts+to+implement+EN16931



## Was ist der Unterschied zwischen Factur-X und ZUGFeRD
Factur-X 1.0.50 ist der französische und internationale Name von ZUGFeRD 2.1. Der Factur-X-Dateiname (factur-x.xml) und Metadaten (RDF-Metadaten mit dem Namespace Prefix „fx“) sind seit ZUGFeRD 2.1 bevorzugt.

## Ist meine Berechnungsmethode korrekt? 
Die Berechnung von elektronischen Rechnungen ist im Rahmen von EN16931-1 normiert, das kostenlos online bezogen werden kann, in Deutschland im Shop der DIN angegliederten Beuth Verlags.

## Welche Attributwerte kann ich verwenden?
Die entsprechenden Codelisten werden vom CEF verwaltet und veröffentlicht. Sie sind Teil des ZUGFeRD Infopakets.
Gibt es kostenlose Tools?
Unter http://zugferd.org/ gibt es eine Liste von Open-Source-Tools die direkt oder indirekt mit ZUGFeRD zu tun haben. 

## Kann ich alle PDF-Dateien für ZUGFeRD verwenden?
ZUGFeRD basiert auf archivierbaren (PDF/A) PDFs, die alle zur Darstellung benötigten Daten wie Schriftarten einbetten. Eine kostenlose Möglichkeit „normale“ PDF-Dateien zu konvertieren stellt beispielsweise Ghostscript dar. 

## Wie sieht eine ZUGFeRD-Datei aus
Abgesehen von der Identifikation in den Metadaten ist beispielsweise im Adobe Reader ist eine ZUGFeRD-Datei durch Hinweis auf PDF-A und das Büroklammersymbol mit der eingebetten Datei zugferd-invoice.xml oder factur-x.xml ersichtlich. 



## Common issues when writing
* paper-invisible attributes like VAT exemption reason codes
* Decimals
* Schema+Schematron
* Fixed Namespace Prefixes
* Codelists, formal and semantic
* STK=Stück? → Quba-viewer.org
* Why 1..n tax currency?
* Gross price definition correct?
* HATE test: Have your EN16931-1 handy
* Check totals


## Common issues when reading

* Filename can be 
  * zugferd-invoice.xml, 
  * xrechnung.xml, 
  * ZUGFeRD-invoice.xml,
  * cida.xml (Deliver-X prerelease),
  * order-x.xml or 
  * factur-x.xml (default)
* PDF
  * embedded files may have „alias“ filenames
  * can be embedded using „flat“ or „tree“ method
  * PDF parts can be compressed
  * PDF/A-4?
* XML
  * may contain UTF8-BOM
  * Venetian blinds design pattern
  * Attached files may be attached as additional PDF embedded file, or, 
in case of XRechnung, base64 encoded within the XML



