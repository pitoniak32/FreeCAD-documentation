---
- GuiCommand   */de
   Name   *Sketcher CreateBSpline
   Name/de   *Sketcher B-SplineErstellen
   MenuLocation   *Sketch → Skizzengeometrien → B-Spline erstellen
   Workbenches   *[Sketcher](Sketcher_Workbench/de.md)
   Shortcut   ***G** **B** **B**
   Version   *0.17
   SeeAlso   *[Sketcher GeschlossenenB-SplineErstellen](Sketcher_CreatePeriodicBSpline/de.md)
---

# Sketcher CreateBSpline/de

## Beschreibung

Dieses Werkzeug erstellt eine offene B-Spline-Kurve aus ihren Kontrollpunkten. (Siehe [diese Seite](B-Splines/de.md) für weitere Informationen über B-Splines).

![](images/Sketcher_B-spline_example01.png ) 
*Eine B-Spline-Kurve (in weiß), definiert durch 4 Kontrollpunkte. Abgebildet sind das Kontrollpolygon in Grün (die Geraden, die die Kontrollpunkte verbinden) und die Gewichtskreise in Dunkelgelb. Die grüne Ziffer "3" in der Mitte bezieht sich auf den [Grad](Sketcher_BSplineIncreaseDegree/de#Beschreibung.md) des B-Splines und die Ziffern "(4)" an den Endpunkten des B-Splines beziehen sich auf deren [Knotenvielfachheit](Sketcher_BSplineDecreaseKnotMultiplicity/de#Beschreibung.md). Die rote Ziffer "3" steht für das Kontrollpunktgewicht, das über die Radiusbedingung am Kontrollpunktkreis definiert ist.*

## Anwendung


<div class="mw-translate-fuzzy">

1.  Drücke die **[<img src=images/Sketcher_CreateBSpline.svg style="width   *16px"> [B-spline erstellen](Sketcher_CreateBSpline/de.md)** Taste.
2.  Erstelle eine Reihe von Punkten, durch anklicken in der 3D Ansicht. Während der Befehl aktiv ist, werden die erzeugten Punkte mit geraden Linien verbunden, und es wird ein Konstruktionskreis erstellt, der auf jeden Punkt zentriert ist.
3.  Klicke mit der rechten Maustaste, um die Eingabe zu beenden und die Kurve zu erzeugen.
4.  Abhängig von den Einstellungen kann das Werkzeug aktiv bleiben, um eine neue Kurve zu verfolgen. Klicke erneut mit der rechten Maustaste, um den Befehl zu beenden.

-   Es ist möglich, das Gewicht der Kontrollpunkte zu definieren, indem man die Radien der Gewichtskreise ändert. Die Gleichheitsbeschränkungen für die Kreise müssen zuerst gelöscht werden. Die Radiusbeschränkung ist willkürlich, das Gewicht der Kontrollpunkte wird durch die relativen Radien der Kreise definiert. Es funktioniert ähnlich wie die Schwerkraft   * Je größer ein Kreis im Verhältnis zu den anderen ist, desto mehr wird die Kurve zum Kontrollpunkt gezogen.
-   Die Sichtbarkeit des Kontrollpolygons, des Krümmungskamms, des Grades und der Knotenvielfalt kann über die Symbolleiste [B-Spline Werkzeuge](Sketcher_Workbench/de#Skizzierer_B-Spline_Werkzeuge.md) ein- und ausgeschaltet werden.
-   Schaue Dir die anderen Werkzeuge in der Werkzeugleiste von [B-Spline Werkzeuge](Sketcher_Workbench/de#Skizze_B-spline_Werkzeuge.md) an, für weitere B-Spline-Bearbeitungswerkzeuge.


</div>

## Begrenzungen


<div class="mw-translate-fuzzy">

-   Viele Arten von Beschränkungen werden derzeit nicht unterstützt. Nur der Kontrollpunkt und die Endpunkte des B-Splines können beschränkt werden.
-   [Trimming](Sketcher_Trimming/de.md) und [extend](Sketcher_Extend/de.md) Werkzeuge werden nicht unterstützt.
-   Die Form einer B-Splinekurve kann nur durch Ziehen eines der Kontrollpunkte bearbeitet werden. Die auf der Kurve liegenden Knoten können nicht ausgewählt werden.


</div>





{{Sketcher_Tools_navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Sketcher](Sketcher_Workbench.md) > Sketcher CreateBSpline/de
