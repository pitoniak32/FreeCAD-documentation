# <img alt="Sketcher Arbeitsbereichssymbol" src=images/Workbench_Sketcher.svg  style="width   *64px;"> Sketcher Workbench/de


{{TOCright}}

## Einführung

Der FreeCAD-Arbeitsbereich <img alt="" src=images/Workbench_Sketcher.svg  style="width   *24px;"> [Sketcher](Sketcher_Workbench/de.md) wird verwendet, um 2D-Geometrien für den Gebrauch in den Arbeitsbereichen <img alt="" src=images/Workbench_PartDesign.svg  style="width   *24px;"> [PartDesign](PartDesign_Workbench/de.md), <img alt="" src=images/Workbench_Arch.svg  style="width   *24px;"> [Arch](Arch_Workbench/de.md) und anderen Arbeitsbereichen zu erstellen. Im Allgemeinen wird eine 2D-Zeichnung als Ausgangspunkt für die meisten CAD-Modelle angesehen, da eine 2D-Skizze \"extrudiert\" werden kann, um eine 3D-Form zu erstellen; weitere 2D-Skizzen können verwendet werden, um andere Merkmale wie Taschen, Stege oder Extrusionen auf den zuvor erstellten 3D-Formen zu erstellen. Zusammen mit booleschen Operationen, definiert im Arbeitsbereich <img alt="" src=images/Workbench_Part.svg  style="width   *24px;"> [Part](Part_Workbench/de.md), bildet der Sketcher die Grundlage der [Konstruktive-Festkörpergeometrie](constructive_solid_geometry/de.md)-Methode (engl. constructive solid geometry (CSG) method) für den Aufbau von Volumenkörpern. Darüber hinaus bildet der Sketcher zusammen mit den Abläufen des Arbeitsbereichs <img alt="" src=images/Workbench_PartDesign.svg  style="width   *24px;"> [PartDesign](PartDesign_Workbench/de.md) auch die Grundlage der Methodik der [Formelemente-Bearbeitung](feature_editing/de.md) zum erstellen von Geometrieelementen, um Volumenkörper zu erzeugen.

Der Arbeitsbereich Sketcher bietet *Randbedingungen* (auch   * Ein-/Beschränkungen; engl.   * constraints), die es 2D-Formen erlauben/ermöglichen, präzisen geometrischen Vorgaben bezüglich Länge, Winkel und Lage (wie horizontal, vertikal, rechtwinklig, usw.) zu folgen. Ein Löser für geometrische Gleichungen (Constraint-Solver) berechnet die vorgegebene Ausdehnung der 2D-Geometrie und ermöglicht die interaktive Untersuchung von Freiheitsgraden in der Skizze.

<img alt="" src=images/FC_ConstrainedSketch.png  style="width   *450px;"> 
*Eine vollständig bestimmte Skizze‎*

## Grundlagen des Skizzierens mit Randbedingungen 

Um zu erklären, wie der Sketcher arbeitet, ist es sinnvoll, das Vorgehen mit der traditionellen Art des Entwerfens zu vergleichen.

#### Traditionelle Zeichnungserstellung 

