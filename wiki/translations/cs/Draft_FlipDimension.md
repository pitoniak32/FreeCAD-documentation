---
- GuiCommand:/cs   Name:Draft FlipDimension   Name/cs:Kreslení PřehoďKótu   Workbenches:[Architektura](Draft_Workbench/cs___Kreslení]],_[[Arch_Workbench/cs.md)|MenuLocation:Draft → Utilities → Flip Dimension   SeeAlso:[Kóty](Draft_Dimension/cs.md)---


</div>

## Description


<div class="mw-translate-fuzzy">

## Popis

Ve 2D módu je zobrazení textu [Kóty](Draft_Dimension/cs.md) zarovnáno ke kótovací čáře. Nástroj Kóta se snaží vždy zobrazit text na správné straně kótovací čáry v závislosti ze které strany má být viděna. V některých případech však směr pohledu nemusí vyjadřovat smysl pohledu a pak se může hodit změna orientace textu kóty. Tento nástroj obrací orientaci vybraného objektu [kóty](Draft_Dimension/cs.md).


</div>

## Usage


<div class="mw-translate-fuzzy">

## Použití

1.  Vyberte jeden nebo více objektů [kóta](Draft_Dimension/cs.md)
2.  Stiskněte tlačítko **<img src="images/Draft_FlipDimension.png" width=16px> [PřehoďKótu](Draft_FlipDimension/cs.md)
**


</div>

## Notes

-   [Draft Dimensions](Draft_Dimension.md) also have a **Flip Text** property. When set to `True` the text is rotated 180° around the normal direction. This can be combined with the effect of this command.

## Scripting

See also: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

To flip a [Draft Dimension](Draft_Dimension.md) invert its `Normal` property.

Example:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

p1 = App.Vector(0, 0, 0)
p2 = App.Vector(1000, 0, 0)
p3 = App.Vector(500, 300, 0)
dimension = Draft.make_dimension(p1, p2, p3)
dimension.ViewObject.FontSize = 200

dimension.Normal = dimension.Normal.negative()
doc.recompute()
```





 