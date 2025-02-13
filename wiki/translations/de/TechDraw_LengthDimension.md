---
- GuiCommand   */de
   Name   *TechDraw Dimension Length
   Name/de   *TechDraw Längenmaß
   MenuLocation   *TechDraw → Bemaßungen → Längenmaß einfügen
   Workbenches   *[TechDraw](TechDraw_Workbench/de.md)
   SeeAlso   *[TechDraw MaßHorizontal](TechDraw_HorizontalDimension/de.md), [TechDraw MaßVertikal](TechDraw_VerticalDimension/de.md)
---

# TechDraw LengthDimension/de

## Beschreibung

Das Werkzeug <img alt="" src=images/TechDraw_LengthDimension.svg  style="width   *24px;"> **TechDraw Längenmaß** fügt einer Ansicht ein lineares Maß hinzu. Das Längenmaß kann der Abstand zwischen zwei Eckpunkten, die Länge einer Kante oder der Abstand zwischen zwei Kanten sein. Der Abstand ist zuerst der projizierte Abstand (wie in der Zeichnung dargestellt), kann aber unter Verwendung des Werkzeugs **<img src="images/TechDraw_LinkDimension.svg" width=16px> [MaßVerknüpfen](TechDraw_LinkDimension/de.md)** auf den eigentlichen 3D-Abstand geändert werden.

<img alt="" src=images/TechDraw_Dimension_Length_example.png  style="width   *220px;"> 
*Längenbemaßung zweier beliebiger Knoten der Ansicht*

## Anwendung

1.  Die Punkte oder die Kante auswählen, die die Messung definieren.
2.  Es gibt verschiedene Möglichkeiten das Werkzeug aufzurufen   *
    -   Die Schaltfläche **<img src="images/TechDraw_LengthDimension.svg" width=16px> [Längenmaß einfügen](TechDraw_LengthDimension/de.md)** drücken.
    -   Den Menüeintrag **TechDraw → <img src="images/TechDraw_LengthDimension.svg" width=16px> Längenmaß einfügen** auswählen.
