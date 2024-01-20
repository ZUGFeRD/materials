# Syllabus

This is the attempt to collect e-procurement/ZUGFeRD/XRechnung/Factur-X related training
topics and texts under a free license (public domain).

Currently we're collecting topics and why they may be important.
Fundamentally it's a german view but it can be extended to other countries.

Until we have conducted more trainings and can better specify the content and time needed for each chapter we will
put A-C if it's a small, medium or large topic.

An example of a good syllabus is the [ITSQB syllabus](https://istqb-main-web-prod.s3.amazonaws.com/media/documents/ISTQB_CTFL_Syllabus-v4.0.pdf)
and we might later use their learning levels   

* K1: Remember
* K2: Understand
* K3: Apply

Attributes: Dependencies, how long, how important, how interactive,
how known, how autonomous, how popular


* [Legal and compliance](#__refheading___toc9517_339098550)
  * [GoBD](#__refheading___toc9531_339098550)
    * [Auditing requirements](#__refheading___toc9533_339098550)
    * [Invoice retention](#__refheading___toc9535_339098550)
    * [Procedural documentation](#__refheading___toc9537_339098550)
  * [VAT regulations](#__refheading___toc9539_339098550)
  * [EU/2014/55](#__refheading___toc9541_339098550)
  * [EN16931](#__refheading___toc9543_339098550)
  * [E-Government-Gesetz](#__refheading___toc9545_339098550)
  * [E-Rechnungs-VO](#__refheading___toc9547_339098550)
  * [E-invoices international](#__refheading___toc9549_339098550)
  * [Gross price definition](#__refheading___toc9551_339098550)
  * [Substitutional scans](#__refheading___toc9553_339098550)
  * [Invoice Recognition and ZUGFeRD](#__refheading___toc9555_339098550)
  * [Paper-hidden requirements](#__refheading___toc9557_3390985501)
  <!--Some XML requirements, like VAT type codes, are now required and were never displayed on any paper invoice.-->
  * [Reminders](#__refheading___toc9557_33909855012)


<!--How to remind your customers to pay an invoice, with and without fee-->

* [B2B: ](#__refheading___toc3262_265032451)[Continuous Transaction Control](#__refheading___toc3262_265032451)[s](#__refheading___toc3262_265032451)[	4](#__refheading___toc3262_265032451)

  * [History and generic info](#__refheading___toc9559_339098550)

    * [EDI, EDIFACT and APERAK](#__refheading___toc9561_339098550)

    * [APERAK](#__refheading___toc9563_339098550)

    * [unstructured vs structured invoices](#__refheading___toc9565_339098550)

    * [UN/CEFACT vs UBL](#__refheading___toc9567_339098550)

    * [ZUGFeRD v1](#__refheading___toc9569_339098550)

    * [ZUGFeRD v2](#__refheading___toc9571_339098550)

    * [Factur-X](#__refheading___toc9573_339098550)

    * [Order-X](#__refheading___toc9575_339098550)

    * [Deliver-X](#__refheading___toc9577_339098550)

    * [unit codes and other codelists](#__refheading___toc9579_339098550)

    * [XRechnung](#__refheading___toc9581_339098550)

    * [Invoice attachments](#__refheading___toc9583_339098550)

    * [CIUS vs additional data](#__refheading___toc9585_339098550)

    * [Industry recommendations](#__refheading___toc9587_339098550)

    * [PEPPOL](#__refheading___toc9589_339098550)

    * [E-invoicing vs e-Billing](#__refheading___toc9591_339098550)

    * [Document types](#__refheading___toc9593_339098550)

* [Tools](#__refheading___toc9519_339098550)

  * [SDKs](#__refheading___toc9595_339098550)

  * [Open Source tools](#__refheading___toc9597_339098550)

  * [Libraries](#__refheading___toc9599_339098550)

  * [Software stack/Creation tools](#__refheading___toc9601_339098550)

  * [Consuming applications](#__refheading___toc9603_339098550)

  * [Validators](#__refheading___toc9605_339098550)

  * [Miscellaneous tools](#__refheading___toc9607_339098550)

* [XML](#__refheading___toc9521_339098550)

  * [Basics](#__refheading___toc9609_339098550)

    * [Well-formedness](#__refheading___toc9611_339098550)

    * [Schema](#__refheading___toc9613_339098550)

    * [UTF8](#__refheading___toc9615_339098550)

    * [Namespaces](#__refheading___toc9617_339098550)

    * [UN/CEFACT CII, CIO and CIDA](#__refheading___toc9619_339098550)

    * [UBL](#__refheading___toc9621_339098550)

    * [Xpath](#__refheading___toc9623_339098550)

    * [Evaluation](#__refheading___toc9625_339098550)

    * [Validators](#__refheading___toc9627_339098550)

    * [XSLT](#__refheading___toc9629_339098550)

    * [Saxon](#__refheading___toc9631_339098550)

    * [Apache FOP](#__refheading___toc9633_339098550)

    * [Schematron](#__refheading___toc9635_339098550)

    * [Validate using XSLT](#__refheading___toc9637_339098550)

    * [Codelists](#__refheading___toc9639_339098550)

* [PDF](#__refheading___toc9523_339098550)

    * [Basics](#__refheading___toc9641_339098550)
      * [Creation](#__refheading___toc9643_339098550)

      * [Structure analysis](#__refheading___toc9645_339098550)

      * [PDF-A](#__refheading___toc9647_339098550)

      * [Purpose, ISO Standard](#__refheading___toc9649_339098550)

      * [Validation, e.g. using VeraPDF](#__refheading___toc9651_339098550)

      * [File attachments, PDF/A Schema extensions and RDF Metadata](#__refheading___toc9653_339098550)

    * [Mustang](#__refheading___toc9525_339098550)

      * [Reading](#__refheading___toc9655_339098550)

      * [Writing](#__refheading___toc9657_339098550)

      * [Validation](#__refheading___toc9659_339098550)
      * [Conversion](#__refheading___toc9661_339098550)
      * [Visualization](#__refheading___toc9663_339098550)
    * [Quba](#__refheading___toc9665_339098550)
    * [Integration](#__refheading___toc9527_339098550)

##
## <a name="__refheading___toc9517_339098550"></a>**Legal and compliance**
The European legal situation for e-procurement, in particular in Germany for B2G invoices
### <a name="__refheading___toc9531_339098550"></a>**GoBD**
The european legal situation for e-orders and e-invoices, in particular in Germany for B2G invoices
### <a name="__refheading___toc9533_339098550"></a>**Auditing requirements**
The auditing requirements of the GoBD vis a vis tools to store e-invoices, their processes, their backups and their as well as their unalterability
### <a name="__refheading___toc9535_339098550"></a>**Invoice retention**
How long invoices have to be made available before their archival
### <a name="__refheading___toc9537_339098550"></a>**Procedural documentation**
The requirements of the GoBD as regards to procedural documentation e.g. of the decision if the XML or the PDF-part of an invoice be processed
### <a name="__refheading___toc9539_339098550"></a>**VAT regulations**
Why and how the legislation of identical copies (Inhaltsgleiche Mehrstücke) affected Factur-X/ZUGFeRD
### <a name="__refheading___toc9541_339098550"></a>**EU/2014/55**
Directive EU/2014/55 of the European Commision was the start of a unified requirement vis a vis all European member countries to be able to process electronic invoices
### <a name="__refheading___toc9543_339098550"></a>**EN16931**
CEN EN16931-1 – EN16931-5 is the standard to aid EU/2014/55. We will have a look e.g. at the eligible syntaxes and the calculation rules.
### <a name="__refheading___toc9545_339098550"></a>**E-Government-Gesetz**
The german E-Government-Gesetz is the german ratification of EU/2014/55 and additionally to enforcing the authorities to accept e-invoices, it also prohibits most vendors to further send paper invoices
### <a name="__refheading___toc9547_339098550"></a>**E-Rechnungs-VO**
The E-Rechnungs-Verordnung aids the E-Government-Gesetz and e.g. established deadlines until when the migration has to take place.
### <a name="__refheading___toc9549_339098550"></a>**E-Rechnungen international**
We’ll have a look at special requirements of certain countries, e.g. digital signature (Hungary) or Rappenrundung (Switzerland)
### <a name="__refheading___toc9551_339098550"></a>**Gross price definition**
In germany, gross is often translated as Brutto, including VAT that conflicts with the definition in EN16931, CII and UBL where gross is more of a basic list price, without VAT
### <a name="__refheading___toc9553_339098550"></a>**Substitutional scans**
The GoBD imposes certain requirement on the processes and tools if paper invoices are to be destroyed after their scan.
### <a name="__refheading___toc9555_339098550"></a>**Invoice Recognition and ZUGFeRD**
We cover the topic if and how potentially incomplete OCRs can still build a valid Factur-X file and if profiles are upwards compatible.
### <a name="__refheading___toc9557_3390985501"></a>**Paper-hidden requirements**
### <a name="__refheading___toc9557_339098550"></a>Some XML requirements, like VAT type codes, are now required and were never displayed on any paper invoice.
### <a name="__refheading___toc9557_33909855012"></a>**Reminders**
### <a name="__refheading___toc9557_3390985502"></a>How to remind your customers to pay an invoice, with and without fee
### <a name="__refheading___toc3262_265032451"></a>**B2B: Continuous Transaction Controls**
FatturaPA, How Italy introduced B2B e-invoicing, how France introduces B2B-e-invoicing, CTC models, situation in Germany
1. ## <a name="__refheading___toc9559_339098550"></a>**History and generic info**
   How the standards have evolved and what are their purposes
### <a name="__refheading___toc9561_339098550"></a>**EDI, EDIFACT and APERAK**
Electronic Data Interchange, EDI, combines the meaning of a format with the addressing and exchange of a protocol. Despite being more complex, EDI is much older than XML based e-invoicing, and still in use today. The introduction of (international) e-invoicing standards in germany in fact dates back to the 1977 introduction of EDIFACT.
### <a name="__refheading___toc9563_339098550"></a>**APERAK**
The XML Application error and acknowledgement messages
can be used to signal acceptance or rejection of invoices
### <a name="__refheading___toc9565_339098550"></a>**unstructured vs structured invoices**
Unstructured invoices are human-readable (e.g. image files, TIFF, PDF even with OCR layer), structured invoices are machine readable (e.g. XML files). Unstructured invoices are generally easier to obtain, e.g. by scanning paper invoices, but they can not be processed automatically.
### <a name="__refheading___toc9567_339098550"></a>**UN/CEFACT vs UBL**
UBL was initiated by the UN/CEFACT but later replaced by it’s own standard. There are slight differences between OASIS UBL and UN/CEFACT, their extentability, their governance, and their institutions.
### <a name="__refheading___toc9569_339098550"></a>**ZUGFeRD v1**
In 2014 ZUGFeRD defined how to embed XML in PDF to get a hybrid invoice, both structured and unstructured at the same time. PDF/A was selected as the carrier, a customized UN/CEFACT CII/2013b for the data and three subsets („profiles“) were defined.
### <a name="__refheading___toc9571_339098550"></a>**ZUGFeRD v2**
ZUGFeRD version 2~=Factur-X version 1 switched UN/CEFACT CII from a customized 2013b to a unchanged 2016b version, introduced first two more profiles and renamed one. Later, in v2.1.1, the concept of reference profiles were conceived.
### <a name="__refheading___toc9573_339098550"></a>**Factur-X**
Factur-X 1 started as a french fork of ZUGFeRD 2 led by the FNFE. The „Factur-X namespace“ soon also became the recommended name(space?) for ZUGFeRD.
### <a name="__refheading___toc9575_339098550"></a>**Order-X**
Order-X is the sister standard to Factur-X, with in PDF embedded XML of orders instead of invoices. Process-wise it also supports proposal and acceptance of changes. For this purpose, UN/CEFACT CrossIndustryOrder 2020b is used, the embedded file is called Order-X.xml.
### <a name="__refheading___toc9577_339098550"></a>**Deliver-X**
GS1 and BVL were working on hybrid electronic despatch advices based on UN/CEFACT Cross Industry Despatch Advice, crossing the gap between orders and invoices, which will be the basis for the upcoming Deliver-X standard
### <a name="__refheading___toc9579_339098550"></a>**unit codes and other codelists**
The different lists of the different standards for eligible attribute values have been centralized by the CEF, who republish them as excel. They are binding for EN16931, i.e. not only CII but also UBL.
### <a name="__refheading___toc9581_339098550"></a>**XRechnung**
The XRechnung is the requirements specification of the german government vis a vis electronic invoices. XML-wise they are mapped to CII and UBL and it makes certain attributes mandatory, e.g. the postal address of the receiver and a seller contact as well as the governmental routing number „Leitweg-ID“. Due to political reasons cash discounts are handled using a proprietary format, not XML. This lesson clarifies Business Term IDs, how to find them (and their cardinalities) in ZUGFeRD’s technical appendix, which industry recommendation exists, what the difference is between the two XRechnung profiles, how to convert between the XML formats, how to validate XRechnung, how to visualize them and how they are mapped to Peppol-IDs to facilitate automatic transmission.
### <a name="__refheading___toc9583_339098550"></a>**Invoice attachments**
Invoice attachments like protocols, bills of material or measurements are added either as embedded file within the PDF (Factur.-X) or base64-encoded in the XRechnung.
### <a name="__refheading___toc9585_339098550"></a>**CIUS vs additional data**
Core Invoice Usage Specifications, CIUS, like the german XRechnung, can make optional attributes mandatory, Andreas Starke’s additional data can cater additional structured attributes for electronic invoices.
### <a name="__refheading___toc9587_339098550"></a>**Industry recommendations**
E.g. the Deutsche Bahn or the construction industry has published requirements vis á vis Xrechnung respective ZUGFeRD files, and the french Chorus Pro has published requirements both for french B2G as well as for french B2B invoices.
### <a name="__refheading___toc9589_339098550"></a>**PEPPOL**
PEPPOL is a international EDI organization, based on UBL messages and the AS/4 protocol, which implement a four-corner model for their paying customers.
### <a name="__refheading___toc9591_339098550"></a>**E-invoicing vs e-Billing**
E-Billing, in Germany for amounts <150 Eur, allow amounts with VAT which could otherwise not be expressed, e.g. 20,20 Eur @ 19%.
### <a name="__refheading___toc9593_339098550"></a>**Document types**
Apart from usual invoices, sometimes there might be need for reminders (not in scope), credit notes, or corrected invoices. Partial invoice are in scope, collective invoices (single invoice on multiple orders) only available in certain profiles.
## <a name="__refheading___toc9519_339098550"></a>**Tools**
### <a name="__refheading___toc9595_339098550"></a>**SDKs**
Open Source SDKs for C++, Java, Python and PHP are covered
### <a name="__refheading___toc9597_339098550"></a>**Open Source tools**
Open source tools for Metadata and schema validation
### <a name="__refheading___toc9599_339098550"></a>**Libraries**
Which free libraries can be used to make software e.g. Factur-X ready
### <a name="__refheading___toc9601_339098550"></a>**Software stack/Creation tools**
Free software and editors which perform e.g. schema validation for XML authoring
### <a name="__refheading___toc9603_339098550"></a>**Consuming applications**
Free open source private banking software and e-invoice viewers
### <a name="__refheading___toc9605_339098550"></a>**Validators**
Free software to re-calculate invoices and check their formal correctness
### <a name="__refheading___toc9607_339098550"></a>**Miscellaneous tools**
- E.g. text editors, hex editors and diff tools for XML authoring


## <a name="__refheading___toc9521_339098550"></a>**XML**
   XRechnung and Factur-X/ZUGFeRD consist of XML files, this convers XML’s validity, in general, tools to validate, address, mix and transform XML and gives an intro to the two most important XML formats for electronic invoices, UN/CEFACT Cross Industry Invoice (used for Factur-X/ZUGFeRD and XRechnung) and UBL (used for XRechnung and Peppol)


### <a name="__refheading___toc9609_339098550"></a>**Basics**
Basics for XML in general: Charsets and general validity
1. #### <a name="__refheading___toc9611_339098550"></a>***Well-formedness***
   Describes how XML is a hierarchical format and what all XML files must and must not have, as well as a authoring tool to ensure that
1. #### <a name="__refheading___toc9613_339098550"></a>***Schema***
   Schema files also allow to specify which format e.g. attributes should take, e.g. that the total amount has to consist of numbers with two decimals.
1. #### <a name="__refheading___toc9615_339098550"></a>***UTF8***
   Unicode is the most important international character encoding for XML, UTF8 is a 8 bit representation that comes with certain peculiarities, e.g. a possible Byte Order Mark
1. #### <a name="__refheading___toc9617_339098550"></a>***Namespaces***
   Namespaces are used to blend XML documents together
### <a name="__refheading___toc9619_339098550"></a>**UN/CEFACT CII, CIO and CIDA**
UN/CEFACT CII is a standard used for electronic invoices, the „MUG“ has been determined as it’s european subset. For orders, CIO can be used. The current version, schema file, the root, the basic elements and the basic namespaces are described.
### <a name="__refheading___toc9621_339098550"></a>**UBL**
- UBL is another XML invoice standard. Alternative XML structures and why they are deprecated are discussed (e.g. OpenTrans, FinInvoice). Here as well the current version, schema file, the root, the basic elements and the basic namespaces are described.



### <a name="__refheading___toc9623_339098550"></a>**Xpath**
Xpath is a standard used to find, address and aggregate XML elements and attributes. Apart from being useful to find invoice data, it plays an important role when transforming XML (with XSLT) and when validating XML (using schematron)
1. #### <a name="__refheading___toc9625_339098550"></a>***Evaluation***
   Simple Xpath queries and how to run them on a sample document
1. #### <a name="__refheading___toc9627_339098550"></a>***Validators***
   How and why Schematron uses Xpath to be able to specify tests/validations on XML files
### <a name="__refheading___toc9629_339098550"></a>**XSLT**
XSL transformations allow to transform any XML file in one format into anotther file in the same, or a different format
1. #### <a name="__refheading___toc9631_339098550"></a>***Saxon***
   Saxon is a powerful open source engine to apply XSLT
1. #### <a name="__refheading___toc9633_339098550"></a>***Apache FOP***
   Apache FOP can be used to generate PDF from a particular XML format, called „Formatting Objects“ (FO), so a XML file can be translated into PDF
### <a name="__refheading___toc9635_339098550"></a>**Schematron**
Schematron files use Xpath to be a much more powerful validation than mere Schema files can do, allowing e.g. mathematical operations like the total amount has to match the sum of the items. Which e-invoice related schematron files are published where is part of this lesson.
1. #### <a name="__refheading___toc9637_339098550"></a>***Validate using XSLT***
   Schematron rules can be converted to format specific XSLT files, in which case the XSLT transformation output is a XML validation report of the input file against the given Schematron rules. This lesson shows how this can be done to obtain validation reports.
### <a name="__refheading___toc9639_339098550"></a>**Codelists**
Codelists specify possible attribute values, e.g. „H87“ as unit code for „piece“. Which e-invoice related codelists are published where and which versions are relevant is part of this lesson.
1. ## <a name="__refheading___toc9523_339098550"></a>**PDF**
   PDF is the second pillar of hybrid invoices
### <a name="__refheading___toc9641_339098550"></a>**Basics**
Like XML, PDF is a hierarchical format, but with references, binary data and compression
### <a name="__refheading___toc9643_339098550"></a>**Creation**
Ghostscript is one of the very few free open source tools capable of converting PDF to PDF/A. It is often used in virtual PDF printing software and actually Ghostscript can read and process PDF files so well that it is occasionally used to fix even corrupted PDFs. Even Factur-X comliant PDF/A-3 can be created with Ghostscript.
### <a name="__refheading___toc9645_339098550"></a>**Structure analysis**
Open-Source tools like itext RUPS, Exiftool, or the structure view of the commercial Acrobat Pro highlight the internal hierachy or metadata within the PDF files.
### <a name="__refheading___toc9647_339098550"></a>**PDF-A**
This lesson will discuss the difference between PDF and it’s archival counterparts, PDF/A-1 to 4 and why it is important to at least use PDF/A-1
### <a name="__refheading___toc9649_339098550"></a>**Purpose, ISO Standard**
The knowledge of the aforementioned tools, along with the specifications (PDF is available, PDF/A costs money) can help to make files valid and more readable

### <a name="__refheading___toc9651_339098550"></a>**Validation, e.g. using VeraPDF**
VeraPDF is a open source Validator for PDF/A as the common PDF standard has evolved so much that validation is de facto no longer possible.
### <a name="__refheading___toc9653_339098550"></a>**File attachments, PDF/A Schema extensions and RDF Metadata**
Within PDF/A, file attachments are available since A-3, this lesson also has a look at the A-3 subset a, u and b, as well as PDF/A-4‘s „f“ subsubset.
## <a name="__refheading___toc9525_339098550"></a>**Mustang**
   How Mustang can be used and embedded
### <a name="__refheading___toc9655_339098550"></a>**Reading**
How to use the command line tool to extract XML from Factur-X/ZUGFeRD
### <a name="__refheading___toc9657_339098550"></a>**Writing**
Use the command line tool to combine XML and PDF to Factur-X/ZUGFeRD and Order-X
### <a name="__refheading___toc9659_339098550"></a>**Validation**
Validation with the command line tool, meaning of the error types. How to follow up on rounding errors.
### <a name="__refheading___toc9661_339098550"></a>**Conversion**
How the commandline can be used to convert ZUGFeRD from v1 to v2, from CII to UBL and (for the purpose of visualization) from CII to HTML. How Mustang can be used in automated tests.
### <a name="__refheading___toc9663_339098550"></a>**Visualization**

### <a name="__refheading___toc9665_339098550"></a>**Quba**
### <a name="__refheading___toc9527_339098550"></a>**Integration**
How to embed the Mustang Library and the Mustang validator in Java software. How to facilitate checks (and tests, e.g. the HATE test) if the calculation match. How XRechnung can be extracted from the invoice class and how invoices can be parsed either coarse or fine.

Exercises could include 
* Use Mustang to extract, combine, convert to HTML or UBL and/or validate
* Use Kosit to validate XRechnung
* Use Kosit to display HTML, PDF
* How to apply schematron the XSLT way
* How to identify a rounding error in the schematron
* correction of various invalid XML invoices
* correction of invalid PDF invoices
* Xpath authoring
* Assign Which BT is which attribute
* What is the correct unit code?
* How to calculate correctly: The HATE test, gross prices
* How to find my cardinality?
* May I use this element?
* Getting aquainted with rounding errors in official schematrons
