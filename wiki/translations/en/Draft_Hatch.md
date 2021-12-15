---
- GuiCommand:
   Name:Draft Hatch
   MenuLocation:Drafting → Hatch
   Workbenches:[Draft](Draft_Workbench.md), [Arch](Arch_Workbench.md)
   Shortcut:**H** **A**
   Version:0.20
   SeeAlso:[Draft Pattern](Draft_Pattern.md)
---

# Draft Hatch/en

## Description

The <img alt="" src=images/Draft_Hatch.svg  style="width:24px;"> **Draft Hatch** command creates hatches on the planar faces of a selected object.

## Usage

1.  Select an object with faces. Only the planar faces of the object will be hatched.
2.  There are several ways to invoke the command:
    -   Press the **<img src="images/Draft_Hatch.svg" width=16px> [Draft Hatch](Draft_Hatch.md)** button.
    -   Select the **Drafting → <img src="images/Draft_Hatch.svg" width=16px> Hatch** option from the menu.
    -   Use the keyboard shortcut: **H** then **A**.
3.  The **Hatch** task panel opens. See [Options](#Options.md) for more information.
4.  Press the **OK** button to finish the command.

## Options

-   Press the **...** button to select a **PAT file**. See [Notes](#Notes.md).
-   Select a **Pattern** from the file. It is currently advisable to avoid patterns with dashed lines.
-   Specify a **Scale** for the pattern.
-   Specify a **Rotation** for the pattern.
-   Press **Esc** or the **Close** button to abort the command.

## Pattern alignment 

When the hatch pattern for a face is calculated it is temporarily translated to the global XY plane by default. For a face with straight edged the first straight edge determines how this happens. The first point of that edge is put on the origin, and the edge itself is aligned with the X-axis. If you create [Draft Wires](Draft_Wire.md) with that in mind you can control how the hatch pattern is aligned with the outline of the face.

If all faces of the selected object are on the global XY plane you can switch off this default behavior by setting the **Translate** property of the Draft Hatch to `False`. The hatch pattern is then aligned with the origin and the X axis of the global coordinate system. For faces on the XY plane with straight edges the **Translate** property can be used to switch between absolute (on the left in the image) and relative (on the right in the image) patterns.

<img alt="" src=images/Draft_Hatch_alignment.png  style="width:400px;"> 
*
Two Draft Wires with hatches.<br>
The wires were created in a CCW direction starting from the bottom left point.<br>
For the Draft Hatch on the left the Translate property is set to false.<br>
For the Draft Hatch on the right it is set to true.
*

## Notes

-   For now the advice is to download a PAT file. Many can be found online. You can for example do a web search for {{FileName|acad.pat}} or {{FileName|acadiso.pat}}.
-   A small PAT file is installed with FreeCAD: {{FileName|<program_folder>/data/Mod/TechDraw/PAT/FCPAT.pat}}, where {{FileName|<program_folder>}} is the FreeCAD program folder:
    -   On Linux it is usually {{FileName|/usr/share/freecad}}.
    -   On Windows it is usually {{FileName|C:\Program Files\FreeCAD}}.
    -   On macOS it is usually {{FileName|/Applications/FreeCAD}}.

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

The following preferences are involved:

-   PAT file: **Tools → Edit parameters... → BaseApp → Preferences → Mod → TechDraw → PAT → FilePattern**.
-   Pattern: **Tools → Edit parameters... → BaseApp → Preferences → Mod → TechDraw → PAT → NamePattern**.
-   Scale: **Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → HatchPatternScale**.
-   Rotation: **Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → HatchPatternRotation**.

## Properties

See also: [Property editor](Property_editor.md).

A Draft Hatch object is derived from a [Part Feature](Part_Feature.md) object and inherits all its properties. It also has the following additional properties:

### Data


{{TitleProperty|Hatch}}

-    **Base|Link**: specifies the object whose faces are hatched.

-    **File|File**: specifies the PAT file.

-    **Pattern|String**: specifies the pattern name.

-    **Rotation|Angle**: specifies the rotation of the pattern.

-    **Scale|Float**: specifies the scale of the pattern.

-    **Translate|Bool**: specifies if the faces are temporarily translated to the global XY plane during the hatching process. Setting it to `False` may give wrong results for non-XY faces.

## Scripting

See also: _.

To create a Draft Hatch use the `make_hatch` method of the Draft module.


```python
hatch = make_hatch(baseobject, filename, pattern, scale, rotation)
```

Example:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

rectangle = Draft.make_rectangle(4000, 1000)
rectangle.MakeFace = True
filename = App.getHomePath() + "data/Mod/TechDraw/PAT/FCPAT.pat"
pattern = "Horizontal5" # The pattern must exist in the PAT file.
hatch = Draft.make_hatch(rectangle, filename, pattern, scale=50, rotation=45)

doc.recompute()
```

---
[documentation index](../README.md) > [Draft](Draft_Workbench.md) > Draft Hatch/en