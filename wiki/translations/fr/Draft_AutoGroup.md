---
- GuiCommand:/fr
   Name:Draft AutoGroup
   Name/fr:Draft Groupement automatique
   MenuLocation:Utilitaires → Groupement automatique
   Workbenches:[Draft](Draft_Workbench/fr.md), [Arch](Arch_Workbench/fr.md)
   Version:0.17
   SeeAlso:[Draft Calque](Draft_Layer/fr.md), [Std Créer un groupe](Std_Group/fr.md)
---

## Description

La commande <img alt="" src=images/Draft_AutoGroup.svg  style="width:24px;"> **Draft Groupement automatique** modifie le [Draft Calque](Draft_Layer/fr.md) actif ou, [éventuellement](#Pr.C3.A9f.C3.A9rences.md), l\'objet actif [Std Groupe](Std_Group/fr.md) ou similaire aux groupes [Arch](Arch_Workbench/fr.md). Les nouveaux objets [Draft](Draft_Workbench/fr.md) et [Arch](Arch_Workbench/fr.md) sont automatiquement placés dans ce calque ou groupe actif.

Cette commande était à l\'origine destinée aux groupes, d\'où son nom, mais a été remaniée dans la version 0.19 de FreeCAD lorsqu\'un système de calques a été introduit. Comme la gestion des couches est maintenant la valeur par défaut de la commande, le reste de cette page se concentrera principalement sur les couches.

![](images/Draft_tray_menu.png ) *Le menu calque de la barre Draft*

## Utilisation

1.  Pour utiliser cette commande dans FreeCAD version 0.19, au moins un [calque](Draft_Layer/fr.md) doit exister.
2.  Sélectionnez éventuellement le calque que vous voulez rendre actif dans la [Vue en arborescence](Tree_view/fr.md).
3.  Il existe plusieurs façons de lancer la commande :
    -   Appuyez sur le **<img src="images/button_invalid.svg" width=16px> [Aucun](Draft_AutoGroup/fr.md)** dans la [Draft Barre](Draft_Tray/fr.md). Ce bouton peut avoir un aspect différent. S\'il y a un calque actif, il affichera le nom du calque et une icône de calque avec la {{PropertyView/fr|Line Color}} et la {{PropertyView/fr|Shape Color}} du calque.
    -   Sélectionnez l\'option **Utilitaires → <img src="images/Draft_AutoGroup.svg" width=16px> Groupement automatique** dans le menu.
    -   Si vous avez sélectionné un calque : sélectionnez l\'option **<img src="images/button_right.svg" width=16px> Activer ce calque** dans le menu contextuel de la [Vue en arborescence](Tree_view/fr.md).
4.  Si vous n\'avez pas encore sélectionné de calque, le menu des calques s\'ouvre. Effectuez l\'une des opérations suivantes :
    -   Sélectionnez **None** pour travailler sans calque actif.
    -   Sélectionnez un calque existant pour le rendre actif.
    -   Sélectionnez **Add new Layer** pour créer un nouveau calque. La sélection de cette option ne modifie pas la couche active.
5.  Si le calque active a été modifiée, le bouton de la [Draft Barre](Draft_Tray/fr.md) est mis à jour.

## Remarques

-   Un nouveau [calque](Draft_Layer/fr.md) peut également être créé en cliquant avec le bouton droit de la souris sur le conteneur de calque dans la [Vue en arborescence](Tree_view/fr.md) et en sélectionnant l\'option **<img src="images/Draft_NewLayer.svg" width=16px> Ajouter un nouveau calque** dans le menu contextuel.
-   Si [Draft Basculer en mode construction](Draft_ToggleConstructionMode/fr.md) est activé, le [calque](Draft_Layer/fr.md) actif est ignoré.

## Préférences

Voir aussi : [Réglage des préférences](Preferences_Editor/fr.md) et [Draft Préférences](Draft_Preferences/fr.md).

-   Cette commande peut éventuellement gérer aussi les groupes : **Edition → Préférences... → Draft → Paramètres généraux → Réglages généraux Draft → Afficher les groupes dans la liste déroulante des calques**.

## Script

Voir aussi: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) et [Débuter avec les scripts FreeCAD](FreeCAD_Scripting_Basics/fr.md).

Si l\'[atelier Draft](Draft_Workbench/fr.md) est actif, l\'objet d\'application FreeCADGui possède une propriété `draftToolBar`. Cet objet `draftToolBar` a une propriété `autogroup`, qui contient le nom de l\'autogroupe actif, ou est `None` si aucun autogroupe n\'est actif. Pour modifier l\'autogroupe actif, utilisez la méthode `setAutoGroup` de l\'objet `draftToolBar`. Pour placer des objets dans l\'autogroupe actif, utilisez la méthode `autogroup` du module Draft.


```python
# This code only works if the Draft Workbench is active!

import FreeCAD as App
import FreeCADGui as Gui
import Draft

doc = App.newDocument()

polygon1 = Draft.make_polygon(5, radius=1000)
polygon2 = Draft.make_polygon(3, radius=500)
polygon3 = Draft.make_polygon(6, radius=220)

layer = Draft.make_layer()
Gui.draftToolBar.setAutoGroup(layer.Name)

Draft.autogroup(polygon1)
Draft.autogroup(polygon2)
Draft.autogroup(polygon3)

doc.recompute()
```





 