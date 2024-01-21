# ZUGFeRD/Factur-X/Order-X/Deliver-X Knowledge base

## Namespace prefixes

rsm:, ram:, qdt: and udt are mandatory:
https://www.zugferd-community.net/de/infothek/technical_xml_regarding_fixed_namespace_prefixes_rsm_ram_

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



