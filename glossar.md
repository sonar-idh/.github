# Glossar 

## XML: Struktur, Validierung und Verarbeitung

### XML

Auszeichnungssprache zur Darstellung hierarchisch strukturierter Daten im Format einer Textdatei, die sowohl von Menschen als auch von Maschinen lesbar ist. Besteht aus Elementen, die entweder Text oder weitere Elemente enthalten (Baumstruktur). Diese werden durch verschiedene *Tags* markiert:

- ein Starttag für den Beginn eines Elementes: `<Elementname>`
- ein Endtag für das Ende eines Elementes: `</Elementname>`
- ein Leertag für ein Element ohne Inhalt: `<Elementname/>`

Die Validität eines XML-Dokuments kann mithilfe einer [Document Type Definition](#document-type-definition-dtd) oder einer [XML Schema Definition (XSD)](#xml-schema-definition-xsd) geprüft werden.

### Document Type Definition (DTD)

Eine Menge an Regeln, die benutzt wird, um XML-basierte Dokumente eines bestimmten Typs zu deklarieren. Ein Dokumenttyp ist dabei eine Klasse ähnlicher Dokumente, wie beispielsweise Telefonbücher oder Inventurdatensätze. Die Document Type Definition besteht dabei aus Elementtypen, Attributen von Elementen, Entitäten und Notationen. Konkret heißt das, dass in einer DTD die Reihenfolge, die Verschachtelung der Elemente und die Art des Inhalts von Attributen festgelegt wird, also die Struktur des Dokuments.

### XML Schema Definition (XSD)

Standard zur Beschreibung und Validierung der Struktur von XML-Dokumenten. Wie eine [Document Type Definition](#document-type-definition-dtd) legt eine XSD fest, welche Elemente und Attribute in welcher Reihenfolge und Verschachtelung vorkommen dürfen. Anders als eine DTD ist eine XSD jedoch selbst ein XML-Dokument und lässt sich daher mit denselben Werkzeugen verarbeiten. Außerdem bietet sie im Gegensatz zu einer       DTD ein umfangreiches Typsystem: Der Inhalt von Elementen und Attributen kann genau typisiert werden (z. B. als Ganzzahl, Datum, Wahrheitswert oder als Zeichenkette mit vorgegebenem Muster), Häufigkeiten lassen sich präzise angeben (`minOccurs`/`maxOccurs`), und man kann eigene, wiederverwendbare Datentypen definieren. XSD unterstützt zudem [XML-Namespaces](#namespace-xml-namensraum).

### Namespace (XML-Namensraum)

Mechanismus, um Element- und Attributnamen eindeutig einer bestimmten Vokabular- bzw. Herkunftsquelle zuzuordnen. Notwendig wird das, sobald in einem [XML](#xml)-Dokument Vokabulare aus verschiedenen Quellen kombiniert werden, die zufällig gleichlautende Namen verwenden — ein `title` aus dem einen Vokabular wäre sonst nicht von einem `title` aus einem anderen zu unterscheiden. Ein Namespace wird durch eine eindeutige Kennung in Form einer URI identifiziert. Diese ist nur ein Bezeichner und muss nicht zwingend auf eine abrufbare Ressource verweisen, auch wenn häufig URLs verwendet werden.

Deklariert wird ein Namespace über das Attribut `xmlns`:

- mit Präfix: `xmlns:mods="http://www.loc.gov/mods/v3"` — die zugehörigen Elemente werden dann mit diesem Präfix qualifiziert, z. B. `<mods:title>`
- als Standard-Namespace (ohne Präfix): `xmlns="http://www.loc.gov/mods/v3"` — gilt dann für das Element und alle nicht anderweitig qualifizierten Kindelemente

Das Präfix selbst ist frei wählbar und nur ein lokales Kürzel. Maßgeblich für die Eindeutigkeit ist allein die dahinterstehende URI.

### XSL Transformation (XSLT)

Sprache zur Transformation von [XML](#xml)-Dokumenten in andere Formate. Eine XSLT-Transformation ist selbst ein XML-Dokument und beschreibt Transformationsregeln für Dokumentteile wie Elemente oder Attribute. Ein XSLT-Prozessor (wie z.B. [Saxon](https://de.wikipedia.org/wiki/Saxon_(Software))) wendet diese Regeln auf ein Eingabedokument an und erzeugt daraus das Ergebnisdokument, das Original bleibt dabei unverändert. Zur Adressierung der zu verarbeitenden Teile des Eingabebaums nutzt XSLT die Sprache [XPath](#xpath).

### XPath

Sprache zur Adressierung einzelner Teile eines [XML](#xml)-Dokuments. XPath beschreibt einen Pfad durch die Baumstruktur des Dokuments und wählt damit bestimmte Elemente, Attribute oder Textinhalte aus. Diese Angabe ist vergleichbar mit einer Pfadangabe in einem Dateisystem. Ein Ausdruck wie `/mods:mods/mods:titleInfo/mods:title` adressiert beispielsweise das `title`-Element innerhalb von `titleInfo` innerhalb des Wurzelelements `mods`. XPath wird unter anderem von [XSLT](#xsl-transformation-xslt) und vielen weiteren XML-Werkzeugen zur Selektion verwendet.

## Forschungsdaten/ SoNAR-Forschungsdaten

"Forschungsdaten sind durch eine spezifische Methode und Schritte der Operationalisierung systematisch gewonnene, strukturierte Informationen, die (computergestützt) ausgewertet und verarbeitet werden können. Sie bilden die Grundlage des Forschungsprozesses. Daten können sowohl quantitativen wie qualitativen Charakter tragen. In den Geschichtswissenschaften sind Forschungsdaten häufig (die Nennung bleibt beispielhaft):
- Texte, Transkriptionen, edierte Texte bis hin zu Textsammlungen und Corpora mit oder ohne Annotationen
- qualitative und quantitative empirisch erhobene Rohdaten, **bereinigte Daten**, **verschnittene oder aggregierte Daten**, Analysedaten
- komplexere Hypertexte, webbasierte Textsammlungen
- Historische Informationssysteme bzw. Historische Geo-Informationssysteme" (Quelle: Historisches Datenzentrum Sachsen-Anhalt, Serviceabteilung Digital Humanities und Digital History; Link: https://www.geschichte.uni-halle.de/struktur/hist-data/datenmanagement/)
  --> SoNAR-Netzwerkdaten können als bereinigte Daten, als verschnittene Daten und als aggregierte Daten verstanden werden.
