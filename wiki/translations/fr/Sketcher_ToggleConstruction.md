---
- GuiCommand:/fr
   Name:Sketcher ToggleConstruction
   Name/fr:Sketcher Basculer construction
   MenuLocation:Sketch → Géométries d'esquisse → Basculer mode géométrie de construction
   Workbenches:[Sketcher](Sketcher_Workbench/fr.md)
---

## Description

Cet outil permet de basculer les géométries sélectionnées de/à mode de construction. Il peut être utilisé sur n\'importe quel type de géométrie : ligne, arc, ou un cercle.

La géométrie de construction est un outil important du Sketcher. Lorsque vous utilisez une esquisse pour une opération 3D, la géométrie de construction est ignorée.

En **<img src=images/Sketcher_EditSketch.svg style="width:16px"> <img src=images/Sketcher_LeaveSketch.svg style="width:mode d'édition d'esquisse](Sketcher_EditSketch/fr.md)**, la géométrie de construction est affichée en bleu, et ne deviendra pas verte lorsqu\'une esquisse est entièrement contrainte. Une fois que vous **[16px"> [quittez le mode d'édition d'esquisse](Sketcher_LeaveSketch/fr.md)**, la géométrie de construction est masquée dans la [vue 3D](3D_view/fr.md).

Les lignes de construction peuvent être utilisées comme axe de rotation par la fonction **<img src=images/PartDesign_Revolution.svg style="width:16px"> [PartDesign Révolution](PartDesign_Revolution/fr.md)**.

<img alt="" src=images/Sketcher_ConstructionMode_fr_01.png  style="width:480px;">

## Utilisation

Il y a deux façons d\'utiliser cet outil :

1.  Sans que rien ne soit sélectionné dans la [Vue 3D](3D_view/fr.md) :
    -   Activez le mode construction en cliquant sur le **<img src=images/Sketcher_ToggleConstruction.svg style="width:16px"> <img src=images/Sketcher_ToggleConstruction.svg style="width:Basculer mode géométrie de construction](Sketcher_ToggleConstruction/fr.md)** ou en utilisant l\'entrée **Sketch → Géométries d'esquisse → [16px"> Basculer mode géométrie de construction** dans le menu Sketcher.
    -   Cela changera la couleur pour la création de nouveaux éléments géométriques en bleu.
    -   Les éléments géométriques nouvellement créés seront désormais créés en mode construction.
2.  Avec un ou plusieurs éléments géométriques sélectionnés dans la [Vue 3D](3D_view/fr.md).
    -   Invoquez l\'outil Sketcher ToggleConstruction en cliquant sur le **<img src=images/Sketcher_ToggleConstruction.svg style="width:16px"> [Basculer mode géométrie de construction](Sketcher_ToggleConstruction/fr.md)** ou en le sélectionnant dans le menu.
    -   Les éléments sélectionnés passent alors en mode construction.
    -   Ensuite, les éléments nouvellement créés seront à nouveau des géométries normales.

## Exemple

Utilisez le mode de construction sur des géométries d\'esquisse,

<img alt="" src=images/Sketcher_ConstructionMode_fr_01.png  style="width:450px;">

puis une fois que vous quittez le **<img src=images/Sketcher_LeaveSketch.svg style="width:16px"> [mode d'édition d'esquisse](Sketcher_LeaveSketch/fr.md)**, les géométries qui ont été basculées en mode construction sont devenues invisibles à l\'écran dans la [vue 3D](3D_view/fr.md) (mais sont toujours présentes dans le mode d\'édition d\'esquisse).

<img alt="" src=images/Sketcher_ConstructionMode_fr_02.png  style="width:450px;">





{{Sketcher Tools navi

}}  