3.  Ein Maß wird der Ansicht hinzugefügt. Das Maß kann an die gewünschte Position gezogen werden.
4.  Falls erforderlich, können Toleranzen, wie auf der [GD&T-Seite](TechDraw_Geometric_dimensioning_and_tolerancing/de#Toleranzen.md) beschrieben, hinzugefügt werden.

Um die Eigenschaften eines Bemaßungsobjekts zu ändern, doppel-klicke sie entweder in der Zeichnung oder in der [Baumansicht](Tree_view/de.md). Dadurch wird der Bemaßungsdialog geöffnet.

## Bemaßungsdialog

Der Bemaßungsdialog bietet die folgenden Einstellungen   *

![](images/TechDraw_DimensionDialog.png )

### Tolerierung

-   **Theoretisch genau**   * Wenn diese Option aktiviert ist, wird das Maß als theoretisch genaues Maß angegeben. Als solches darf es keine Toleranzen aufweisen. Das Maß wird durch einen Rahmen um den Wert dargestellt   * <img alt="" src=images/TechDraw_theoretically_exact.png  style="width   *100px;">

-   **Gleiche Toleranz**   * Falls aktiviert, sind Über- und Untertoleranz gleich und der negierte Wert der Übertoleranz wird als Untertoleranz benutzt. Die Anzeige zeigt <img alt="" src=images/TechDraw_equal-tolerance.png  style="width   *100px;">, anderenfalls <img alt="" src=images/TechDraw_Non-equal-tolerance.png  style="width   *80px;">.

-   **Übertoleranz**   * Der Wert, um den die Abmessung größer sein kann.

-   **Untertoleranz**   * Der Wert, um den die Abmessung kleiner sein kann.

### Formatierung


<div class="mw-translate-fuzzy">

-   **Formatspezifizierer**   * Wie die Maßzahl formatiert werden soll. Standardspezifizierer ist {{Value|%.xf}}, wobei {{Value|x}} die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax findet man unter [printf format string](https   *//en.wikipedia.org/wiki/Printf_format_string) (engl.). Es gibt noch ein zusätzliches {{Value|%w}} Format, das die festgelegte Anzahl von Ziffern nach dem Dezimaltrennzeichen ausgibt und die am Ende stehenden Nullen entfernt. Zum Beispiel heißt {{Value|%.2w}}, dass höchstens 2 Dezimalstellen ausgegeben und alle Nullen am Ende abgeschnitten werden.


</div>

-   **Beliebiger Text**   * Falls aktiviert, wird die Bemaßung durch den Inhalt des **Formatspezifizierer**-Feldes ersetzt.


<div class="mw-translate-fuzzy">

-   **Formatspezifizierer für das obere Abmaß**   * Wie das obere Abmaß formatiert werden soll. Standardspezifizierer ist {{Value|%.xf}}, wobei {{Value|x}} die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax findet man unter [printf format string](https   *//en.wikipedia.org/wiki/Printf_format_string) (engl.).


</div>


<div class="mw-translate-fuzzy">

-   **Formatspezifizierer für das untere Abmaß**   * Wie das untere Abmaß formatiert werden soll. Standardspezifizierer ist {{Value|%.xf}}, wobei {{Value|x}} die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax findet man unter [printf format string](https   *//en.wikipedia.org/wiki/Printf_format_string) (engl.).


</div>

-   **Beliebiger Toleranztext**   * Falls aktiviert, werden die Toleranzen durch den Inhalt der **Übertoleranz Formatspezifizierer**- und **Untertoleranz Formatspezifizierer**-Felder ersetzt.

### Anzeigeformat

-   **Maßpfeile umdrehen**   * Dreht die Richtung um, in die die Bemaßungspfeile zeigen. Als Vorgabe sind sie innerhalb der/des Bemaßungslinie/-bogens und zeigen nach außen.

-   **Farbe**   * Die Farbe für Linien und Texte.

-   **Schrifthöhe**   * Die Größe des Bemaßungstextes.

-   **Zeichnungsstil**   * Gibt den Standard (und dessen Stil) an, nach dem die Bemaßung gezeichnet wird. Siehe die Eigenschaft [**Standard und Stil**](#View.md) für Einzelheiten.

### Linien

-   **Winkel überschreiben**   * Wenn angehakt, werden die gewöhnlichen Winkel für Maßlinie und Maßhilfslinie durch die angegebenen Werte überschrieben.

-   **Maßlinienwinkel**   * Vorgabewert für den Winkel zwischen Maßlinie und der X-Achse der Ansich (in Grad).

-   **Standardwert verwenden**   * Setzt den Maßlinienwinkel auf den üblichen Winkel.

-   **Auswahl verwenden**   * Setzt den Maßlinienwinkel entsprechend dem Winkel der ausgewählten Kante (oder der 2 Knotenpunkte) in der Ansicht.

-   **Maßhilfslinienwinkel**   * Vorgabewert für den Winkel zwischen Maßhilfslinie und der X-Achse der Ansicht (in Grad).

-   **Standardwert verwenden**   * Setzt den Maßhilfslinienwinkel auf den üblichen Winkel.

-   **Auswahl verwenden**   * Setzt den Maßhilfslinienwinkel entsprechend dem Winkel der ausgewählten Kante (oder der 2 Knotenpunkte) in der Ansicht.

## Eigenschaften

### Daten


{{Properties_Title/de|Basis}}


<div class="mw-translate-fuzzy">

-    {{PropertyData/de|X}}   * Horizontale Position des Maßtexts relativ zur Ansicht.

-    {{PropertyData/de|Y}}   * Vertikale Position des Maßtexts relativ zur Ansicht.

-    {{PropertyData/de|Typ}}   * Länge, Radius, Durchmesser usw. Wird normalerweise vom Endanwender nicht geändert.

-    {{PropertyData/de|MessungsTyp}}   * Wie die Messung durchgeführt wird. Wird normalerweise nicht direkt durch den Endbenutzer geändert.

   *   

       *   True - basierend auf 3D-Geometrie
       *   Projected - basierend auf der Zeichung

-    {{PropertyData/de|TheoretischExakt}}   * Gibt ein theoretisch genaues (oder grundlegende) Maß an.

   *   

       *   
        `False`
        
        \- standardmäßig ein normales Maß, eventuell mit Toleranzen.

       *   
        `True`
        
        \- ein theoretischer Wert. Als solcher darf er keine Toleranzen aufweisen. Der Wert ist durch einen Rahmen um den Wert gekennzeichnet.

-    {{PropertyData/de|GleicheToleranz}}   * Falls oberes und unteres Abmaß gleich sind. Dann wird der negative Wert des oberen Abmaßes als unteres Abmaß benutzt

   *   

       *   
        `True`
        
        \- der negierte Wert von {{PropertyData/de|ObereToleranz}} wird als {{PropertyData/de|UntereToleranz}} benutzt. Die Anzeige zeigt <img alt="" src=images/TechDraw_equal-tolerance.png  style="width   *100px;">

       *   
        `False`
        
        \- der Wert von {{PropertyData/de|UntereToleranz}} wird benutzt. Die Anzeige zeigt <img alt="" src=images/TechDraw_Non-equal-tolerance.png  style="width   *80px;">

-    {{PropertyData/de|ObereToleranz}}   * Der Betrag, um den das Maß größer sein darf.

-    {{PropertyData/de|UntereToleranz}}   * Der Betrag, um den das Maß kleiner sein darf.

-    {{PropertyData/de|Umgekehrt}}   * Hebt hervor, ob das Maß einen üblichen oder einen invertierten Wert darstellt.

   *   

       *   
        `False`
        
        \- der gewöhnliche Wert wird verwendet. Für Länge ist es eine positive Zahl, für Winkel der schräggestellte Wert (0° - 180°).

       *   
        `True`
        
        \- der umgekehrte Wert wird verwendet. Für Länge eine negative Zahl, für Winkel der Reflexwert (180° - 360°).


</div>


{{Properties_Title/de|Format}}


<div class="mw-translate-fuzzy">

-    {{PropertyData/de|FormatAngabe}}   * Wie die Bemaßung formatiert sein wird. Siehe [Formatierung](#Formatierung.md).

-    {{PropertyData/de|FormatAngabeObereToleranz}}   * Wie {{PropertyData/de|FormatAngabe}}, aber für obere Abmaße.

-    {{PropertyData/de|FormatAngabeUntereToleranz}}   * Wie {{PropertyData/de|FormatAngabe}}, aber für untere Abmaße.

-    {{PropertyData/de|frei wählbar}}   * Gibt an, ob **FormatAngabe** als Vorlage oder als aktueller Text behandelt werden soll.

   *   

       *   
        `False`
        
        \- der Inhalt von **Format Spec** wird zur Formatierung der Maßzahl verwendet.

       *   
        `True`
        
        \- der Inhalt von **Format Spec** wird anstatt der Maßzahl als Text angezeigt.

-    {{PropertyData/de|frei wählbare Toleranzen}}   * Wie {{PropertyData/de|frei wählbar}}, aber für die Toleranz.

   *   

       *   
        `False`
        
        \- the content of the **Format Spec** is used to format the actual dimensional value.

       *   
        `True`
        
        \- the content of the **Format Spec** will be displayed as text instead if the dimension value.

-    **Arbitrary Tolerances**   * Like **Arbitrary**, but for the tolerance.


</div>


{{Properties_Title/de|Override}}


<div class="mw-translate-fuzzy">

-    {{PropertyData/de|AngleOverride}}   * Ob die Richtung der Maßlinien und Maßhilfslinien überschrieben wird.

   *   

       *   
        `False`
        
        \- die Richtungen werden wie üblich berechnet.

       *   
        `True`
        
        \- die Richtungen werden mit den Werten der Eigenschaften LineAngle und ExtensionAngle überschrieben.

-    {{PropertyData/de|LineAngle}}   * Winkel zwischen Maßlinie und der X-Achse der Ansicht (in Grad).

-    {{PropertyData/de|ExtensionAngle}}   * Winkel zwischen Maßlinie(n) und der X-Achse der Ansicht (in Grad).


</div>

### Ansicht


{{Properties_Title/de|Basis}}


<div class="mw-translate-fuzzy">

-    {{PropertyView/de|Sichtbarkeit}}   * Setzt, ob das Maß sichtbar ist. `True` - sichtbar, `False` - versteckt.


{{Properties_Title/de|Dim Format}}

-    {{PropertyView/de|Schriftart}}   * Der Name der Schriftart, die für den Maßtext verwendet werden soll.

-    {{PropertyView/de|Schriftgröße}}   * Höhe des Maßtextes.

-    {{PropertyView/de|Linienbreite}}   * Maßlinienstärke.

-    {{PropertyView/de|Farbe}}   * Farbe für Linien und Text.

-    {{PropertyView/de|Standard und Stil}}   * Gibt die Norm (und deren Ausführungsart) an, nach der die Bemaßung gezeichnet wird   *

<img alt="Unterschiede zwischen den unterstützten Standards" src=images/TechDraw_Dimension_standardization.png  style="width   *500px;">

   *   

       *   ISO Orientiert - gezeichnet gemäß Standard ISO 129-1, Text wird so gedreht, dass er parallel zur Tangente der Maßlinie liegt.
       *   ISO Referenzierung - gezeichnet in Übereinstimmung mit ISO 129-1, der Text ist immer horizontal, über der kürzest möglichen Referenzlinie.
       *   ASME Innenliegend - gezeichnet gemäß Standard ASME Y14.5M, der Text ist horizontal, in einem Ausbruch innerhalb der Maßlinie oder des Bogens eingefügt.
       *   ASME Referenzierung - gezeichnet in Übereinstimmung mit ASME Y14.5M, der Text ist horizontal, eine kurze Referenzlinie ist an der vertikalen Mitte einer Seite angebracht.

-    {{PropertyView/de|Rendering Extent}}   * Eher universelle Eigenschaft, die angibt, wie viel Platz die Maßzeichnung einnehmen darf   *

   *   

       *   None - es werden keine Linien oder Pfeile gezeichnet, sondern nur die nackte Maßzahl angezeigt.
       *   Minimal - für Längen und Winkel wird eine einzelne Kopflinie gezeichnet, die die Maßzahl mit der *virtuellen Verlängerungslinie* des Endpunktes verbindet. Die Verlängerungslinie selbst wird nicht hinzugefügt.
       *   Durchmesser werden nach Begrenzt Umfang, Radien nach Reduziert Umfang gerendert.
       *   Eingegrenzt - für Längen und Winkel wird eine doppelte Linie (oder ein Bogen) gezeichnet, die die *virtuellen Verlängerungslinien* des Start- und Endpunktes verbindet, wobei die Verlängerungslinien selbst nicht hinzugefügt werden.
       *   Durchmesser werden mit einer minimalen einteiligen Linie vom Bemaßungswert zum nächsten Punkt auf dem Kreis gezeichnet, Radien wie bei ReduziertUmfang.
       *   Normal - der Standardwert. Für Längen und Winkel wird eine doppelseitige Linie (oder ein Bogen) gezeichnet, die die *Verlängerungslinien* des Start- und Endpunktes verbindet, die Verlängerungslinien selbst ebenfalls.
       *   Durchmesser werden als doppelseitige Linien gezeichnet, die den Mittelpunkt treffen und den nächsten und den entferntesten Punkt auf dem Kreis verbinden.
       *   Radien werden als einseitige Linie vom Mittelpunkt zum nächsten Kreisbogenpunkt gezeichnet.
       *   Erweitert - Nur Durchmesser unterstützen diesen Wert, so dass sie horizontal oder vertikal längenähnlich dargestellt werden. Andere Maßtypen werden wie bei Normal Ausdehnung dargestellt.

-    {{PropertyView/de|Pfeilspitzen kippen}}   * Standardmäßig bedeutet der Wert *innerhalb* der Maßlinie/des Bogens die Pfeile, die *nach außen* zeigen. Wird der Wert *außerhalb* der Maßlinie/des Bogens platziert, zeigen die Pfeile der Maßlinie/des Bogens *nach innen*.

   *   

       *   
        `False`
        
        \- Wählt die Richtung der Pfeile automatisch nach der obigen Regel aus.

       *   
        `True`
        
        \- Außer Kraft setzen der automatisch gewählten Richtung und erzwingen der entgegengesetzten Richtung.


</div>

## Begrenzungen

Dimension-Objekte (Maße) sind anfällig für das \"[Topological-Naming-Problem](topological_naming_problem/de.md)\" (Problem der topologischen Benennung). Das bedeutet, dass bei einer Änderung der 3D Geometrie die Flächen und Kanten des Modells intern umbenannt werden können; wenn ein Maß an eine Kante angehängt wird, die dann geändert wird, kann das Maß brechen. Im Allgemeinen ist es nicht möglich, die projizierten 2D-Bemaßungen mit den tatsächlichen 3D-Objekten synchronisiert zu halten.

Es wird daher empfohlen, Bemaßungen hinzuzufügen, wenn das 3D Modell nicht mehr verändert wird.

### Zwischenlösung

Wenn du eine TechDraw Ansicht mit Bemaßungen behalten möchtest, die nicht brechen, musst du ein Objekt bemaßen, das sich nicht ändert.

-   Wähle das zu projizierende Objekt aus, wechsle dann zur <img alt="" src=images/Workbench_Part.svg  style="width   *24px;"> [Part Arbeitsbereich](Part_Workbench/de.md) und verwende {{MenuCommand/de|Part → <img src="images/Part_SimpleCopy.svg" width=16px> [Einfache Kopie erstellen](Part_SimpleCopy.md)}}. Dadurch wird ein einzelnes Objekt erzeugt, das nicht parametrisch ist, d.h. nicht mehr bearbeitet werden kann.
-   Wähle diese Kopie aus, verwende dann [TechDraw Ansicht](TechDraw_View/de.md) und füge die gewünschten Bemaßungen hinzu.
-   Wenn das ursprüngliche 3D Modell geändert wird, wirken sich die Änderungen weder auf die einfache Kopie noch auf die Bemaßungen in der TechDraw Ansicht aus.

Siehe [Leitbemaßungen](TechDraw_LandmarkDimension/de.md) für einen weiteren Ansatz zur Umgehung des Problems der topologischen Benennung.

## Skripten


**Siehe auch   ***

[TechDraw API](TechDraw_API/de.md) und [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics/de.md).

Das Werkzeug Längenmaß kann in [Makros](Macros/de.md) und von der [Python](Python/de.md)-Konsole aus mit den folgenden Funktionen verwendet werden   *


```python
dim1 = FreeCAD.ActiveDocument.addObject('TechDraw   *   *DrawViewDimension','Dimension')
dim1.Type = "Distance"
dim1.References2D=[(view1, 'Edge1')]
rc = page.addView(dim1)
```

## Anmerkungen


<div class="mw-translate-fuzzy">

-   **Kantenauswahl**. Die Auswahl von Kanten kann schwierig sein. Du kannst den Auswahlbereich für Kanten mit dem Parameter \"/Mod/TechDraw/General/EdgeFuzz\" anpassen (siehe [Std_DlgParameter](Std_DlgParameter.md)). Dies ist eine dimensionslose Zahl. Die Voreinstellung ist 10.0. Werte im Bereich von 20-30 erleichtern die Auswahl von Kanten spürbar. Große Zahlen führen zu Überlappungen mit anderen Zeichnungselementen.
-   **Nachkommastellen**. Bei Bemaßungen wird standardmäßig die globale Einstellung der Dezimalstellen verwendet. Diese kann über [Einstellungen](TechDraw_Preferences#Dimensions/de.md) oder durch Ändern der FormatSpec Eigenschaft geändert werden.
-   **Mehrfache Objekte**\'. Ansichten können mehrere 3D Objekte als Quelle enthalten. Bemaßungen können auf die Geometrie von jedem Objekt in der Ansicht angewendet werden (z.B. von Objekt1.Vertex0 bis Objekt2.Vertex3).


</div>





{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw LengthDimension/de
