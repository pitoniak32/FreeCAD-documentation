# Placement/de
## Overview


<div class="mw-translate-fuzzy">

## Übersicht

**Positionierung** ist wie FreeCAD den Standort und die Lage (Orientierung) eines Objekts im Raum angibt. Die Platzierung kann in verschiedenen Formen angegeben und über [Skripten](Python_scripting_tutorial/de#Vektoren_und_Positierungen.md), den [Eigenschaftseditor](Property_editor/de.md) oder durch Auswahl von **Bearbeiten → Positionierung...** zum Öffnen des [Positionierung Aufgabenpaneel](Std_Placement/de.md) verändert werden.

### Zugriff auf das Positionierungsattribut 

Auf die Positionierungsattribute eines Objekts kann auf 3 Arten zugegriffen und diese verändert werden   *


</div>

### Accessing the Placement Attribute 

An object\'s Placement attributes can be accessed and modified in 3 ways   *

![Positionierung im Eigenschaftenpaneel](images/PlacementPropertiesv10-800x800.png ) 

![Skriptpositionierung als y/p/r und Matrix und seine [API](images/Placement_API/de.md).](PlacePyConv10.png ) 

![Positionierung Aufgabenpaneel](images/PlacementDialogv10.png ) 

## Forms of Placement 


<div class="mw-translate-fuzzy">

## Formen der Positionierung 

Die Positionierung wird intern als eine Position und eine Drehung (Drehachse und Winkel in ein Quaternion umgewandelt [Quaternionen und räumliche Rotation](https   *//en.wikipedia.org/wiki/Quaternions_and_spatial_rotation), [Quaternionen](https   *//de.wikipedia.org/wiki/Quaternion)) gespeichert. Während es mehrere Formen gibt, um eine Drehung festzulegen, z.B. mit einem Rotationszentrum, wird dies nur zur Beeinflussung der Drehungsberechnung verwendet und nicht für spätere Operationen gespeichert. Wenn eine Drehachse von (1,1,1,1) angegeben ist, kann sie ebenfalls normalisiert werden, wenn sie im Quaternion gespeichert ist und als (0.58, 0.58, 0.58, 0.58, 0.58) erscheinen, wenn das Objekt später durchsucht wird.


</div>

### Angle, Axis and Position 


<div class="mw-translate-fuzzy">

### Winkel, Achse und Position 

**Positionierung = \[Winkel, Achse, Position\]**


</div>


<div class="mw-translate-fuzzy">

Die erste Form von **Positionierung** legt die Lage eines Objekts im Raum mit einer Position fest und beschreibt seine Orientierung als eine einzelne Drehung um eine Achse.

**Winkel = r** ist ein Skalar, der den Betrag der Drehung des Objekts um **Achse** angibt. Wird als Grad eingegeben, aber intern als Bogenmaß gespeichert.


</div>

**Angle = r** is a scalar indicating the amount of rotation of the object about **Axis**. Entered as degrees, but stored internally as radians.


<div class="mw-translate-fuzzy">

**Achse = (ax,ay,az)** ist ein Vektor, der eine Drehachse beschreibt (siehe Hinweis zur Drehachse). Beispiele sind   *

   (1,0,0) ==> um die **X** Achse
   (0,1,0) ==> um die **Y** Achse
   (0,0,1) ==> um die **Z** Achse
   (0.71,0.71,0) ==> um die Linie **y=x**


</div>

   (1,0,0)       ==> about **X** axis
   (0,1,0)       ==> about **Y** axis
   (0,0,1)       ==> about **Z** axis
   (0.71,0.71,0) ==> about the line **y=x**


<div class="mw-translate-fuzzy">

Beachte, dass es auch möglich ist, ein Objekt entlang dieser Drehachse (Axialbewegung) zu verschieben (bewegen), indem du den Bewegungsabstand im {{SpinBox|Axial   * 0.0mm}}-Drehfeld eingibst und auf die Schaltfläche **Apply axial** klickst. (Eine Möglichkeit, sich eine axiale Bewegung vorzustellen, ist, an ein Flugzeug zu denken, bei dem sich ein Propeller auf der Nase dreht - der Propeller dreht sich um eine Drehachse, während sich das Flugzeug entlang derselben Achse bewegt.) Die Werte im Vektor können als die relative Bewegungsgröße betrachtet werden, die in dieser Richtung angewendet wird. So wird beispielsweise im Fall y=x (0.71,0.71,71,0) der in der Axialspinbox enthaltene Wert gleichermaßen auf die X- und Y-Richtung angewendet, aber es findet keine Bewegung in der Z-Richtung statt.

**Position = (x,y,z)** ist ein Vektor, der den Punkt beschreibt, von dem aus die Geometrie des Objekts berechnet wird (tatsächlich ein \"lokaler Ursprung\" für das Objekt). Beachte, dass in Skripten Placement.Base verwendet wird, zur Bezeichnung der Positionskomponente einer Positionierung. Der Eigenschaftseditor ruft diesen Wert \"Position\" und der Positionierungsdialog nennt ihn \"Translation\".


</div>

**Position = (x,y,z)** is a Vector describing the point from which the object\'s geometry will be calculated (in effect, a \"local origin\" for the object). Note that in scripts, Placement.Base is used to denote the Position component of a placement. The property editor calls this value **Position** and the Placement task panel calls it **Translation**.

### Position and Yaw, Pitch and Roll 


<div class="mw-translate-fuzzy">

### Position und Gieren, Neigen und Rollen 

![Positionierung Aufgabenpaneel   * {{ComboBox|Euler Winkel}} ausgewählt](images/PlacementDialogv10b.png )  **Positionierung = \[Position, Gieren-Neigen-Rollen\]**


</div>

**Placement = \[Position, Yaw-Pitch-Roll\]**


<div class="mw-translate-fuzzy">

Die zweite Form der **Positionierung** legt die Lage eines Objekts im Raum mit einer **Position** (wie in der ersten Form) fest, beschreibt aber seine Ausrichtung mit den Winkeln Gieren, Neigen und Rollen ([Gier, Neigen, Roll Winkel](http   *//en.wikipedia.org/wiki/Yaw,_pitch,_and_roll)). Diese Winkel werden manchmal als Euler Winkel oder Tait-Bryan Winkel bezeichnet ([Euler-Winkel](https   *//de.wikipedia.org/wiki/Eulersche_Winkel)). Gieren, Neigen und Rollen sind gängige Luftfahrtbegriffe für die Orientierung (oder Haltung) eines Körpers.


</div>

**Position = (x,y,z)** ist ein Vektor, der den Punkt beschreibt, von dem aus die Geometrie des Objekts berechnet wird (in Wirklichkeit ein \"lokaler Ursprung\" für das Objekt).


<div class="mw-translate-fuzzy">

**Yaw-Pitch-Roll = (y,p,r)** ist ein Tupel, das die Position des Objekts angibt. Die Werte für y,p,r geben den Grad der Drehung um jede der z,y,x-Achsen an (siehe Hinweis).  {{Code|code|code=
>>> App.getDocument("Name_des_Dokuments").Cylinder.Placement=App.Placement(App.Vector(0,0,0,0), App.Rotation(10,20,30), App.Vector(0,0,0))
}}


</div>


```python
>>> App.ActiveDocument.Cylinder.Placement = App.Placement(App.Vector(0,0,0), App.Rotation(10,20,30), App.Vector(0,0,0))
```

App.Rotation(10,20,30) = Euler Winkel

**Gieren** = 10 Grad (**Z**)

**Neigung** = 20 Grad (**Y**)

**Rollen** = 30 Grad (**X**)

![](images/Tache_Placement_Lacet_fr_Mini.gif )**Yaw** ist die Drehung um die **Z-Achse**, d.h. eine Drehung von links nach rechts.
(Der Gierwinkel wird **Psi ψ** genannt). 

![](images/Tache_Placement_Tangage_fr_Mini.gif )**Pitch** ist die Rotation um die **Y Achse**, man kann sagen, die Nase hoch und runter.
(Der Neigungswinkel wird **Phi φ** genannt). 

![](images/Tache_Placement_Roulis_fr_Mini.gif )**Roll** ist die Rotation um die **X Achse**, man sagt über die Flügel rollen.
(Der Rollwinkel wird **Thêta θ** genannt). 

### Matrix


<div class="mw-translate-fuzzy">

### Matrix 

**Positionierung = Matrix**


</div>

Die dritte Form der **Positionierung** beschreibt die Position und Orientierung des Objektes mit einer 4 mal 4 Transformationsmatrix ([Affine Abbildung](https   *//de.wikipedia.org/wiki/Affine_Abbildung)).

**Matrix** =


<div class="mw-translate-fuzzy">

((r11,r12,r13,t1),

   (r21,r22,r23,t2),
   (r31,r32,r33,t3),
   (0,0,0,1)) , wobei rij die Rotation und ti die Verschiebung angibt. 





</div>

## The Placement Dialog 


<div class="mw-translate-fuzzy">

## Der Positionierungsdialog 

Der Positinierungsdialog wird über das Menü **Bearbeiten** aufgerufen. Er wird zum präzisen Drehen/Übersetzen von Objekten verwendet. Er wird auch verwendet, wenn wir eine Skizze auf einer \"Nicht Standard\" Ebene erstellen oder die Ausrichtung einer Skizze auf eine neue Ebene ändern müssen.

Der Abschnitt **Schiebung** passt die Position des Objekts im Raum an. Der Abschnitt **Mitte** passt die Rotationsachse an eine Achse an, die nicht durch den Referenzpunkt des Objekts verläuft. Der Abschnitt **Rotation** stellt den/die Rotationswinkel und die Methode zur Angabe dieser Winkel ein.


</div>

-   The **Translation** section adjusts the object\'s location in space.
-   The **Center** section adjusts the rotational axis to one that does not pass through the object\'s reference point.
-   The **Rotation** section adjusts the rotational angle(s) and the method of specifying those angles.


<div class="mw-translate-fuzzy">

Aber während die Elemente innerhalb jedes Abschnitts im Allgemeinen für den Zweck dieses Abschnitts gelten, gibt es auch einige Elemente in einem Abschnitt, die sich auf Elemente in einem anderen Abschnitt auswirken können. Wenn Sie beispielsweise im Abschnitt **Zentrum** mit 2 in der 3D-Ansicht ausgewählten Punkten auf die Schaltfläche \"Ausgewählte Punkte\" klicken, werden nicht nur die Koordinaten-Rotationsboxen **Zentrum** mit den Koordinaten des Zentrums zwischen diesen beiden ausgewählten Punkten gefüllt, sondern es wird auch eine benutzerdefinierte Achse entlang der Linie erstellt, die durch diese beiden ausgewählten Punkte im Abschnitt **Rotation** definiert ist. In einem anderen Beispiel wird durch Platzieren eines Wertes in der Axial-Rotationsbox und Klicken auf die Schaltfläche \"Übernehmen\" axial im Abschnitt **Verschieben** das Objekt entlang der im Abschnitt **Rotation** definierten Achse verschoben/bewegt.

Das Kontrollkästchen *\'Inkrementelle Änderungen an der Objektpositionierung anwenden* ist nützlich, wenn Drehungen/Verschiebungen relativ zur aktuellen Position/Höhe des Objekts und nicht zur ursprünglichen Position/Höhe vorgenommen werden sollen. Das Ankreuzen dieses Kästchens setzt die Dialogeingabefelder auf Null zurück, ändert aber nicht die Orientierung oder Lage des Objekts. Nachfolgende Eingaben ändern zwar die Orientierung/Lage, werden aber von der aktuellen Position des Objekts aus angewendet. Das Aktivieren dieses Kontrollkästchens ist auch bei der Verwendung der Schaltfläche \"Gewählte Punkte\" nützlich, da es manchmal unerwünschte Positionierungsänderungen verhindern kann.


</div>

The **Apply incremental changes to object placement** tick box is useful when translations/rotations are to be made relative the object\'s current position/attitude, rather than to the original position/attitude. Ticking this box resets the dialogue input fields to zero, but does not change the object\'s orientation or location. Subsequent entries do change the orientation/location, but are applied from the object\'s current position. Enabling this checkbox is also useful when using the Selected points button as it can sometimes prevent undesired placement changes.


<div class="mw-translate-fuzzy">

PS   * seit Version 0.17 wird das neue Objekt \"Part\" eingeführt. Dieses Objekt hat eine Positionierungsfunktion und das im Objekt \"Part\" erstellte Positionierungsobjekt wird mit der \"Part\" Positionierungsfunktion inkrementiert. <small>(v0.17)</small>  Mit dem folgenden Code erhält man das \"Part\" Positionierungsobjekt


</div>

To obtain the Part Placement use this code   *


```python
import Draft, Part
sel = FreeCADGui.Selection.getSelection()
print(sel[0].Placement)
print(sel[0].getGlobalPlacement())   # return the GlobalPlacement
print(sel[0].getParentGeoFeatureGroup()) # return the GeoFeatureGroup, ex   *  Body or a Part.
print("____________________")
```


<div class="mw-translate-fuzzy">

Die Schaltfläche **Ausgewählte Punkte** wird verwendet, um die Koordinaten in die Koordinaten-Rotationsboxen **Zentrum** einzutragen und, wenn 2 oder 3 Punkte ausgewählt sind, zusätzlich eine benutzerdefinierte Rotationsachse im Abschnitt **Rotation** zu erstellen. Ein Punkt kann ein Scheitelpunkt sein, aber er kann auch ein beliebiger Punkt entlang einer Kante oder auf einer Fläche sein. Wenn Sie eine Kante oder Fläche auswählen, wird die gesamte Kante oder Fläche ausgewählt, aber FreeCAD merkt sich auch, über welchen Punkt auf dieser Fläche oder Kante der Mauszeiger schwebte, als diese Kante oder Fläche ausgewählt wurde. Es sind die Koordinaten dieses Punktes, die im Positionierungsdialog verwendet werden, wenn die Schaltfläche **Ausgewählte Punkte** angeklickt wird. Dies ist keine präzise Art und Weise einen Punkt auszuwählen. Aber in vielen Fällen reicht es aus, dass sich der ausgewählte Punkt garantiert auf dieser Kante oder Fläche befindet. In Fällen, in denen ein zu verwendender Punkt genau bestimmt werden muss, sollten ein Scheitelpunkt gewählt werden. Wenn an der gewünschten Stelle kein Scheitelpunkt vorhanden ist, sollten einer erstellt werden, z.B. in einer temporären Skizze, die an diese Fläche oder Kante angehängt wird oder unter Verwendung eines \"Draft workbench\"-Objekts, wie z.B. einer Linie oder eines Punktes usw.


</div>


<div class="mw-translate-fuzzy">

Betrachten wir zunächst den einfachen Fall der Auswahl eines Punktes. Der Arbeitsablauf besteht darin, zunächst den gewünschten Punkt auszuwählen und dann auf die Schaltfläche **Ausgewählte Punkte** zu klicken. Die Koordinaten des ausgewählten Punktes werden verwendet, um die X-, Y- und Z-Rotationsboxen innerhalb des Abschnitts **Zentrum** zu füllen. Nun wird jede Drehung des Objekts um dieses Rotationszentrum durchgeführt.


</div>


<div class="mw-translate-fuzzy">

Betrachten wir nun den Fall der Auswahl von 2 Punkten. Nun würden 2 gewünschte Punkte ausgewählt und dann auf die Schaltfläche **Ausgewählte Punkte** geklickt werden. Die Koordinaten des Mittelpunktes zwischen den beiden ausgewählten Punkten werden in die X-, Y- und Z-Rotationsboxen innerhalb des Abschnitts **Zentrum** gelegt. Nun wird jede Drehung des Objekts um dieses Rotationszentrum erfolgen. Aber zusätzlich zum Einrichten der Koordinaten des Abschnitts **Zentrum** wird auch eine benutzerdefinierte Achse zum Element **Achse** innerhalb des Abschnitts **Rotation** hinzugefügt. **Hinweis   *** Wenn der Euler-Rotationsmodus aktiv war, wird der Modus auf Rotation mit einer Achse umgeschaltet und die neue benutzerdefinierte Achse wird als aktuelle Rotationsachse ausgewählt. Nun wird jede Rotation, die unter Verwendung der neuen benutzerdefinierten Achse durchgeführt wird, um diese Rotationsachse erfolgen. Als zusätzlicher Bonus wird der Abstand zwischen den beiden ausgewählten Punkten gemessen und diese Information wird in der Berichtsansicht angezeigt. **Hinweis   *** Bleibt die Umschalt-Taste gedrückt, während auf die Schaltfläche **Ausgewählte Punkte** geklickt wird, dann wird die Abstandsmessung in die Zwischenablage kopiert. Wird dieser Abstand in die Axial-Rotationsbox im Abschnitt **Verschieben** eingegeben und auf die Schaltfläche **Übernehmen axial** geklickt, dann wird das Objekt so verschoben, dass der erste ausgewählte Punkt nun die Koordinaten einnimmt, die der zweite ausgewählte Punkt zu dem Zeitpunkt hatte, als die Schaltfläche **Ausgewählte Punkte** angeklickt wurde.


</div>


<div class="mw-translate-fuzzy">

Betrachten wir nun den Fall der Auswahl von 3 Punkten. Nun würden 3 gewünschte Punkte ausgewählt und dann auf die Schaltfläche **Ausgewählte Punkte** geklickt werden. Die Koordinaten des ersten ausgewählten Punktes (die Reihenfolge der Auswahl ist hier sehr wichtig) werden in die X-, Y- und Z-Rotationsboxen innerhalb des Abschnitts **Zentrum** geschrieben. Da 3 Punkte eine Ebene definieren, ist FreeCAD in der Lage, diese 3 Punkte zu verwenden, um eine neue benutzerdefinierte Drehachse zu erstellen. Sie ist normal, senkrecht, zu dieser definierten Ebene. Wie bei 2 ausgewählten Punkten wird auch in der Berichtsansicht der Abstand zwischen den Punkten angezeigt. Aber diesmal ist es der Abstand zwischen dem 2. und 3. ausgewählten Punkt. **Hinweis   *** Bleibt die Umschalttaste gedrückt, während auf die Schaltfläche **Ausgewählte Punkte** geklickt wird, dann wird die Winkelmessung in die Zwischenablage kopiert. Zusätzlich wird auch der Winkel zwischen dem 2. und 3. Punkt gemessen und in der Berichtsansicht angezeigt. Durch Eingabe dieses Winkels in die Rotationsbox **Winkel** innerhalb des Abschnittes **Drehung** kann das Objekt genau gedreht werden, so dass jetzt der 2. ausgewählte Punkt zu den Koordinaten, die der 3. ausgewählte Punkt einnimmt, ausgerichtet ist. **Hinweis   *** die Anzahl der verwendeten Ziffern im Menü Bearbeiten -\> Voreinstellungen -\> Allgemein -\> Einheiten -\> Anzahl der Dezimalstellen kann erhöht werden, wenn die Präzision erhöht werden soll.


</div>

## Examples


<div class="mw-translate-fuzzy">

## Beispiele

Rotationen um eine einzelne Achse   *


</div>


<div class="mw-translate-fuzzy">

<img alt="Before Rotation" src=images/RotationAboutZBefore.png  style="width   *600px;"> Vor der Rotation (Draufsicht) 

<img alt="After Rotation about Z" src=images/RotationAboutZAfter.png  style="width   *600px;"> Nach der Rotation um Z (Draufsicht) 

<img alt="After Rotation about y=x" src=images/RotationAboutYXAfter.png  style="width   *600px;"> Nach der Rotation um y=x (Ansicht von rechts) 

Rotation mit versetztem Zentrum   *


</div>

<img alt="After Rotation about Z" src=images/RotationAboutZAfter.png  style="width   *600px;"> After Rotation about Z (top view) 

<img alt="After Rotation about y=x" src=images/RotationAboutYXAfter.png  style="width   *600px;"> After Rotation about y=x (right view) 

Rotation with offset centre point   *


<div class="mw-translate-fuzzy">

<img alt="Before Rotation" src=images/RotationOffsetBefore.png  style="width   *600px;"> Vor der Rotation (Draufsicht) 

<img alt="After Rotation about Z" src=images/RotationOffsetAfter.png  style="width   *600px;"> Nach der Rotation um Z (Draufsicht) 

Rotation mit Euler-Winkeln   *


</div>

<img alt="After Rotation about Z" src=images/RotationOffsetAfter.png  style="width   *600px;"> After Rotation about Z (top view) 

Rotation using Euler angles   *

<img alt="Before Rotation" src=images/RotationEulerBefore.png  style="width   *600px;"> Before Rotation 

<img alt="After Rotation" src=images/RotationEulerAfter.png  style="width   *600px;"> After Rotation 

## Placement.Base vs Shape Definition 


<div class="mw-translate-fuzzy">

<img alt="Before Rotation" src=images/RotationEulerBefore.png  style="width   *600px;"> Vor der Rotation 

<img alt="After Rotation" src=images/RotationEulerAfter.png  style="width   *600px;"> Nach der Rotation 

## Placement.Base verglichen mit Shape Definition 

Positionierung ist nicht der einzige Weg, eine Form im Raum zu positionieren. Siehe die Python Konsole in diesem Bild   *


</div>


<div class="mw-translate-fuzzy">

![2 Formen mit gleicher Positionierung](images/2Placements800.png )


</div>


<div class="mw-translate-fuzzy">

Beide Würfel haben den selben Wert zur Positionierung, befinden sich aber an verschiedenen Orten! Das geschieht, weil die beiden Formen durch unterschiedliche Knoten (Kurven in komplexeren Formen) bestimmt werden. Zu den beiden Formen in der Illustration oben   *


</div>

 >>> ev = App.ActiveDocument.Extrude.Shape.Vertexes
 >>> for v in ev   * print(v.X,",",v.Y,",",v.Z)
 ...
 30.0,30.0,0.0
 30.0,30.0,10.0
 40.0,30.0,0.0
 40.0,30.0,10.0
 40.0,40.0,0.0
 40.0,40.0,10.0
 30.0,40.0,0.0
 30.0,40.0,10.0
 >>> e1v = App.ActiveDocument.Extrude001.Shape.Vertexes
 >>> for v in e1v   * print(v.X,",",v.Y,",",v.Z)
 ...
 0.0,10.0,0.0
 0.0,10.0,10.0
 10.0,10.0,0.0
 10.0,10.0,10.0
 10.0,0.0,0.0
 10.0,0.0,10.0
 0.0,0.0,0.0
 0.0,0.0,10.0
 >>>

The Vertices (or Vectors) that define the shape use the Placement.Base attribute as their origin. So if you want to move a shape 10 units along the **X** axis, you could add 10 to the **X** coordinates of all the Vertices or you could set Placement.Base to (10,0,0).

## Using \"Center\" to Control Axis of Rotation 


<div class="mw-translate-fuzzy">

\>\>\> ev = App.ActiveDocument.Extrude.Shape.Vertexes

 >>> for v in ev   * print v.X,",",v.Y,",",v.Z
 ... 
 30.0,30.0,0.0
 30.0,30.0,10.0
 40.0,30.0,0.0
 40.0,30.0,10.0
 40.0,40.0,0.0
 40.0,40.0,10.0
 30.0,40.0,0.0
 30.0,40.0,10.0
 >>> e1v = App.ActiveDocument.Extrude001.Shape.Vertexes
 >>> for v in e1v   * print v.X,",",v.Y,",",v.Z
 ... 
 0.0,10.0,0.0
 0.0,10.0,10.0
 10.0,10.0,0.0
 10.0,10.0,10.0
 10.0,0.0,0.0
 10.0,0.0,10.0
 0.0,0.0,0.0
 0.0,0.0,10.0
 >>> 
 

Die Knoten (oder Vektoren), die die Form bestimmen verwenden das Placement.Base Attribut als deren Ursprung. Wenn du also eine Form um 10 Einheiten entlang der **X** Achse verschieben möchtest, könntest du 10 zu den **X** Koordinaten aller Knoten hinzufügen, oder du kannst Placement.Base zu (10,0,0) setzen.

## Verwendung von \"Mitte\" zur Steuerung der Rotationsachse 

Standardmäßig ist die Rotationsachse nicht wirklich die x/y/z Achse. Sie ist eine Linie, die parallel zur ausgewählten Achse verläuft, aber durch den Referenzpunkt (Placement.Base) des zu drehenden Objekts verläuft. Dies kann durch die Verwendung der Felder Zentrum im Dialogfeld Platzierung oder, in Skripten, durch Verwendung des Parameters Zentrum des Konstruktors FreeCAD.Placement geändert werden.


</div>


<div class="mw-translate-fuzzy">

Nehmen wir zum Beispiel an, wir haben einen Quader (unten), der auf (20,20,10) positioniert ist. ![Vor Drehung](images/LocalZBefore2.png ) Wir möchten den Quader um seine eigene vertikale Mittelachse (d.h. das lokale Z) drehen, wobei er die gleiche Position beibehält. Dies lässt sich leicht erreichen, indem wir einen Mittelpunktswert angeben, der den Koordinaten des Quadermittelpunkts (25,25,15) entspricht. ![Nach Drehung](images/LocalZAfter2.png )

In einem Skript würden wir das tun   *


</div>

![Before Rotation](images/LocalZBefore2.png ) 

We wish to spin the box around it\'s own vertical centre line (ie local Z), while keeping it the same position. We can easily achieve this by specifying a Center value equal to the coordinates of the box\'s central point (25,25,15).

![After Rotation](images/LocalZAfter2.png ) 

In a script, we would do   *


```python
import FreeCAD
obj = App.ActiveDocument.Box                       # our box
rot = FreeCAD.Rotation(FreeCAD.Vector(0,0,1),45)   # 45° about Z
#rot = FreeCAD.Rotation(FreeCAD.Vector(1,0,1),45)   # 45° about X and 45° about Z
#rot = FreeCAD.Rotation(10,20,30)                   # here example with Euler angle Yaw = 10 degrees (Z), Pitch = 20 degrees (Y), Roll = 30 degrees (X)
centre = FreeCAD.Vector(25,25,15)                  # central point of box
pos = obj.Placement.Base                           # position point of box
newplace = FreeCAD.Placement(pos,rot,centre)       # make a new Placement object
obj.Placement = newplace                           # spin the box
```

Das selbe Skript mit der Beispieldatei [RotateCoG2.fcstd](http   *//forum.freecadweb.org/download/file.php?id=1651) (Diskussion im [Forum](http   *//forum.freecadweb.org/viewtopic.php?f=3&t=3950#p31052))


```python
import FreeCAD
obj = App.ActiveDocument.Extrude                    # our box
rot = FreeCAD.Rotation(FreeCAD.Vector(0,0,1),45)    # 45 about Z
#rot = FreeCAD.Rotation(FreeCAD.Vector(1,0,1),45)    # 45° about X and 45° about Z
#rot = FreeCAD.Rotation(10,20,30)                    # here example with Euler angle Yaw = 10 degrees (Z), Pitch = 20 degrees (Y), Roll = 30 degrees (X)
centre = FreeCAD.Vector(25,25,0)                    # "centre" of rotation (where local Z cuts XY)
pos = obj.Placement.Base                            # original placement of obj
newplace = FreeCAD.Placement(pos,rot,centre)        # make a new Placement object
obj.Placement = newplace                            # spin the box
```

## Using Placement in expressions 


<div class="mw-translate-fuzzy">

## Verwendung der Positionierung in Ausdrücken 

In Ausdrücken ist es möglich, die Komponenten der Positionierung zu verwenden, um zum Beispiel den X-Wert eines Objektes mit der Benennung \"Cube\" anzusprechen   * 
```python<<Cube>>.Placement.Base.x```


</div>


```python
<<Cube>>.Placement.Base.x
```


<div class="mw-translate-fuzzy">

Der Winkel der Rotation kann angesprochen werden mit   * 
```python<<Cube>>.Placement.Rotation.Angle```


</div>


```python
<<Cube>>.Placement.Rotation.Angle
```


<div class="mw-translate-fuzzy">

Die Achse der Rotation kann angesprochen werden mit   * 
```python
<<Cube>>.Placement.Rotation.Axis.x
<<Cube>>.Placement.Rotation.Axis.y
<<Cube>>.Placement.Rotation.Axis.z
``` wobei oft einer der Faktoren den Wert 1 hat und die anderen den Wert 0.


</div>


```python
<<Cube>>.Placement.Rotation.Axis.x
<<Cube>>.Placement.Rotation.Axis.y
<<Cube>>.Placement.Rotation.Axis.z
```

where often one of these values is 1 while the others are 0.

Das gesamte Positionieren kann auch in einem einzigen Ausdruck verwendet werden   * Rechtklick auf Positionierungseigenschaft im Eigenschaftseditor, Ausdruck wählen und das Ausdrucksfenster wird geöffnet und alles, was eingegeben wird, wird in die Positionierungseigenschaft eingetragen und nicht in seine untergeordneten Eigenschaften.


<div class="mw-translate-fuzzy">

Um die Positionierung von \"Sketch\" mit der von \"Cylinder\" gleichzusetzen, würdest du auf diese Weise für Sketch den Ausdruck 
```python
<<Cube>>.Placement
``` ![Einstellung der gesamten Positionierung in einem Ausdruck](images/PlacementInExpression.png )


</div>


```python
<<Cube>>.Placement
```

![Setting the whole Placement in one expression](images/PlacementInExpression.png ) 

**Hinweis   *** Es ist auch möglich Positionierungsobjekte in Ausdrücken zu *erstellen*. Siehe hierzu auch [Ausdrücke / Placement](Expressions/de#Placement.md).

## Hinweise


<div class="mw-translate-fuzzy">

-   Die Positionierungseigenschaften unter dem Dataenreiter sind bei Objekten, die an andere Objekte angeheftet sind, deaktiviert.
-   Achse und Winkel können auch als [Quaternionen](https   *//de.wikipedia.org/wiki/Quaternion) ausgedrückt werden.
-   Der Referenzpunkt eines Objektes ändert sich, abhängit vom Objekt selbst. Beispiele allgemeiner Objekte   *

  Objekt                             Referenzpunkt
   
  Part.Box                           linker (minx), vorderer (miny), unterer (minz) Scheitelpunkt
  Part.Sphere                        Mittelpunkt der Kugel (d.h. Zentrum des Begrenzungskastens)
  Part.Cylinder                      Mitte der unteren Fläche
  Part.Cone                          Mitte der unteren Fläche (oder Scheitelpunkt, wenn der untere Radius 0 ist)
  Part.Torus                         Zentrum eines Torus
  Von Skizzen abgeleitete Merkmale   das Merkmal erbt die Position der zugrundeliegenden Skizze. Skizzen beginnen immer mit der Position = (0,0,0). Diese Position entspricht dem Ursprung in der Skizze.


</div>

  Object                           Reference Point
   
  Part.Box                         left (minx), front (miny), bottom (minz) vertex
  Part.Sphere                      center of the sphere (ie centre of bounding box)
  Part.Cylinder                    center of the bottom face
  Part.Cone                        center of bottom face (or apex if bottom radius is 0)
  Part.Torus                       center of the torus
  Features derived from Sketches   the Feature inherits the Position of the underlying Sketch. Sketches always start with Position = (0,0,0). This position corresponds to the origin in the sketch.

## Probleme

-   Ab Version 0.13 wurde die Aktualisierung der Positionierungseigenschaften auf der Registerkarte Daten für Objekte deaktiviert, die mit PartDesign erstellt wurden, mit Ausnahme der ersten Skizze, aus der das Solid erstellt wird. Daher kann die Positionierung eines Solids, das in PartDesign aus einer Skizze erstellt wurde, nur geändert werden, indem die Positionierungsparameter der ursprünglichen Konstruktionsskizze (der ersten Skizze), aus der das Solid erstellt wurde, angepasst werden.
-   Die Funktion der relativen Positionierung wird eventuell im Arbeitsbereich Zusammenbau behandelt.

## Weiteres

-   Dieses Tutorium   * [Flugzeug](Aeroplane/de.md) deckt die Mechanik der Änderung der Positionierung eines Objekts ausführlich ab.



---
![](images/Right_arrow.png) [documentation index](../README.md) > Placement/de