Die traditionelle Art des CAD-Zeichnens leitet sich vom Zeichnen am [Reißbrett](https   *//de.wikipedia.org/wiki/Rei%C3%9Fbrett) ab. [Orthogonale (2D-) Ansichten](https   *//de.wikipedia.org/wiki/Orthogonalprojektion) werden von Hand gezeichnet, um technische Zeichnungen (auch Blaupausen genannt) zu erstellen. Objekte werden genau in der vorgesehenen Größe oder den Abmaßen entsprechend gezeichnet. Soll eine horizontale Linie von 100 mm Länge gezeichnet werden, die bei (0,0) beginnt, aktiviert man das Linienwerkzeug, klickt auf auf den Bildschirm oder gibt die Koordinaten für den ersten Punkt (0,0) ein, klickt ein zweites Mal oder gibt die Koordinaten des zweiten Punktes (100,0) ein. Oder man zeichnet die Linie ohne Rücksicht auf ihre Position und verschiebt sie hinterher. Wenn die Geometrien fertig gezeichnet sind, werden noch Maße hinzugefügt.

#### Skizzieren mit Randbedingungen 

Der **Sketcher** (Skizzierer) entfernt sich von dieser Logik. Objekte müssen (zuerst) nicht genau so gezeichnet werden, wie man es (letztlich) beabsichtigt, da sie später durch Randbedingungen festgelegt werden. Objekte können grob gezeichnet werden und solange sie nicht festgelegt sind, können sie verändert werden. Sie sind gewissermaßen *schwebend* und können verschoben, gestreckt, gedreht, skaliert, usw. werden. Das ergibt eine große Flexibilität im Entwurfsprozess.

#### Was sind Randbedingungen? 

Anstelle von Maßen werden Randbedingungen (auch Beschränkungen, Einschränkungen, Zwangsbedingung genannt) verwendet, um die Freiheitsgrade eines Objektes zu reduzieren. Beispielsweise besitzt eine (2D-) Linie ohne Randbedingung 4 [Freiheitsgrade](#Degrees_Of_Freedom/de.md) (engl.   * Degree(s) of freedom, abgekürzt als \"DOF\")   * Sie kann horizontal oder vertikal verschoben, sie kann gestreckt, oder gedreht werden.

Durch Vorgabe einer Ausrichtung, wie horizontal, vertikal oder eines Winkels (relativ zu einer anderen Linie oder zu einer der Achsen), wird ihr die Fähigkeit zu rotieren genommen, sodass 3 Freiheitsgrade übrig bleiben. Das Festsetzen eines der Punkte relativ zum Ursprung entfernt weitere 2 Freiheitsgrade. Und das Festlegen der Länge entfernt den letzten Freiheitsgrad. Die Skizze ist dann **vollständig bestimmt**.

Mehrere Objekte können relativ zueinander ausgerichtet werden. Zwei Linien können durch je einen ihrer Punkte mit der Bedingung KoinzidentFestlegen (deckungsgleich) verbunden werden. Ein Winkel kann zwischen ihnen festgelegt werden oder sie können rechtwinklig zueinander festgelegt werden. Eine Linie kann tangential zu einem Bogen oder einem Kreis sein, usw. Eine komplexe Skizze mit mehreren Objekten kann auf verschiedene Arten festgelegt werden und wenn man sie **vollständig bestimmt**, bedeutet dies, dass, basierend auf den verwendeten Randbedingungen, genau eine dieser Möglichkeiten erreicht wurde.

Es gibt zwei Arten von Randbedingungen   * geometrische und maßliche. Sie sind im Abschnitt [\'Werkzeuge\'](#Werkzeuge.md) weiter unten ausführlich beschrieben.

#### Wofür der Skizzierer nicht geeignet ist 

Der Sketcher ist nicht für die Herstellung von (2D-) Zeichnungen (Blaupausen) vorgesehen. Sobald Skizzen verwendet werden, um eine Volumenkörpermerkmal zu erzeugen, werden sie automatisch verborgen. Randbedingungen sind nur im Skizzenbearbeitungsmodus sichtbar.


<div class="mw-translate-fuzzy">

Falls nur 2D-Ansichten zum Ausdrucken erzeugt werden sollen und keine 3D-Modelle, sollte man einen Blick auf den Arbeitsbereich [Draft](Draft_Workbench/de.md) werfen. Anders als Sketcher-Elemente, verwenden Draft-Objekte keine Randbedingungen; sie sind einfache Formen, die im Augenblick der Erstellung definiert werden. Sowohl Draft als auch Sketcher können zum Zeichnen von 2D-Geometrien und zum Erzeugen von 3D-Volumenkörpern verwendet werden, obwohl ihre bevorzugte Verwendung unterschiedlich ist.Der Sketcher wird normalerweise mit den Arbeitsbereichen [Part](Part_Workbench/de.md) und [PartDesign](PartDesign_Workbench/de.md) verwendet um Volumenkörper zu erzeugen. Draft wird normalerweise für einfache ebene Zeichnungen verwendet über einem Raster, so wie beim Zeichnen eines Architektur Grundrisses; in solchen Situationen werden Draft-Objekte hauptsächlich zusammen mit dem Arbeitsbereich [Arch](Arch_Workbench/de.md) verwendet. Das Werkzeug [Zeichnung zu Skizze](Draft_Draft2Sketch/de.md) wandelt ein Draft-Objekt in ein Skizzenobjekt und umgekehrt. Viele Werkzeuge, die ein 2D-Element als Eingabe benötigen, arbeiten mit beiden Objekttypen, da intern eine automatische Umwandlung erfolgt.


</div>

## Arbeitsablauf beim Skizzieren 


<div class="mw-translate-fuzzy">

Eine Skizze ist stets zweidimensional (2D). Um einen Volumenkörper zu erzeugen, wird eine 2D-Skizze eines einzelnen, eingeschlossenen Bereichs erstellt und dann entweder aufgepolstert oder gedreht, um die dritte Dimension hinzuzufügen und so einen 3D-Volumenkörper aus einer 2D-Skizze zu erzeugen.


</div>


<div class="mw-translate-fuzzy">

Wenn eine Skizze Segmente besitzt, die einander überschneiden, sie Stellen enthält an denen ein Punkt nicht direkt auf einem Segment liegt, oder Stellen an denen Lücken zwischen Endpunkten angrenzender Segmente existieren, werden Aufpolstern oder Rotieren keine Festkörper erstellen. Manchmal funktioniert eine Skizze, die sich überschneidende Linien enthält, für eine einfache Operation wie Aufpolstern, jedoch werden spätere Arbeitsgänge wie etwa lineare Muster fehlschlagen. Am besten vermeidet man sich überschneidende Linien. Die Konstruktionsgeometrie (blau) bildet eine Ausnahme von dieser Regel.


</div>


<div class="mw-translate-fuzzy">

Innerhalb des geschlossenen Bereiches können sich kleinere nicht überlappende Bereiche befinden. Diese bleiben leer, wenn der 3D-Volumenkörper erstellt wird.


</div>


<div class="mw-translate-fuzzy">

Sobald eine Skizze vollständig bestimmt ist, wechselt die Farbe der Skizzenelemente auf grün; Konstruktionsgeometrie bleibt blau. Normalerweise ist die Skizze an dieser Stelle \"fertig bearbeitet\" und für die Erstellung eines 3D-Volumenkörpers geeignet. Nach dem Schließen des Skizzendialogs, kann es aber nützlich sein, zum Arbeitsbereich <img alt="" src=images/Workbench_Part.svg  style="width   *24px;"> [Part](Part_Workbench/de.md) zu wechseln und **[<img src=images/Part_CheckGeometry.svg style="width   *24px"> [GeometriePrüfen](Part_CheckGeometry/de.md)** auszuführen, um sicherzustellen, dass die Skizze keine Elemente enthält, die später zu Problemen führen können.


</div>

## Werkzeuge

Die Werkzeuge des Arbeitsbereichs Sketcher sind alle im Sketch-Menü zu finden, das beim Laden des Arbeitsbereichs erscheint.

### Allgemein

-   <img alt="" src=images/Sketcher_NewSketch.png‎‎  style="width   *32px;"> [Skizze erstellen](Sketcher_NewSketch/de.md)   * Erstellt eine neue Skizze auf einer ausgewählten Fläche oder Ebene. Falls bei der Ausführung dieses Werkzeugs keine Fläche gewählt wurde, wird der Benutzer über ein Dialogfenster zur Auswahl einer Ebene aufgefordert.

-   <img alt="" src=images/Sketcher_EditSketch.png  style="width   *32px;"> [Skizze bearbeiten](Sketcher_EditSketch/de.md)   * Editieren der gewählten Skizze. Dies öffnet den [Sketcher-Dialog](Sketcher_Dialog/de.md).

-   <img alt="" src=images/Sketcher_LeaveSketch.png  style="width   *32px;"> [Skizze verlassen](Sketcher_LeaveSketch/de.md)   * Beendet den Bearbeitungsmodus des Sketchers.

-   <img alt="" src=images/Sketcher_ViewSketch.png‎  style="width   *32px;"> [Skizze anzeigen](Sketcher_ViewSketch/de.md)   * Legt die Modellansicht senkrecht zur Skizzierebene fest.

-   <img alt="" src=images/Sketcher_ViewSection.svg  style="width   *32px;"> [Schnitt anzeigen](Sketcher_ViewSection/de.md)   * Erzeugt eine Schnittebene, und verbirgt vorübergehend alles, was sich vor der Skizzierebene befindet.

-   <img alt="" src=images/Sketcher_MapSketch.svg‎  style="width   *32px;"> [Skizze einer Fläche zuordnen](Sketcher_MapSketch/de.md)   * Ordnet eine Skizze der vorher gewählten Fläche eines Volumenkörpers zu.

-   <img alt="" src=images/Sketcher_ReorientSketch.svg  style="width   *32px;"> [Skizze neu ausrichten](Sketcher_ReorientSketch/de.md)   * Ermöglicht, die Skizze einer der Hauptebenen zuzuordnen.

-   <img alt="" src=images/Sketcher_ValidateSketch.svg  style="width   *32px;"> [Skizze überprüfen](Sketcher_ValidateSketch/de.md)   * Überprüft die Toleranz verschiedener Punkte und passt sie an.

-   <img alt="" src=images/Sketcher_MergeSketch.svg‎  style="width   *32px;"> [Skizzen zusammenführen](Sketcher_MergeSketches/de.md)   * Führt zwei oder mehr Skizzen zusammen.

-   <img alt="" src=images/Sketcher_MirrorSketch.svg‎  style="width   *32px;"> [Skizze spiegeln](Sketcher_MirrorSketch/de.md)   * Spiegelt eine Skizze entlang der X-Achse, der Y-Achse oder dem Ursprung.

-   <img alt="" src=images/Sketcher_StopOperation.svg  style="width   *32px;"> [Vorgang beenden](Sketcher_StopOperation/de.md)   * Wenn der Bearbeitungsmodus aktiv ist, wird der aktuellen Vorgang beendet, egal ob es sich um das Zeichnen oder das Festlegen von Randbedingungen usw. handelt.

### Sketcher-Geometrien 

Dies sind Werkzeuge zum Erstellen von Objekten.

-   <img alt="" src=images/Sketcher_CreatePoint.png  style="width   *32px;"> [Punkt erstellen](Sketcher_CreatePoint/de.md)   * Zeichnet einen Punkt.

-   <img alt="" src=images/Sketcher_CreateLine.svg  style="width   *32px;"> [Linie erstellen](Sketcher_CreateLine/de.md)   * Zeichnet ein Linienabschnitt zwischen 2 Punkten. Linien werden von bestimmten Randbedingungen als unendlich angesehen.

-   <img alt="" src=images/Sketcher_CompCreateArc.png  style="width   *48px;">[Bogen erstellen](Sketcher_CompCreateArc/de.md)   * Dies ist ein Symbolmenü in der Sketcher-Werkzeugleiste, das die folgenden Befehle enthält   *

   ** <img alt="" src=images/Sketcher_CreateArc.svg  style="width   *32px;"> [Bogen aus Mittelpunkt erstellen](Sketcher_CreateArc/de.md)   * Zeichnet ein Kreissegment aus Mittelpunkt, Radius, Startwinkel und Endwinkel.

   ** <img alt="" src=images/Sketcher_Create3PointArc.svg  style="width   *32px;"> [Kreisbogen durch 3 Punkte erstellen](Sketcher_Create3PointArc/de.md)   * Zeichnet einen Kreisbogen durch zwei Endpunkte und einem weiteren Punkt auf dem Umfang.

-   <img alt="" src=images/Sketcher_CompCreateCircle.png  style="width   *48px;">[Kreis erstellen](Sketcher_CompCreateCircle/de.md)   * Dies ist ein Symbolmenü in der Sketcher-Werkzeugleiste, das die folgenden Befehle enthält   *

   ** <img alt="" src=images/Sketcher_Circle.svg  style="width   *32px;"> [Kreis erstellen](Sketcher_CreateCircle/de.md)   * Zeichnet einen Kreis aus Mittelpunkt und Radius.

   ** <img alt="" src=images/Sketcher_Create3PointCircle.svg  style="width   *32px;"> [Kreis aus drei Punkten erstellen](Sketcher_Create3PointCircle/de.md)   * Zeichnet einen Kreis durch drei Punkten auf dem Umfang.

-   <img alt="" src=images/Sketcher_CompCreateConic.png  style="width   *48px;"> [Kegelschnitt erstellen](Sketcher_CompCreateConic/de.md)   * Der Sketcher stellt die folgenden Kegelschnitte bereit. Im Gegensatz zu B-Splines können sie mit allen Arten von Randbedingungen wie z. B. [Tangente setzen](Sketcher_ConstrainTangent/de.md), [Punkt auf Objekt festlegen](Sketcher_ConstrainPointOnObject/de.md), oder [Orthogonalität festlegen](Sketcher_ConstrainPerpendicular/de.md) verwendet werden.

   ** <img alt="" src=images/Sketcher_CreateEllipseByCenter.svg  style="width   *32px;"> [Ellipse um Mittelpunkt erstellen](Sketcher_CreateEllipseByCenter/de.md)   * Zeichnet eine Ellipse aus Mittelpunkt, Hauptradiuspunkt und Nebenradiuspunkt.

   ** <img alt="" src=images/Sketcher_CreateEllipseBy3Points.svg  style="width   *32px;"> [Ellipse durch 3 Punkte erstellen](Sketcher_CreateEllipseBy3Points/de.md)   * Zeichnet eine Ellipse aus Hauptradius (2 Punkte) und kleinem Radiuspunkt.

   ** <img alt="" src=images/Sketcher_CreateArcOfEllipse.svg  style="width   *32px;"> [Ellipsenbogen erstellen](Sketcher_CreateArcOfEllipse/de.md)   * Zeichnet einen Ellipsenbogen aus Mittelpunkt, Hauptradiuspunkt, Startpunkt und Endpunkt.

   ** <img alt="" src=images/Sketcher_CreateArcOfHyperbola.svg  style="width   *32px;"> [Hyperbelbogen erstellen](Sketcher_CreateArcOfHyperbola/de.md)   * Zeichnet einen Hyperbelbogen.

   ** <img alt="" src=images/Sketcher_CreateArcOfParabola.svg  style="width   *32px;"> [Parabelbogen erstellen](Sketcher_CreateArcOfParabola/de.md)   * Zeichnet einen Parabelbogen.

-   <img alt="" src=images/Sketcher_CompCreateBSpline.png  style="width   *48px;"> [B-spline erstellen](Sketcher_CompCreateBSpline/de.md)   * Dies ist ein Symbolmenü in der Skizzierer Werkzeugleiste, das die folgenden Befehle enthält   *

   ** <img alt="" src=images/Sketcher_CreateBSpline.svg  style="width   *32px;"> [B-Spline erstellen](Sketcher_CreateBSpline/de.md)   * Zeichnet eine B-Spline-Kurve über ihre Kontrollpunkte.

   ** <img alt="" src=images/Sketcher_CreatePeriodicBSpline.svg  style="width   *32px;"> [Geschlossenen B-Spline erstellen](Sketcher_CreatePeriodicBSpline/de.md)   * Zeichnet eine periodische (geschlossene) B-Spline-Kurve über ihre Kontrollpunkte.

-   <img alt="" src=images/Sketcher_CreatePolyline.svg  style="width   *32px;"> [Linienzug erstellen](Sketcher_CreatePolyline/de.md)   * Zeichnet eine Linie aus mehreren Liniensegmenten. Das Drücken der **M**-Taste während des Zeichnens eines Linienzuges, wechselt zwischen den verschiedenen Linienzug-Modi.

-   <img alt="" src=images/Sketcher_CompCreateRectangles.png  style="width   *48px;"> [Rechtecke erstellen](Sketcher_CompCreateRectangles/de.md)   * Dies ist ein Symbolmenü in der Sketcher-Symbolleiste, das die folgenden Befehle enthält   * {{Version/de|0.20}}

   ** <img alt="" src=images/Sketcher_CreateRectangle.svg  style="width   *32px;"> [Rechteck erstellen](Sketcher_CreateRectangle/de.md)   * Zeichnet ein Rechteck durch zwei gegenüberliegende Punkte.

   ** <img alt="" src=images/Sketcher_CreateRectangle_Center.svg  style="width   *32px;"> [Zentriertes Rechteck erstellen](Sketcher_CreateRectangle_Center/de.md)   * Zeichnet ein Rechteck aus einem zentralen Punkt und einem Eckpunkt. {{Version/de|0.20}}

   ** <img alt="" src=images/Sketcher_CreateOblong.svg  style="width   *32px;"> [Abgerundetes Rechteck erstellen](Sketcher_CreateOblong/de.md)   * Zeichnet ein abgerundetes Rechteck aus 2 gegenüberliegenden Punkten. {{Version/de|0.20}}

-   <img alt="" src=images/Sketcher_CreateHexagon.png  style="width   *32px;"> [Regelmäßiges Vieleck erstellen](Sketcher_CompCreateRegularPolygon/de.md)   * Dies ist ein Symbolmenü in der Sketcher-Werkzeugleiste, das die folgenden Befehle enthält   *

   ** <img alt="" src=images/Sketcher_CreateTriangle.svg  style="width   *32px;"> [Gleichseitiges Dreieck erstellen](Sketcher_CreateTriangle/de.md)   * Zeichnet ein gleichseitiges Dreieck, das einem Konstruktionsgeometriekreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreateSquare.svg  style="width   *32px;"> [Quadrat erstellen](Sketcher_CreateSquare/de.md)   * Zeichnet ein Quadrat, das einem Konstruktionsgeometriekreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreatePentagon.png  style="width   *32px;"> [Fünfeck erstellen](Sketcher_CreatePentagon/de.md)   * Zeichnet ein regelmäßigen Fünfeck das einem Umkreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreateHexagon.svg  style="width   *32px;"> [Sechseck erstellen](Sketcher_CreateHexagon/de.md)   * Zeichnet ein regelmäßiges Sechseck, das einem Umkreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreateHeptagon.png  style="width   *32px;"> [Siebeneck erstellen](Sketcher_CreateHeptagon/de.md)   * Zeichnet ein regelmäßiges Siebeneck, das einem Umkreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreateOctagon.png  style="width   *32px;"> [Achteck](Sketcher_CreateOctagon/de.md)   * Zeichnet ein regelmäßiges Achtecks, das einem Umkreis einbeschrieben ist.

   ** <img alt="" src=images/Sketcher_CreateRegularPolygon.svg  style="width   *32px;"> [Regelmäßiges Vieleck erstellen](Sketcher_CreateRegularPolygon/de.md)    * Zeichnet ein regelmäßiges Vieleck durch Auswahl der Anzahl der Seiten und Auswahl zweier Punkte   * dem Zentrum und einer Ecke.

-   <img alt="" src=images/Sketcher_CreateSlot.svg  style="width   *32px;"> [Nut erstellen](Sketcher_CreateSlot/de.md)   * Zeichnet ein Oval, indem das Zentrum des einen Halbkreises und ein Endpunkt des anderen Halbkreises ausgewählt werden.

-   <img alt="" src=images/Sketcher_CompCreateFillets.png  style="width   *48px;"> [Create a fillet](Sketcher_CompCreateFillets.md)   * This is an icon menu in the Sketcher toolbar that holds the following commands   *


<div class="mw-translate-fuzzy">

-   <img alt="" src=images/Sketcher_CreateFillet.png  style="width   *32px;"> [Abrundung erstellen](Sketcher_CreateFillet/de.md) (Verrundung)   * Erstellt eine Verrundung zwischen zwei Linien, die an einem Punkt verbunden sind. Beide Linien oder den Eckpunkt auswählen und anschließend das Werkzeug aktivieren.


</div>

   ** <img alt="" src=images/Sketcher_CreatePointFillet.svg  style="width   *32px;"> [Corner-preserving fillet](Sketcher_CreatePointFillet.md)   * Creates a fillet between two non-parallel lines while preserving their (virtual) intersection.

-   <img alt="" src=images/Sketcher_Trimming.png  style="width   *32px;"> [Kante zuschneiden](Sketcher_Trimming/de.md)   * Stutzt eine Gerade, einen Kreis oder Kreisbogen unter Berücksichtigung des angeklickten Punktes.

-   <img alt="" src=images/Sketcher_Extend.svg  style="width   *32px;"> [Kante verlängern](Sketcher_Extend/de.md)   * Verlängert eine Linie oder einen Kreisbogen bis zu einer Grenzlinie, einem Bogen, einer Ellipse, einem Ellipsenbogen oder einem Punkt im Raum.

-   <img alt="" src=images/Sketcher_Split.svg  style="width   *32px;"> [Kante teilen](Sketcher_Split/de.md)   * Teilt eine Linie oder einen Bogen in zwei, wandelt einen Kreis in einen Bogen um und behält dabei die meisten Randbedingungen bei. {{Version/de|0.20}}

-   <img alt="" src=images/Sketcher_External.svg  style="width   *32px;"> [Externe Geometrie](Sketcher_External/de.md)   * Erstellt eine mit externer Geometrie verknüpfte Kante.

-   <img alt="" src=images/Sketcher_CarbonCopy.svg  style="width   *32px;"> [Pause](Sketcher_CarbonCopy/de.md)   * Paust die Geometrie aus einer anderen Skizze ab.

-   <img alt="" src=images/Sketcher_ToggleConstruction.svg  style="width   *32px;"> [Umschalten der Hilfsgeometrie](Sketcher_ToggleConstruction/de.md)   * Schaltet die Skizzengeometrie vom/zum Konstruktionsmodus um. Die Konstruktionsgeometrie wird in Blau angezeigt und ist außerhalb des Bearbeitungsmodus nicht sichtbar.

### Skizzierbeschränkungen

Beschränkungen werden benutzt, um Längen zu definieren, Regeln zwischen Skizzenelementen aufzustellen und die Skizze entlang der vertikalen und horizontalen Achsen festzulegen. Einige Beschränkungen benötigen die Verwendung von [Hilfsbeschränkungen](Sketcher_helper_constraint/de.md).

#### Besondere Randbedingungen 

Diese Randbedingungen sind nicht mit numerischen Daten verknüpft.

-   <img alt="" src=images/Sketcher_ConstrainCoincident.svg  style="width   *32px;"> [Koinzidenz erzwingen](Sketcher_ConstrainCoincident/de.md) (KoinzidentFestlegen)   * Befestigt einen oder mehrere Punkte (koinzident = deckungsgleich) auf einem anderen Punkt.

-   <img alt="" src=images/Sketcher_ConstrainPointOnObject.svg  style="width   *32px;"> [Punkt auf Objekt festlegen](Sketcher_ConstrainPointOnObject/de.md)   * Befestigt einen Punkt an einem anderen Objekt wie z. B. einer Linie, einem Kreisbogen oder einer Achse.

-   <img alt="" src=images/Sketcher_ConstrainVertical.svg  style="width   *32px;"> [Vertikal einschränken](Sketcher_ConstrainVertical/de.md) (VertikalFestlegen)   * Legt die Ausrichtung der ausgewählten Linien oder Linienzugelemente auf genau vertikal fest. Es kann mehr als ein Objekt ausgewählt werden, bevor diese Randbedingung angewendet wird.

-   <img alt="" src=images/Sketcher_ConstrainHorizontal.svg  style="width   *32px;"> [Horizontal einschränken](Sketcher_ConstrainHorizontal/de.md) (HorizontalFestlegen)   * Legt die Ausrichtung der ausgewählten Linien oder Linienzugelemente auf genau horizontal fest. Es kann mehr als ein Objekt ausgewählt werden, bevor diese Randbedingung angewendet wird.

-   <img alt="" src=images/Sketcher_ConstrainParallel.svg  style="width   *32px;"> [Parallelität erzwingen](Sketcher_ConstrainParallel/de.md) (ParallelFestlegen)   * Legt zwei oder mehr Linien parallel zueinander fest.

-   <img alt="" src=images/Sketcher_ConstrainPerpendicular.svg  style="width   *32px;"> [Orthogonalität festlegen](Sketcher_ConstrainPerpendicular/de.md) (RechtwinkligFestlegen)   * Legt zwei Linien senkrecht aufeinander fest oder eine Linie senkrecht auf einen (Kreisbogen in einem) Bogenendpunkt.

-   <img alt="" src=images/Sketcher_ConstrainTangent.svg  style="width   *32px;"> [Tangente setzen](Sketcher_ConstrainTangent/de.md) (TangentialFestlegen)   * Legt eine Tangentenbedingung zwischen zwei ausgewählten Elementen fest; sind zwei Geradenabschnitte ausgewählt werden sie fluchtend (kollinear) festgelegt. Ein Geradenabschnitt muss nicht direkt an einem Kreis oder Kreisbogen liegen, um tangential zu diesem Kreis oder Kreisbogen festgelegt zu werden.

-   <img alt="" src=images/Sketcher_ConstrainEqual.svg  style="width   *32px;"> [Gleichheit festlegen](Sketcher_ConstrainEqual/de.md)   * Setzt die Längen zweier ausgewählter Geradenabschnitte gleich. Bei Verwendung mit Kreisen oder Bögen werden deren Radien gleich gesetzt.

-   <img alt="" src=images/Sketcher_ConstrainSymmetric.svg  style="width   *32px;"> [Symmetrie festlegen](Sketcher_ConstrainSymmetric/de.md)   * Legt zwei Punkte symmetrisch zu einer Linie oder einem dritten Punkt fest.

-   <img alt="" src=images/Sketcher_ConstrainBlock.svg  style="width   *32px;"> [Fixieren](Sketcher_ConstrainBlock/de.md)   * Blockiert die Bewegung einer Kante, d.h. es wird verhindert, dass ihre Knotenpunkte ihre Lage ändern. Es eignet sich besonders, um die Position von B-Splines zu fixieren. Siehe das [Block Constraint forum topic](https   *//forum.freecadweb.org/viewtopic.php?f=9&t=26572) (engl.).

#### Maßliche Randbedingungen 

Dies sind Randbedingungen, die mit numerischen Daten verknüpft sind, für die du die [Ausdrücke](Expressions/de.md) verwenden kannst. Die Daten können aus einer [Kalkulationstabelle](Spreadsheet_Workbench/de.md) entnommen werden.

-   <img alt="" src=images/Sketcher_ConstrainLock.svg  style="width   *32px;"> [Sperren](Sketcher_ConstrainLock/de.md)   * Fixiert das ausgewählte Element (Knotenpunkt), indem der vertikale und der horizontale Abstand relativ zum Ursprung festgelegt werden, wodurch die Position dieses Elements gesperrt wird. Diese Abstandsbedingungen können später bearbeitet werden.

-   <img alt="" src=images/Sketcher_ConstrainDistanceX.svg  style="width   *32px;"> [Horizontalen Abstand festlegen](Sketcher_ConstrainDistanceX/de.md) (XAbstandFestlegen)   * Legt den horizontalen Abstand zwischen zwei Punkten oder Linienendpunkten fest. Wenn nur ein Element ausgewählt ist, wird der Abstand zum Ursprung festgelegt.

-   <img alt="" src=images/Sketcher_ConstrainDistanceY.svg  style="width   *32px;"> [Vertikalen Abstand festlegen](Sketcher_ConstrainDistanceY/de.md) (YAbstandFestlegen)   * Legt den vertikalen Abstand zwischen 2 Punkten oder Linienendpunkten fest. Wenn nur ein Element ausgewählt ist, wird der Abstand zum Ursprung festgelegt.

-   <img alt="" src=images/Sketcher_ConstrainDistance.svg  style="width   *32px;"> [Abstand festlegen](Sketcher_ConstrainDistance/de.md)   * Legt die Länge einer ausgewählten Linie über ihre Enpunkte fest, den senkrechten Abstand eines ausgewählten Punktes auf eine ausgewählte Linie oder legt den Abstand zwischen zwei ausgewählten Punkten.

-   <img alt="" src=images/Sketcher_CompConstrainRadDia.png  style="width   *48px;"> [AuswahlRadDiaFestlegen](Sketcher_CompConstrainRadDia.md)   * Dies ist ein Symbolmenü in der Sketcher-Constraints-Werkzeugleiste, das die folgenden Befehle enthält   *

   ** <img alt="" src=images/Sketcher_ConstrainRadius.svg  style="width   *32px;"> [Radius oder Gewicht festlegen](Sketcher_ConstrainRadius/de.md) (RadiusFestlegen)   * Legt den Radius eines ausgewählten Kreisbogens oder Kreises fest.

   ** <img alt="" src=images/Sketcher_ConstrainDiameter.svg  style="width   *32px;"> [Durchmesser festlegen](Sketcher_ConstrainDiameter/de.md)   * Legt den Durchmesser eines ausgewählten Bogens oder Kreises fest.

   ** <img alt="" src=images/Sketcher_ConstrainRadiam.svg  style="width   *32px;"> [Automatisch Radius/Durchmesser einschränken](Sketcher_ConstrainRadiam/de.md) (RadiamFestlegen)   * Legt automatisch den Radius bzw. Durchmesser eines ausgewählten Bogens oder Kreises fest (Gewicht für einen B-Spline-Pol, Durchmesser für einen vollständigen Kreis, Radius für einen Bogen) {{Version/de|0.20}}

-   <img alt="" src=images/Sketcher_ConstrainAngle.svg  style="width   *32px;"> [Winkel festlegen](Sketcher_ConstrainAngle/de.md)   * Legt den Innenwinkel zwischen zwei ausgewählten Linien fest.

#### Besondere Randbedingungen 

-   <img alt="" src=images/Sketcher_ConstrainSnellsLaw.svg  style="width   *32px;"> [Lichtbrechung (nach Snellius-Gesetz) festlegen](Sketcher_ConstrainSnellsLaw/de.md) (BrechungNachSnelliusFestlegen)   * Legt zwei Linien so fest, dass sie einem Brechungsgesetz unterliegen, um Licht zu simulieren, das eine Grenzfläche passiert.

-   <img alt="" src=images/Sketcher_ConstrainInternalAlignment.svg  style="width   *32px;"> [Interne Ausrichtung festlegen](Sketcher_ConstrainInternalAlignment/de.md)   * Richtet ausgewählte Elemente an der ausgewählten Form aus (z. B. eine Linie, die zur Hauptachse einer Ellipse wird).

#### Werkzeuge für Randbedingungen 

Die folgenden Werkzeuge können verwendet werden, um die Wirkung von Randbedingungen zu ändern   *

-   <img alt="" src=images/Sketcher_ToggleDrivingConstraint.svg  style="width   *32px;"> [Einschränkung zwischen festlegend und anzeigend umschalten](Sketcher_ToggleDrivingConstraint/de.md) (UmschalterFührendeRandbedingung)   * Schaltet die Werkzeugleiste oder die ausgewählten Randbedingungen in den Referenzmodus um oder wieder zurück.

-   <img alt="" src=images/Sketcher_ToggleActiveConstraint.svg  style="width   *32px;"> [Einschränkung aktivieren/deaktivieren](Sketcher_ToggleActiveConstraint/de.md) (UmschalterAktiveRandbedingung)   * Schaltet eine bereits platzierte Randbedingung aktiv bzw. inaktiv. {{Version/de|0.19}}

### Sketcher-Werkzeuge 

-   <img alt="" src=images/Sketcher_SelectElementsWithDoFs.svg  style="width   *32px;"> [Unterbestimmte Elemente auswählen](Sketcher_SelectElementsWithDoFs/de.md)   * Hebt Geometrie mit nicht bestimmten Freiheitsgraden (DOFs), d.h. nicht vollständig bestimmte Geometrie, in grün hervor.

-   <img alt="" src=images/Sketcher_CloseShape.svg  style="width   *32px;"> [Kontur schließen](Sketcher_CloseShape/de.md)   * Erstellt eine geschlossene Form, durch Anwendung der Randbedingung KoinzidentFestlegen auf Endpunkte. Dieses Werkzeug ist veraltet. Es wird in zukünftigen Veröffentlichungen nicht mehr zur Verfügung stehen ({{VersionPlus/de|1.0}}).

-   <img alt="" src=images/Sketcher_ConnectLines.svg  style="width   *32px;"> [Linien verbinden](Sketcher_ConnectLines/de.md)   * Verbindet Skizzenelemente, durch Anwendung der Randbedingung KoinzidentFestlegen auf Endpunkte. Dieses Werkzeug ist veraltet. Es wird in zukünftigen Veröffentlichungen nicht mehr zur Verfügung stehen ({{VersionPlus/de|1.0}}).

-   <img alt="" src=images/Sketcher_SelectConstraints.svg  style="width   *32px;"> [Zugehörige Einschränkungen auswählen](Sketcher_SelectConstraints/de.md) (RandbedingungenAuswählen)   * Wählt die zu einem Skizzenelement gehörenden Randbedingungen aus.

-   <img alt="" src=images/Sketcher_SelectElementsAssociatedWithConstraints.svg  style="width   *32px;"> [Zugehörige Geometrie auswählen](Sketcher_SelectElementsAssociatedWithConstraints/de.md) (ZugehörigeElementeAuswählen)   * Wählt die mit Randbedingungen verknüpften Skizzenelemente aus.

-   <img alt="" src=images/Sketcher_SelectRedundantConstraints.svg  style="width   *32px;"> [überflüssige Einschränkungen wählen](Sketcher_SelectRedundantConstraints/de.md) (RedundanteRandbedingungenAuswählen)   * Wählt redundante Randbedingungen einer Skizze aus.

-   <img alt="" src=images/Sketcher_SelectConflictingConstraints.svg  style="width   *32px;"> [Widersprüchliche Einschränkungen auswählen](Sketcher_SelectConflictingConstraints/de.md) (WidersprüchlicheRandbedingungenAuswählen)   * Wählt widersprüchliche Randbedingungen einer Skizze aus.

-   <img alt="" src=images/Sketcher_RestoreInternalAlignmentGeometry.svg  style="width   *32px;"> [Interne Geometrie anzeigen / ausblenden](Sketcher_RestoreInternalAlignmentGeometry/de.md) (InterneAusrichtungsgeometrieWiederherstellen)   * Stellt fehlende interne Geometrie einer ausgewählten Ellipse oder eines Ellipsen-, Hyperbel-, Parabel- oder B-Spline-Bogens wieder her oder löscht nicht benötigte interne Geometrie.

-   <img alt="" src=images/Sketcher_SelectOrigin.svg  style="width   *32px;"> [Ursprung auswählen](Sketcher_SelectOrigin/de.md)   * Wählt den Ursprung einer Skizze aus

-   <img alt="" src=images/Sketcher_SelectVerticalAxis.svg  style="width   *32px;"> [Vertikale Achse auswählen](Sketcher_SelectVerticalAxis/de.md)   * Wählt die vertikale Achse einer Skizze aus.

-   <img alt="" src=images/Sketcher_SelectHorizontalAxis.svg  style="width   *32px;"> [Horizontale Achse auswählen](Sketcher_SelectHorizontalAxis/de.md)   * Wählt die horizontale Achse einer Skizze aus

-   <img alt="" src=images/Sketcher_Symmetry.svg  style="width   *32px;"> [Symmetrie](Sketcher_Symmetry/de.md)   * Kopiert ein Skizzenelement symmetrisch zu einer ausgewählten Linie.

-   <img alt="" src=images/Sketcher_Clone.svg  style="width   *32px;"> [Klonen](Sketcher_Clone/de.md)   * Klont ein Skizzenelement.

-   <img alt="" src=images/Sketcher_Copy.svg  style="width   *32px;"> [Kopieren](Sketcher_Copy/de.md)   * Kopiert ein Skizzenelement.

-   <img alt="" src=images/Sketcher_Move.svg  style="width   *32px;"> [Verschieben](Sketcher_Move/de.md)   * Verschiebt die ausgewählte Geometrie mit Bezug auf den zuletzt ausgewählten Punkt.

-   <img alt="" src=images/Sketcher_RectangularArray.svg  style="width   *32px;"> [Rechteckige Anordnung](Sketcher_RectangularArray/de.md)   * Erstellt eine Anordnung ausgewählter Skizzenelemente

-   <img alt="" src=images/Sketcher_RemoveAxesAlignment.svg  style="width   *32px;"> [Achsenausrichtung entfernen](Sketcher_RemoveAxesAlignment/de.md)   * Entfernt Achsenausrichtungen der Auswahl, wenn möglich unter Beibehaltung anderer Randbedingungen. {{Version/de|0.20}}

-   <img alt="" src=images/Sketcher_DeleteAllGeometry.svg  style="width   *32px;"> [Gesamte Geometrie löschen](Sketcher_DeleteAllGeometry/de.md) (AlleGeometrienLöschen)   * Löscht sämtliche Geometrie aus der Skizze.

-   <img alt="" src=images/Sketcher_DeleteAllConstraints.svg  style="width   *32px;"> [Alle Einschränkungen löschen](Sketcher_DeleteAllConstraints/de.md) (AlleRandbedingungenLöschen)   * Löscht alle Randbedingungen aus der Skizze.

### Sketcher-B-Spline-Werkzeuge 

-   <img alt="" src=images/Sketcher_BSplineDegree.svg  style="width   *32px;"> [B-Spline Grad ein- / ausblenden](Sketcher_BSplineDegree/de.md) (BSplineGrad)

-   <img alt="" src=images/Sketcher_BSplinePolygon.svg  style="width   *32px;"> [B-Spline-Kontrollpolygon ein- / ausblenden](Sketcher_BSplinePolygon/de.md) (BSplinePolygon)

-   <img alt="" src=images/Sketcher_BSplineComb.svg  style="width   *32px;"> [B-Spline-Krümmungskamm ein- / ausblenden](Sketcher_BSplineComb/de.md) (BSplineKamm)

-   <img alt="" src=images/Sketcher_BSplineKnotMultiplicity.svg  style="width   *32px;"> [Vielfachheit der B-Spline-Knoten ein- / ausblenden](Sketcher_BSplineKnotMultiplicity/de.md) (BSplineKnotenVielfachheit)

-   <img alt="" src=images/Sketcher_BSplinePoleWeight.svg  style="width   *32px;"> [Gewicht der B-Spline-Kontrollpunkte anzeigen / ausblenden](Sketcher_BSplinePoleWeight.md) (BSplinePolGewicht), {{Version/de|0.19}}

-   <img alt="" src=images/Sketcher_BSplineApproximate.svg  style="width   *32px;"> [Geometrie in B-Spline wandeln](Sketcher_BSplineApproximate/de.md) (BSplineApproximieren)

-   <img alt="" src=images/Sketcher_BSplineIncreaseDegree.svg  style="width   *32px;"> [Grad des B-Splines erhöhen](Sketcher_BSplineIncreaseDegree/de.md) (BSplineGradErhöhen)

-   <img alt="" src=images/Sketcher_BSplineDecreaseDegree.svg  style="width   *32px;"> [Grad des B-Splines verringern](Sketcher_BSplineDecreaseDegree.md) (BSplineGradVerringern), {{Version/de|0.19}}

-   <img alt="" src=images/Sketcher_BSplineIncreaseKnotMultiplicity.svg  style="width   *32px;"> [Vielfachheit eines Spline-Knotens erhöhen](Sketcher_BSplineIncreaseKnotMultiplicity/de.md) (BSplineKnotenVielfachheitErhöhen)

-   <img alt="" src=images/Sketcher_BSplineDecreaseKnotMultiplicity.svg  style="width   *32px;"> [Vielfachheit eines Spline-Knotens verringern](Sketcher_BSplineDecreaseKnotMultiplicity/de.md) (BSplineKnotenVielfachheitVerringern)

-   <img alt="" src=images/Sketcher_BSplineInsertKnot.svg  style="width   *32px;"> [Knoten einfügen](Sketcher_BSplineInsertKnot/de.md) (BSplineKnotenEinfügen), {{Version/de|0.20}}

### Virtueller Sketcher-Bereich 

-   <img alt="" src=images/Sketcher_SwitchVirtualSpace.svg  style="width   *32px;"> [Virtuellen Bereich wechseln](Sketcher_SwitchVirtualSpace/de.md)   * Ermöglicht alle Randbedingungen einer Skizze auszublenden und wieder sichtbar zu machen.

## Einstellungen

-   <img alt="" src=images/Std_DlgParameter.png  style="width   *32px;"> [Einstellungen](Sketcher_Preferences/de.md)   * Einstellungen für den Arbeitsbereich **Sketcher**.

## Bewährtes Vorgehen 

Jeder CAD-Benutzer entwickelt im Laufe der Zeit seine eigene Arbeitsweise, aber es gibt einige nützliche allgemeine Grundsätze, denen man folgen kann.


<div class="mw-translate-fuzzy">

-   Eine Reihe einfacher Skizzen ist einfacher handzuhaben als eine komplexe einzelne Skizze. Beispielsweise kann eine erste Skizze für die grundlegenden 3D Funktionen (entweder ein aufpolstern oder ein drehen) erstellt werden, während eine zweite Skizze Löcher oder Ausschnitte (Taschen) enthalten kann. Einige Details können weggelassen werden, um später als 3D Funktionen realisiert zu werden. Sie können wählen, dass Verrundungen in Ihrer Skizze vermieden werden, wenn zu viele vorhanden sind, und diese als 3D Funktionen hinzugefügt werden.
-   Erstelle immer ein geschlossenes Profil, da Deine Skizze keinen Volumenkörper, sondern eine Reihe offener Seitenflächen erzeugt. Wenn Du nicht möchtest, dass einige der Objekte in die Volumenkörpererstellung einbezogen werden, können sie mit dem Konstruktionsmodus Werkzeug in Konstruktionselemente umgewandelt werden.
-   Verwende die automatische Beschränkungsfunktion, um die Anzahl der Beschränkungen zu begrenzen, die Sie manuell hinzufügen müssen.
-   Wende in der Regel zuerst geometrische und dann maßliche Beschränkungen an und sperre sie am Ende Deiner Skizze. Aber denke daran   * Regeln sind dazu da, gebrochen zu werden. Wenn Probleme beim Bearbeiten Deiner Skizze auftreten, kann es hilfreich sein, zuerst einige Objekte einzuschränken, bevor Dein Profil vervollständigt wird.
-   Wenn möglich, zentriere Deine Skizze auf den Ursprung (0,0) mit der Sperr Beschränkung. Wenn Deine Skizze nicht symmetrisch ist, suche einen ihrer Punkte zum Ursprung oder wähle schöne runde Zahlen für die Verriegelungsabstände. Externe Beschränkungen (Beschränken der Skizze auf vorhandene 3D-Geometrie wie Kanten oder andere Skizzen) sind in v0.12 nicht implementiert. Dies bedeutet, dass die Abstände zur ersten Skizze manuell festgelegt werden müssen, um die Geometrie der folgenden Skizzen zur ersten Skizze festzulegen. Eine Sperrbeschränkung von (25,75) vom Ursprung kann man sich leichter merken als (23.47,73.02).
-   Wenn man die Möglichkeit hat, zwischen der Längenbeschränkung und der horizontalen oder vertikalen Abstandsbeschränkung zu wählen, bevorzuge die Letztere. Horizontale und vertikale Abstandsbeschränkungen sind rechentechnisch billiger.
-   Im Allgemeinen sind die besten Beschränkungen zur Verwendung   * Horizontale und vertikale Beschränkungen; Horizontale und vertikale Längenbeschränkungen; Punkt-zu-Punkt Tangentialität. Wenn möglich, begrenze die Verwendung der folgenden   * der allgemeinen Längenbeschränkung; Tangentialität von Kante zu Kante; Fixpunkt auf einer Linienbeschränkung; Symmetriebeschränkung.
-   Wenn Zweifel an der Gültigkeit einer Skizze bestehen, nachdem diese vollständig ist (Merkmale werden grün), schließe das Skizzierer Dialogfeld, wechsle zum <img alt="" src=images/Workbench_Part.svg  style="width   *24px;"> [ Arbeitbereich Part](Part_Workbench/de.md) und führe das <img alt="" src=images/Part_CheckGeometry.svg  style="width   *16px;"> [Geometrie prüfen](Part_CheckGeometry/de.md) aus.


</div>

## Tutorien


<div class="mw-translate-fuzzy">

-   [Sketcher tutorial](https   *//forum.freecadweb.org/viewtopic.php?f=36&t=30104) von chrisb. Dies ist ein 70 Seiten langes PDF Dokument, das als ausführliches Handbuch für den Skizzierers dient. Die Grundlagen zur Verwendung des Skizzierers werden erläutert und sie geht in zahlreiche Details zur Erstellung geometrischer Formen sowie zu den einzelnen Beschränkungen hinein.
-   [Basistutorium Skizzierer](Basic_Sketcher_Tutorial/de.md) für Anfänger
-   [Skizzierer Mikro Tutorial - Beschränkungspraxis](Sketcher_Micro_Tutorial_-_Constraint_Practices/de.md)
-   [Skizzierer Anforderungen an Skizzen](Sketcher_requirement_for_a_sketch/de.md) Mindestanforderung für eine Skizze und vollständige Festlegung einer Skizze


</div>

## Skripten

Die Seite [Sketcher Skripten](Sketcher_scripting/de.md) enthält Beispiele für die Erstellung von Randbedingungen aus Python-Skripten.





{{Sketcher_Tools_navi

}} 

[Category   *Workbenches](Category_Workbenches.md)



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Workbenches](Category_Workbenches.md) > Sketcher Workbench/de
