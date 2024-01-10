# Bestandsnachweise mit einem CIDOC CRM-Application Profile

Posted on 10. August 2014 by Hans-Georg Becker	

Auf meinen Beitrag [Bestandsnachweise von Bibliotheken als Linked Data](../../../2013/11/22/bestandsnachweise-von-bibliotheken-als-linked-data.md) gab es einige Anmerkungen. Neben einigen Retweets wurde insbesondere die Komplexität des CRM angesprochen. Beispielhaft greife ich hier eine Reaktion von Karen Coyle ([@karencoyle](https://twitter.com/karencoyle)) in der Mailing-Liste der [Schema Bib Extend Community Group](https://www.w3.org/community/schemabibex/) heraus[^1]: 

> […] Although a friend and I were joking the other day that FRBRoo diagrams look frighteningly like a London Tube Map. […].

[^1]: Mail vom 22.11.2013 im Mailarchiv

Auch in vielen Gesprächen am Rande der SWIB13 zeigt sich, dass die Akzeptanz für die CIDOC CRM-Welt an der vermeintlichen Komplexität des Modells scheitert. Auf der SWIB13 zeigte sich aber auch, dass an einigen Stellen neue Ontologien entstehen, deren Inhalte auch schon im CIDOC CRM abgebildet sind.[^2]

[^2]: Ich meine hier nicht die zahlreichen “Application Profiles” sondern die tatsächlich neuen Ontologien.

Sicherlich sieht der Ansatz im CIDOC CRM recht komplex aus. Doch was bleibt letztlich davon übrig, wenn beispielsweise für eine wissenschaftliche Bibliothek die zugehörige Universität bzw. die Bibliothek selbst die administrativen Informationen der Einrichtung als Linked Open Data bereitstellt?

Meine bisherigen Betrachtungen zeigen die Mächtigkeit des Modells und die Zusammenhänge für bibliographische Informationen eher abstrakt. Ich werde mich daher nun mit der Frage auseinandersetzen, ob auf Basis des CIDOC CRM ein “Application Profile” definierbar ist, welches tatsächlich anwendbar ist. Im Sinne der Unterscheidung zwischen Referenz- und Anwednungsontologie[^3] sollte es möglich sein, ein “Application Profile” auf Basis des CRM zu definieren, welches im Retrieval durch das CIDOC CRM als Referenzontologie nutzbar wird.

[^3]: Zur Anwendung des CIDOC CRM als Referenzontologie bzw. Anwendungsontologie vergleiche auch Hohmann, Georg (2010): Die Anwendung des CIDOC CRM für die semantische Wissensrepräsentation in den Kulturwissenschaften. In: Ohly, Peter; Sieglerschmidt, Jörn (eds.): Wissensspeicher in digitalen Räumen. Nachhaltigkeit, Verfügbarkeit, semantische Interoperabilität. Proceedings der 11. Tagung der Deutschen Sektion der Internationalen Gesellschaft für Wissensorganisation Konstanz 20.-22. Februar 2008. Würzburg: Ergon. pp. 210-222.

Im folgenden entwickelt sich eine Beschreibung der Bestandsnachweise, bei der die Komplexität des auf dem CIDOC CRM basierenden Modells durch eine “Aufgabenteilung” deutlich abnimmt.

## “Man-Made Features” und “Sites”

Wie im Beitrag über die Bestandsnachweise beschrieben, lässt sich mittels der CRM-Entität `E27_Site`[^4], `E26_Physical_Feature`[^5] und `E25_Man-Made_Feature`[^6] eine beliebige Örtlichkeit beschreiben.\
Die folgenden Beispiele zeigen einige Datensätze für die TU Dortmund.

[^4]: CRM: “This class comprises pieces of land or sea floor.”

[^5]: CRM: “This class comprises identifiable features that are physically attached in an integral way to particular physical objects.”

[^6]: CRM: “This class comprises physical features that are purposely created by human activity, such as scratches, artificial caves, artificial water channels, etc.”

```
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix ecrm: <http://erlangen-crm.org/120111/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix org: <http://www.w3.org/ns/org#>
@prefix lgd: <http://linkedgeodata.org/page/triplify/> .
@prefix osm: <http://www.openstreetmap.org/> .
@prefix data: <http://data.ub.tu-dortmund.de/resource/> .

data:site/TUDortmundUniversity 
  a ecrm:E27_Site , org:Site ;
  skos:prefLabel "Technische Universität Dortmund"@de , "TU Dortmund University"@en ;
  skos:altLabel "TU Dortmund" , "Universität Dortmund"@de , "Dortmund University"@en ;
  rdfs:isDefinedBy data:site/TUDortmundUniversity/about.rdf ;
  ecrm:P46i_forms_part_of lgd:relation1829065 ;
  ecrm:P46_is_composed_of data:site/NorthernCampus , data:site/SouthernCampus ;
  org:siteOf data:gnd/16039348-6 .
```
```
data:site/NorthernCampus 
  a ecrm:E27_Site, org:Site ;
  skos:prefLabel "Campus Nord"@de , "Northern Campus"@en ;
  rdfs:isDefinedBy data:site/NorthernCampus/about.rdf ;
  ecrm:P46i_forms_part_of data:site/TUDortmundUniversity ;
  ecrm:P46_is_composed_of data:feature/VP_76 , ... , data:feature/EF_50 ;
  owl:sameAs lgd:way130972690 ;
  rdfs:seeAlso osm:way/130972690 .
```
```
data:feature/VP_76
  a ecrm:E25_Man-Made_Feature, org:Site ;
  skos:prefLabel "Vogelpothsweg 76" ;
  skos:altLabel "Zentralbibliothek"@de , "Central Library"@en , "ZB"@de , "CL"@en , "VP 76" ;
  rdfs:isDefinedBy data:feature/VP_76/about.rdf ;
  ecrm:P46i_forms_part_of data:site/NorthernCampus ;
  ecrm:P46_is_composed_of data:feature/VP_76/ThirdFloor , ... , data:feature/VP_76/BasementLevel2 ;
  owl:sameAs lgd:way17059611 ;
  rdfs:seeAlso osm:way/17059611 . 
  org:siteOf data:organisation/DE-290 , data:organisation/DE-290/GB1 , ... .
```

Um präzise Lagerangaben bei Bestandsnachweisen zu beschreiben, sind weitere Kenntnisse innerhalb von Gebäuden, z.B. über Abschnitte oder Etagen, notwendig. Diese lassen sich mittels CRM als `E25_Man-Made_Feature` beschreiben. Die folgenden Beispiele zeigen das dritte Obergeschoss, das zweite Untergeschoss sowie den Zeitschriftenlesesaal im Erdgeschoss des Gebäudes Vogelpothsweg 76 (`VP_76`) auf Campus Nord.
```
data:feature/VP_76/ThirdFloor
  a ecrm:E25_Man-Made_Feature , org:Site ;
  skos:prefLabel "3. Obergeschoss"@de , "Third Floor"@en ;
  skos:altLabel "3.OG"@de ;
  rdfs:isDefinedBy data:feature/VP_76/ThirdFloor/about.rdf ;
  ecrm:P46i_forms_part_of data:feature/VP_76 ;
  ecrm:P46_is_composed_of data:collection/290/0/Sn .
```
```
data:feature/JournalsReadingRoom
  a ecrm:E25_Man-Made_Feature , org:Site ;
  skos:prefLabel "Zeitschriftenlesesaal"@de , "Journals Reading Room"@en ;
  ecrm:P46i_forms_part_of data:feature/VP_76/GroundFloor .
]  .
```
Damit auch Aussagen in Bezug auf eine der dem Ort zugeordneten Organisation getroffen werden können, sind die Objekte auch vom Typ Site der W3C Organization Ontology.

## Sammlungen in der Bibliothek

Die physischen Bestände sind in Bibliotheken in der Regel systematisch in Sammlungsbereiche geordnet, z.B. als Sektionen basierend auf einer Systematik wie die Dewey Decimal Classification (DDC). Der Charakter dieser Sammlungen findet sich in der CRM-Entität `E78_Collection` wieder und kann mittels der Eigenschaft “forms part of” einem “Feature” und mittels “has current or former curator” einer Einrichtung zugeordnet werden.\
Die folgenden Code-Beispiele zeigen einerseits die Signaturgruppe Sn, welche in der “Freihand”-Sammlung verortet ist und andererseits die “Lehrbuchsammlung”. Beide sind Teil der gesamten Sammlung der Zentralbibliothek.
```
data:collection/290/0
  a ecrm:E78_Collection ;
  skos:prefLabel "Central Library"@en , "Zentralbibliothek"@de ;
  skos:altLabel "ZB"@de , "CL"@de ;
  rdfs:isDefinedBy data:collection/290/0/about.rdf ;
  ecrm:P46i_forms_part_of data:feature/VP_76 ;
  ecrm:P109_has_current_or_former_curator data:organisation/DE-290/Fachreferate .
```
```
data:collection/290/0/1
  a ecrm:E78_Collection ;
  skos:prefLabel "Freihand"@de ;
  rdfs:isDefinedBy data:collection/290/0/1/about.rdf ;
  ecrm:P46i_forms_part_of data:collection/290/0 ;
  ecrm:P46i_forms_part_of (data:feature/VP_76/SecondFloor data:feature/VP_76/ThirdFloor) ;  
  ecrm:P109_has_current_or_former_curator data:organisation/DE-290/Fachreferate .
```
```
data:collection/290/0/1/Sn
  a ecrm:E78_Collection ;
  skos:prefLabel "Signaturgruppe Sn"@de , "Shelf Mark Sn"@en ;
  rdfs:isDefinedBy data:collection/290/0/1/Sn/about.rdf ;
  ecrm:P46i_forms_part_of data:collection/290/0/1 ;
  ecrm:P46i_forms_part_of data:feature/VP_76/ThirdFloor; ;
  ecrm:P109_has_current_or_former_curator data:organisation/DE-290/Fachreferate/Informatik .
```
```
data:collection/290/0/2
  a ecrm:E78_Collection ;
  skos:prefLabel "Textbook Collection"@en , "Lehrbuchsammlung"@de ;
  rdfs:isDefinedBy data:collection/290/0/2/about.rdf ;
  ecrm:P46i_forms_part_of data:collection/290/0 ;
  ecrm:P46i_forms_part_of data:feature/VP_76/GroundLevel; ;
  ecrm:P109_has_current_or_former_curator data:organisation/DE-290/Fachreferate .
```

# Bestandsnachweise konkret

Die bisherigen Daten werden nach ihrer initialen Erstellung relativ selten aktualisiert und stehen somit als administrative Daten bei der
Beschreibung der Bestandsnachweise zur Verlinkung zur Verfügung. Also was bleibt nun noch konkret für den eigentlichen Bestandsnachweis zu tun?
Das folgende Beispiel zeigt, dass bis auf die individuelle Signatur und den Status der zur Verfügung stehenden Services nur noch Links zu erfassen sind. Folgende Links werden benötigt[^7]:

*    Link zum Besitzer
*    Link zur Kollektion
*    Link zur Manifestation*
*    Link zur Publication Expression*
*    ggf. Link zum Production Event*

[^7]: Für die mit * gekennzeichneten Links vgl. den Abschnitt “WEM + I im CIDOC CRM-Universum” in [Bestandsnachweise von Bibliotheken als Linked Data](../../../2013/11/22/bestandsnachweise-von-bibliotheken-als-linked-data.md).

```
data:item/13000956
  a efrbroo:F5_Item ;
  skos:prefLabel "Sn 23555" ;
  rdfs:isDefinedBy data:item/13000956/about.rdf ;
  ecrm:P52_has_current_owner data:organisation/DE-290 ;
  ecrm:P46I_forms_part_of data:collection/290/0/1/Sn ;
  efrbroo:R7_is_example_of data:manifestation/32d8f198-5ec0-4afc-8fe9-0b0388852459 ;
  efrbroo:R6_carries data:expression/c90e09d7 ;
  efrbroo:R28i_was_produced_by data:event/32d8f198-5ec0-4afc-8fe9-0b0388852459 ;
  ecrm:P70i_is_documented_in data:item/13000956/about.rdf .
```

## Fazit und Ausblick

Die vermeintliche Komplexität der Modelle mittels CIDOC CRM und seinen Erweiterungen im Beitrag ["Bestandsnachweise von Bibliotheken als Linked Data"](../../../2013/11/22/bestandsnachweise-von-bibliotheken-als-linked-data.md) lässt sich somit bei genauerer Betrachtung in die vier Bereiche location, organization, collection und holding aufteilen und somit erheblich reduzieren.

Für die tatsächliche Erfassungsarbeit der Bestände durch Bibliothekarinnen und Bibliothekare können in dieser Form sehr einfach gehaltene Formulare dienen, die an den Linking-Felder mit “autosuggest“-Funktionen hinterlegt sind. Im Sinne der Forderung von Dorothea Salo bei der SWIB 13[^8] nach Tools, wäre das ein sehr wertvolles Szenario und ein wesentlicher Schritt vom “Cataloging” zum “Catalinking“.

[^8]: vgl. z.B. mein Tagungsbericht [“In LOD we trust” – Ein Bericht von der SWIB13](https://the-lodlam-mercury.de/2014/08/08/in-lod-we-trust-ein-bericht-von-der-swib13/)

***
