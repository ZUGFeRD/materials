# ZUGFeRD/Factur-X/Order-X/Deliver-X Knowledge base

## Namespace prefixes

rsm:, ram:, qdt: and udt are mandatory:
https://www.zugferd-community.net/de/infothek/technical_xml_regarding_fixed_namespace_prefixes_rsm_ram_

## Format vs Protokoll, EDI
Ich würde grob zwischen Format und Protokoll unterscheiden, das Format definiert die Bedeutung (Beispiel deutsche Sprache) und das Protokoll die Adressierung, Abfolge und Übertragung (Beispiel Telefon: Erst klingelts, dann abnehmen). Beides zusammen ist EDI und ja, da sind erste internationale Standards in Deutschland ab 1977 im Einsatz. Es ist nur superkomplex, allein weil jede Firma in jedem EDI eine andere Adresse hat - und nicht jede Firma hat EDI im Einsatz, geschweige denn jedes EDI.

Insofern ist die Frage nach dem Format aus der CII oder UBL herausgegangen sind die Frage nach dem was wäre denn der kleinste gemeinsame Nenner aus dem wir maschinenlesbar das rausholen können was wir brauchen.

Peppol ist UBL als Format und AS/4 als Protokoll, by the way. AS/4 ist dabei angeblich https-ähnlich.

## Frankreich

Frankreich stellt OpenApi-Beschreibungen zur Verfügung (vgl https://communaute.chorus-pro.gouv.fr/wp-content/uploads/2020/04/External_Specifications_API_Appendix_V5.00.pdf verweist auf das API Management der Franzose, https://developer.aife.economie.gouv.fr/, da kann man sich auch mit einer deutschen USt ID anmelden und OpenAPI-Dateien für deren Schnittstelle ziehen), in Deutschland gab es aber nur für B2G eine konventionelle menschenlesbare Spezifikation für ein REST API das mittlerweile abgeschaltet ist und es wird wohl keins für B2B geben.

## USt Meldesystem

Nach der Empfangspflicht und nach der Sendepflicht soll das Umsatzsteuermeldesystem in einem dritten Schritt eingeführt werden. Da wirds dann spannend, das wäre eine Schnittstelle bei der OpenAPI oder WSDL total Sinn macht, ich meine aber irgendwo meine ich gelesen zu haben, dass man die XML-Pflicht schonmal haben wollen würde gerade weil es beim Umsatzsteuermeldesystem gerade nicht so schnell vorangeht. Und das wird dann wesentlich später entschieden und veröffentlicht.
ViDA (EU) Pläne: https://ec.europa.eu/commission/presscorner/detail/en/ip_22_7514

Folgende Typen: Kollmann https://www.pagero.com/downloads/documents/compliance/Next_Generation_Model-Decentralised_CTC_and_Exchange_v1.pdf 

## Report issues

 https://github.com/ConnectingEurope/eInvoicing-EN16931/issues 



about validation artefacts, versioning and general considerations


https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Validations


about release dates and how to comment / create an issue
https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Registry+of+supporting+artefacts+to+implement+EN16931#RegistryofsupportingartefactstoimplementEN16931-Regularreleaseschedule



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



## Bruttopreise

Was mit UBL/CII/EN16931 beispielsweise nicht geht ist die Bruttorechnungsthematik, gewisse "Regalpreise" wie 9,99€ brutto bei 19% bekommt man beispielsweise gar nicht EN16931-konform berechnet: 8,39€ netto wären 9,98€ Zahlbetrag, 8,40€ sind hingegen schon 10€.

## Kassenbons

Zu gesetzlichen Verpflichtungen: es gibt zwar seit 30.07.2021 die § 6 Satz 2 KassenSichV, i.e. die QR-Code-Norm https://www.bzst.de/SharedDocs/Downloads/DE/Aussenpruefung/dsfinv_k_v_2_4.zip?__blob=publicationFile&v=7 , aber ein Bon ist eine Kleinbetragsrechnung und was da spezifiziert wird hält sich an keinen internationalen Standard. Da bin ich und viele meiner Kollegen einfach raus,  elektronische Rechnungen bspw. i.S.v. EN16931 berücksichtigen nur "richtige" Rechnungen (in Deutschland ab 250€, mit Pflichtangaben wie Name und Anschrift des Kunden). Anonym ist der QR-Code übrigens auch nicht, weil u.a. genau das Protokoll der Kartenzahlung, sofern erfolgt, mitgeliefert werden muss. 

## Common issues when writing
* paper-invisible attributes like VAT exemption reason codes
* Decimals and rounding. And, please, use arbitrary precision
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
    * Please, use arbitrary precision
    * Attached files may be attached as additional PDF embedded file, or,
      in case of XRechnung, base64 encoded within the XML



