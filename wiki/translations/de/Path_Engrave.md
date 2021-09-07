---
- GuiCommand:/de
   Name:Path Engrave
   Name/de:Pfad Gravieren
   MenuLocation:Pfad → Gravieren
   Workbenches:[Pfad](Path_Workbench/de.md)
   Shortcut:
   SeeAlso:
---


</div>

## Beschreibung

The <img alt="" src=images/Path_Engrave.svg  style="width:24px;"> [Path Engrave](Path_Engrave.md) tool is primarily for engraving a <img alt="" src=images/Draft_ShapeString.svg  style="width:24px;"> [Draft ShapeString](Draft_ShapeString.md) onto a part. However, it may be useful for other kinds of 2D.

## Anwendung

Empty

## Optionen

Empty

## Properties

### Daten

#### Base

-    **Placement**: -

-    **Label**: - User name of the object (UTF-8)

#### Depth

-    **Clearance Height**: The height needed to clear clamps and obstructions

-    **Final Depth**: Final Depth of Tool- lowest value in Z

-    **Safe Height**: The above which Rapid motions are allowed.

-    **Start Depth**: Starting Depth of Tool- first cut depth in Z

-    **Step Down**: Incremental Step Down of Tool

#### Path

-    **Active**: - Make False, to prevent operation from generating code

-    **Base**: - The base geometry for this operation

-    **Comment**: - An optional comment for this operation

-    **Coolant Mode**: - Coolant mode for this operation

-    **Cycle Time**: - Estimated cycle time for this operation

-    **Start Vertex**: - The vertex index to start the path from

-    **Tool Controller**: - The tool controller that will be used to calculate the path

-    **User Label**: - User assigned label

### Hidden

-    **Base Object**: -

-    **Base Shapes**: -

-    **Expression Engine**: -

-    **Label2**: -

-    **Path**: -

-    **Proxy**: -

-    **Visibility**: -

### View

Empty

## Scripting


<div class="mw-translate-fuzzy">

## Skripten


**Siehe auch:**

[FreeCAD Grundlagen Skripten](FreeCAD_Scripting_Basics/de.md).


</div>

Example:


```python
#Place code example here.
```





{{Path_Tools_navi

}} 