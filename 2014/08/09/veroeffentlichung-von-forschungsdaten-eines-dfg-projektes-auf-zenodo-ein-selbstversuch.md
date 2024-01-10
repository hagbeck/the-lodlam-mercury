# Veröffentlichung von Forschungsdaten eines DFG-Projektes auf Zenodo – Ein Selbstversuch

Posted on 9. August 2014 by Hans-Georg Becker	

Jede wissenschaftliche Einrichtung stellt – in der Regel basierend auf Empfehlungen von Drittmittelgebern wie der DFG – an sich den Anspruch, nach den Regeln guter wissenschaftlicher Praxis zu arbeiten. Hierzu heißt es beispielweise in den [Regeln für die TU Dortmund](https://www.tu-dortmund.de/uni/Uni/Organisation/Kommission_gute_wissenschaftliche_Praxis/Regeln_guter_wissenschaftlicher_Praxis_der_TUDO_17_06_09.pdf):

>    Hierzu gehört es, lege artis zu arbeiten, korrekte Angaben zu machen, geistiges Eigentum anderer zu achten sowie andere in ihrer Forschungstätigkeit nicht zu beeinträchtigen. […]\
>    Im Zusammenhang der Veröffentlichung schließt dies insbesondere Folgendes ein:
>    * Die nachvollziehbare Beschreibung der angewandten Methoden,
>    * die vollständige Dokumentation aller im Forschungsprozess erhobenen und für die Veröffentlichung relevanten Daten,
>    * eine nachprüfbare Darstellung der Forschungsergebnisse […]

Was bedeuten diese Forderungen nun für ein Projekt?

Die TU Dortmund hat bereits seit mehr als 15 Jahren ein Repositorium auf dem neben Hochschulschriften auch Projektberichte und andere Berichtsformen im Sinne des Open Access veröffentlicht werden können. Die fortschreitende Digitalisierung der Wissenschaftsdisziplinen erfordert aber heute weit mehr als “nur” die Archivierung textueller Daten. Zunehmend werden auch die zur Publikation führenden sogenannten Primär- oder Rohdaten digital erzeugt bzw. erfasst. Diese zu erschließen und zu archivieren ist eine nicht triviale Herausforderung.

In den letzten Jahren wurden weltweit Projekte begonnen, die sich zum Ziel genommen haben, eine Infrastruktur für Forschungsdaten aufzubauen. Während einige Forschungsgebiete eigene Data Center oder Data Journals (z.B. [Pangaea](https://www.pangaea.de/) oder [F1000 Research](https://f1000research.com/)) gegründet haben, sind kleinere Forschungsbereiche eher auf der Strecke geblieben. Diese Lücke möchten nun Plattformen wie [Zenodo](https://zenodo.org/), [Dryad Digital Repository](https://datadryad.org/) oder [figshare](https://figshare.com/) schließen. Aber auch immer mehr Zeitschriftenverlage bieten die Möglichkeit der Datenablage an.[^1]

[^1]: Hier ist aber Vorsicht geboten, da die Verlage teilweise fragwürdige Nutzungslizenzen vereinbaren wollen.

Für einen Teil der Ergebnisse des DFG-Projekts ArcheoInf, an dem die Universitäsbibliothek Dortmund beteiligt war, habe ich die Plattform Zenodo getestet und die Datensätze sowie die im Projekt entstandene Software dort archiviert.

![ArcheoInf-Logo](https://data.ub.tu-dortmund.de/archeoinf/images/archeoinf-logo.png)

Das [Projekt ArcheoInf](https://data.ub.tu-dortmund.de/archeoinf/) und das zu archivierende Material der beteiligten Bibliotheken
Zum Projekt ArcheoInf wurde bereits an einigen Stellen publiziert.[^2] Deshalb soll hier nur kurz über das Projekt selber berichtet werden.

[^2]: vgl. u.a. Open Data und Linked Data in einem Informationssystem für die Archäologie / Maike Lins, Hans-Georg Becker. In: (Open) Linked Data in Bibliotheken / hrsg. von Patrick Danowski, Adrian Pohl. De Gruyter Saur, 2013. – S. 201-223. DOI: [10.1515/9783110278736.201](https://doi.org/10.1515/9783110278736.201)

Das Projekt wurde im Rahmen des Programms “Themenorientierte Informationsnetze” seit dem Jahr 2008 von der Deutschen Forschungsgemeinschaft gefördert. Neben dem Archäologischen Institut der Georg-August-Universität Göttingen, dem Lehrstuhl für Software-Technologie der Technischen Universität Dortmund sowie dem Fachbereich Geoinformatik/Geodäsie der Hochschule Bochum arbeiteten die Universitätsbibliotheken Dortmund und Bochum in diesem Projekt an der Entwicklung eines Informationssystems für die Archäologie.

ArcheoInf zielte auf eine Verfügbarmachung wissenschaftlicher Forschungsdaten – also Karten, Bilder, Texte, schlicht alle zu den beteiligten archäologischen Grabungs- und Surveyprojekten verfügbaren Informationen – im Netz über eine einzige Oberfläche und von jedem Ort der Welt erreichbar. Es sollten hier nicht die Projekte isoliert durchsuchbar sein, sondern in einer Weise miteinander verknüpft werden, dass projektübergreifend Informationen zu einem gesuchten Thema gefunden und verbunden werden können.

Trotz des von Fachwissenschaftlern artikulierten Bedarfs einer derartigen Lösung, hat sich während der Projektlaufzeit gezeigt, dass die Freigabe von Projektdaten zur Bereitstellung über ein solches Portal aus verschiedenen Gründen häufig nicht zu erreichen ist. Insbesondere wurde deutlich, dass den Fachwissenschaftlern zunächst an Werkzeugen gelegen ist, die eine qualitativ hochwertige Verarbeitung von Primärdaten ermöglicht und diese somit erst publizierbar werden.

Das Resultat war, dass ArcheoInf kein Datenmaterial zur Verfügung stand und steht, mit dem einerseits die zu entwickelnden Instrumente ausgebaut werden konnten und andererseits eine oben beschriebene Plattform mit Inhalt gefüllt werden konnte. Dies gilt in besonders hohem Maße für archäologische Forschungsdaten, aber auch für die mit diesen verknüpften bibliographischen Daten.

Trotz dieser Schwierigkeiten ist es dem Projektteam gelungen, Werkzeuge, Programme und Datenmaterial zu entwickeln, um ein prototypisches Informationssystem zu erstellen.

Die am Projekt beteiligten Bibliotheken hatten unter anderem die Aufgabe, ein Dokumentenrepositorium – insbesondere für graue Literatur – mindestens aber eine Bibliographie der in den auf der ArchoInf-Plattform bereitgestellten Projekte zur Verfügung zu stellen. Dabei wurde schon sehr früh entschieden, dass als gemeinsamer Nenner das bibliographische Datenformat MODS dienen soll. Ferner wurden die Daten einerseits für die Indexierung in einer auf Apache Solr basierenden Suchmaschine und andererseits mittels der CIDOC CRM-Ontologien für die Verwendung als Linked Data aufbereitet.

![Zenodo-Logo](https://zenodo.org/static/images/invenio-rdm.svg)

**Zenodo – An open digital repository for everyone and everything that isn’t served by a dedicated service**\
[OpenAIRE](https://www.openaire.eu/) und [CERN](https://home.web.cern.ch/) haben dieses Repositorium im Jahr 2013 gestartet. Das von der Europäischen Kommission unterstützte Repositorium bietet einen zentralen Ort für die Speicherung und Recherche von Forschungsdaten und dient zusätzlich als Orphan Repository für Publikationen, für die kein passendes institutionelles oder disziplinäres Repositorium zur Verfügung steht.

Auf der [Webseite von Zenodo](https://zenodo.org/) wird die Plattform wie folgt beschrieben:

>    Zenodo is an open dependable home for the long-tail of science, enabling researchers to share and preserve any research outputs in any size, any format and from any science. 

Damit eignet sich die Plattform vor allem für die Archivierung von Materialien institutsübergreifender und kleinerer Projekte.

Zu den Funktionen gehören:

*    Community Collections inkl. OAI-PMH-Schnittstelle
*    Vergabe von bzw. Nachnutzung bereits vorhandener DOIs
*    flexible Lizensierung der Daten
*    Archivierung von GitHub-Software-Repositorien
*    Reporting zu Drittmittelgebern (derzeit nur EU-Projekte via OpenAIRE)

Zenodo speichert die beim Upload angegebenen Metadaten intern im MARC-Format ab, welches als [ZENODO Metadata Schema](https://invenio-software.org/wiki/Project/OpenAIREplus/DevelopmentRecordMarkup) dokumentiert ist. Als Exportformate stehen MARCXML, Dublin Core und DataCite Metadata Schema gemäß der OpenAIRE Guidelines zur Verfügung. Fachliche Metadaten (z.B. [DDI Metadata zur Beschreibung von sozial- und wirtschaftswissenschaftlichen Daten](https://www.ddialliance.org/)) werden nicht erfasst.

Die Metadaten sind bis auf die E-Mail-Adressen unter der CC0-Lizenz veröffentlicht und können über OAI-PMH abgerufen werden (vgl. auch die [Policy von Zenodo](https://zenodo.org/policies)).

# ArcheoInf auf Zenodo

Die Möglichkeit, eine Community Collection – also für eine spezielle Gruppe oder ein Projekt ein eigenes Repositorium – aufzusetzen, machte für ArcheoInf ohne Zweifel Sinn. So habe ich die [Community Collection “ArcheoInf Projekt”](https://zenodo.org/collection/user-archeoinf) angelegt, um dort die zum Projekt gehörigen Daten abzulegen.

Wie bereits oben beschreiben, haben die am Projekt beteiligten Bibliotheken vor allem bibliographische Datensätze für zwei Anwendungsszenarien aufbereitet. Auf Zenodo habe ich für jede “Projektbibliographie” ein Datenpaket bestehend aus den angereicherten MODS-Daten, den für die Indexierung in Apache Solr erzeugten und den Linked Data als RDF/XML abgelegt.

Die Datensätze haben durch die Ablage auf Zenodo einen DOI bekommen. Somit sind die Daten nun wie folgt publiziert:

*    Datensätze zur Bibliographie der phönizisch-punischen Archäologie: [10.5281/zenodo.10248](https://doi.org/10.5281/zenodo.10248)
*    Datensätze zur Bibliographie eines Gela-Surveys: [10.5281/zenodo.10249](https://doi.org/10.5281/zenodo.10249)
*    Datensätze aus der British National Bibliography: [10.5281/zenodo.10250](https://doi.org/10.5281/zenodo.10250)
*    Datensätze aus dem Katalog der Universitäts- und Stadtbibliothek Köln: [10.5281/zenodo.10251](https://doi.org/10.5281/zenodo.10251)
*    Bibliographische Datensätze zu Artikeln mit archäologischem Bezug: [10.5281/zenodo.10263](https://doi.org/10.5281/zenodo.10263)

Die Beschreibung der Datensätze sieht die Möglichkeit vor, Verknüpfungen zu anderen Publikationen zu erstellen. Beispielsweise ist es möglich, Datensätze als Supplement zu einer textuellen Publikation in Beziehung zu setzen. Von dieser Möglichkeit habe ich bei den fünf Datensätzen gebrauch gemacht, in dem ich sie als Supplements zu den beiden Publikationen von Maike Lins und mir im Sammelwerk “(Open) Linked Data in Bibliotheken” zugeordnet habe. Insbesondere in dem Beitrag “Open Data und Linked Data in einem Informationssystem für die Archäologie” wird auf die Erzeugung dieser Daten eingegangen und das Verfahren sowie die Verwendung der Daten beschrieben.

Die im Rahmen des Projektes entstandene Software zur Erzeugung bzw. Konvertierung der bibliographischen Daten wurde in einem [Repositorium “ArcheoInf” auf GitHub](https://github.com/ArcheoInf) abgelegt. Zenodo bietet die Möglichkeit, die Releases aus dem GitHub-Repositorium automatisch als zip-Archiv zu archvieren und diesem ebenfalls einen DOI zu vergeben. Die finale Version der Software zur Erzeugung bzw. Konvertierung der bibliographischen Daten in ArcheoInf hat nun den DOI [10.5281/zenodo.11177](https://doi.org/10.5281/zenodo.11177).

## Fazit

Um die Grundsätze der guten wissenschatlichen Arbeit im Sinne der eigenen Einrichtung aber auch der Drittmittelgeber zu erfüllen, ist die Plattform Zenodo sehr gut geeignet – insbesondere wenn es keine fachbezogene oder institutionelle Alternative gibt. Ein wesentlicher Vorteil von Zenodo liegt in der abgesicherten dauerhaften Finanzierung durch EU-Mittel und dem Betrieb durch das mit großen Datenmengen erfahrene CERN. Auch die Vergabe von DOIs und der automatischen Meldung der Publikationen an Drittmittelgeber (bisher nur für EU-Projekte via OpenAIRE) sind für Aspekte wie Sichtbarkeit und Vereinfachung von Verwaltungsaufgaben von Vorteil.\
Ein Nachteil könnte sein, dass eine Beschreibung der Daten mittels fachspezifischer Metadaten fehlt. Allerdings ist fast davon auszugehen, dass es in einem Fachgebiet mit einem speziellen Metadatenschema auch ein Datenrepositorium exisitert (nach schlagen kann man dies im Verzeichnis [Registry of Research Data Repositories (re3data)](https://www.re3data.org/).

***

