


<div class="mw-translate-fuzzy">


{{VeryImportantMessage|(November 2018) Diese Information kann unvollständig und veraltet sein. Für die letzte API siehe die (engl.) [https://www.freecadweb.org/api autogenerierte API-Dokumentation].}}


</div>

Being parametric, document objects in FreeCAD can have a lot of additional properties, but these are the basic ones, present in every FreeCAD Document Object. Objects can be retrieved simply by their name. Example: 
```python
myObj = FreeCAD.ActiveDocument.myObjectName
print myObj.PropertiesList
```


{{APIProperty|Content|An XML representation of the properties of an object.}}


{{APIProperty|Label|Gets/sets the objects label. The string can be unicode.}}


{{APIProperty|Name|The unique name of an object.}}


{{APIProperty|Placement|Gets/sets the Placement of an object. A placement defines an orientation (rotation) and a position (base) in 3D space. It is used when no scaling or other distortion is needed.}}


{{APIProperty|PropertiesList|A list of the properties of an object}}


{{APIProperty|State|The FreeCAD state of an object (ie. if it needs to be recomputed)}}


{{APIProperty|Type|A string describing the type of an object}}


{{APIProperty|ViewObject|The associated View Provider (FreeCADGUI object) of an object}}


{{APIFunction|getAllDerivedFrom| | |All descendants of this object}}


{{APIFunction|getDocumentationOfProperty| | |The documentation string of the property of this class.}}


{{APIFunction|getGroupOfProperty| | |The name of the group which the property belongs to in this class. The properties are sorted in different named groups for convenience.}}


{{APIFunction|getPropertyByName| | |The value of a named property.}}


{{APIFunction|getTypeOfProperty| | |The type of a named property. This can be (Hidden,ReadOnly,Output) or any combination.}}


{{APIFunction|isDerivedFrom| | |True if given type is a father}}


{{APIFunction|purgeTouched| |Marks the object as unchanged| }}


{{APIFunction|touch| |Marks the object as changed (touched)| }}


 

[Category:API{{\#translation:}}](Category:API.md) [Category:Poweruser Documentation{{\#translation:}}](Category:Poweruser_Documentation.md)