# FRBRoo - eine Anwendung

Veröffentlicht am 15. Februar 2013 von Hans-Georg Becker	

![The LODLAM Mercury von Hans-Georg Becker steht unter einer Creative Commons Namensnennung 4.0 Unported Lizenz.](../../../cc_by_88x31.png)\
The LODLAM Mercury von Hans-Georg Becker steht unter einer Creative Commons Namensnennung 4.0 Unported Lizenz.

***

In den letzten Jahren habe ich mich im Rahmen des von der DFG geförderten Projektes ["ArcheoInf - Informationszentrum für die Archäologie](https://www.ub.tu-dortmund.de/archeoinf/) mit dem CIDOC CRM und der zugehörigen Erweiterung FRBRoo beschäftigt.

Ziel des Projektes war es, "Primärdaten archäologischer Forschung, die bisher in heterogenen Datenstrukturen vorgehalten wurden, unter Wahrung ihrer Autonomie in einer gemeinsamen Umgebung web-basiert verfügbar" zu machen. Mit den archäologischen Primärdaten sollten bibliothekarische Informationen und Dienstleistungen sowie geoinformatisches Datenmaterial verbunden werden.

Aufgrund der als "Best Practice" einzuordnenden Erfahrungen aus den britischen Strukturen zur Erhaltung des kulturellen Erbes (z.B. English Heritage, British Museum), war uns sehr früh bewusst, dass ein System wie ArcheoInf nur auf Basis des CIDOC CRM gelingen kann.

**Was ist das CIDOC CRM?**

Beim [CIDOC Conceptual Reference Model](http://www.cidoc-crm.org/) handelt es sich um eine Norm (ISO 21127:2006) für den kontrollierten Austausch von Informationen im Bereich des kulturellen Erbes. Die Ontologie soll unter anderem von Archiven, Bibliotheken und Museen zur Verbesserung der Verfügbarkeit von Wissen angewandt werden. Es wurde vom CIDOC, einem der 30 internationalen Komitees des International Council of Museums (Internationalen Museumsrats, ICOM) entwickelt.

Mit dem CIDOC CRM wird das Ziel verfolgt, die vielfältigen Informationen im Bereich des kulturellen Erbes gemeinsam zu erfassen und einen allgemeinen Rahmen ihrer formalen Semantik zur Verfügung zu stellen, damit jede Information dieses Bereichs den Begriffen des CIDOC CRM zugeordnet wer-den kann. Auf diese Weise werden wichtige Voraussetzungen für die Informationsintegration geschaffen, da auf der Grundlage des CIDOC CRM Werkzeuge zur Schematransformation und -integration entwickelt werden können.

Das CRM beruht auf zwei Hierarchien von Entitäten und Eigenschaften und erlaubt ein hohes Maß an semantischer Präzision. Es eignet sich daher als eine Art Zwischenformat, dessen Verwendung die Anzahl der notwendigen Mappings dramatisch reduziert, wenn verschiedene Quellformate und mehrere Zielsprachen benötigt werden. Die wichtigste Eigenschaft des CIDOC CRM ist allerdings die Ereigniszentriertheit, d.h. es wird davon ausgegangen, dass jedes Objekt nur dann existiert, wenn vorher ein Ereignis stattgefunden hat, welches das Objekt zum Resultat hat.

**Aber es fehlen Strukturen für bibliographische Daten!**

Das CRM erlaubt Mappings beliebiger Datenmodelle. Für einige der im Bereich des kulturellen Erbes einschlägigen Modelle liegen generische Mappings vor, die von den Entwicklern des CRM veröffentlicht wurden. Die im Rahmen des CRM-Entwicklungsprojekts entworfenen Mappings für Dublin Core (DC), Encoded Archival Description (EAD), Lightweight Information Describing Objects (LIDO) und anderer Modelle und Formate orientieren sich an den im CRM-Entwicklungsprozess ausgearbeiteten [Empfehlungen](http://www.cidoc-crm.org/crm_mappings.html). <mark>Link defekt</mark>

[FRBRoo](http://www.cidoc-crm.org/frbr_inro.html) <mark>Link defekt</mark> ist die objektorientierte Version der FRBR (siehe auch [Tillet: What is FRBR?](http://www.loc.gov/cds/downloads/FRBR.PDF) und [Wiesenmüller: Zehn Jahre ‘Functional Requirements for Bibliographic Records’](http://www.b2i.de/fileadmin/dokumente/BFP_Bestand_2008/Jg_32-Nr_3/Jg_32-Nr_3_Aufsaetze/Jg_32-2008-Nr_3-S_348-359.pdf) <mark>Link defekt</mark>) und ermöglicht die gemeinsame Darstellung von Bibliotheks- und Museumsdokumentation. Damit ist es möglich, interoperable Informationssysteme für alle Nutzerinnen und Nutzer zu implementieren, die ein Interesse daran haben, auf gemeinsame oder verwandte Inhalte kultureller Einrichtungen zuzugreifen.

Mit der Entwicklung der FRBRoo ging eine gegenseitige Anreicherung der FRBR und des CIDOC CRM einher:

* Ergänzung der FRBR um Zeit und Ereignisse,
* begriffliche Abklärung der Entität Manifestation,
* explizite Modellierung von Aufführungen und Aufzeichnungen, die in den FRBR erwähnt sind,
* Ergänzung des CRM durch die Entität Werk und
* Ergänzung des CRM durch einen Identifikator-Vergabeprozess.

FRBRoo fügt damit den FRBR die dynamischen Aspekte des CRM hinzu. Ferner erlaubt es, aufgrund der netzartigen Struktur des CRM, bibliographische Informationen in Linked Data Kontexte zu übertragen.

**FRBR, Serials und die fehelende Manifestation**

Spätestens mit der Frage nach "FRBR and Serials" innerhalb des [lobid.org-Projektes des hbz](https://wiki1.hbz-nrw.de/display/SEM/2011/10/17/Serials+and+FRBR), habe ich mich entschlossen, mehr über meine Ergebnisse zum CRM und zu FRBRoo zu berichten.

In den nächsten Beiträgen dieses Blogs werde ich auf Basis der Publikationsformen nach dem bibliothekarischen Standardwerk "Bibliothekarisches Grundwissen" die Sichtweise der FRBRoo darstellen und zeigen, dass die Fragestellungen bzgl. der "Serials" sich damit beantworten lassen.

Weiterlesen: [FRBRoo — Eine prozessorientierte Sicht auf bibliographische Informationen](2013/02/16/frbroo-eine-prozessorientierte-sicht-auf-bibliographische-informationen.md)
