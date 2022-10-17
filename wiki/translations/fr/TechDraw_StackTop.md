---
- GuiCommand   */fr
   Name   *TechDraw StackTop
   Name/fr   *TechDraw Empiler en haut
   MenuLocation   *TechDraw → Empiler → Déplacer la vue vers le haut de la pile
   Workbenches   *[TechDraw](TechDraw_Workbench/fr.md)
   Shortcut   *
   Version   *1.0
   SeeAlso   *[TechDraw Empiler en bas](TechDraw_StackBottom/fr.md), [TechDraw Empiler vers le haut](TechDraw_StackUp/fr.md), [TechDraw Empiler vers le bas](TechDraw_StackDown/fr.md).
---

# TechDraw StackTop/fr

## Description

L\'outil <img alt="" src=images/TechDraw_StackTop.svg  style="width   *24px;"> **TechDraw Empiler en haut** déplace les vues au sommet de l\'ordre d\'empilement. L\'ordre d\'empilement contrôle la profondeur apparente des vues sur une page.

## Utilisation

1.  Sélectionnez une ou plusieurs vues sur une [Page](TechDraw_PageDefault/fr.md) ou dans la [Vue en arborescence](Tree_view/fr.md). Pour cet outil, et [TechDraw Empiler en bas](TechDraw_StackBottom/fr.md), l\'ordre de sélection est important.
2.  Il existe plusieurs façons de lancer l\'outil    *
    -   Appuyez sur le bouton **<img src="images/TechDraw_StackTop.svg" width=16px> [Déplacer la vue vers le haut de la pile](TechDraw_StackTop/fr.md)**.
    -   Sélectionnez la **TechDraw → Empiler → <img src="images/TechDraw_StackTop.svg" width=16px> Déplacer la vue vers le haut de la pile** dans le menu.
3.  La propriété **Stack Order** des vues est modifiée.

## Script


**Voir aussi   ***

[TechDraw API](TechDraw_API/fr.md) et [Débuter avec les scripts](FreeCAD_Scripting_Basics/fr.md).

L\'ordre d\'empilement peut être modifié dans les scripts en changeant la propriété {{Incode|StackOrder}} de {{Incode|ViewObject}} d\'une vue.





{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw StackTop/fr