---
- GuiCommand:/fr
   Name:Path Helix
   Name/fr:Path Helix 
   MenuLocation:Path → Helix
   Workbenches:[Path](Path_Workbench/fr.md)
   Shortcut:
   SeeAlso:
---


</div>

## Description

La commande <img alt="" src=images/Path_Helix.svg  style="width:24px;"> [Path Helix ](Path_Helix/fr.md) insère une opération d\'interpolation hélicoïdale à la tâche. L\'interpolation hélicoïdale dans le sens des aiguilles d\'une montre produit des commandes G-Code (G2). A l\'inverse, des commandes G-Code (G3). Pourcentage de dépassement spécifie le dépassement concentrique en pourcentage du diamètre de l\'outil.

## Utilisation

-   Sélectionnez l\'**<img src=images/Workbench_Path.svg style="width:16px"> [atelier Path](Path_Workbench/fr.md)**.
-   Sélectionnez l\' icône **<img src="images/Path_Helix.svg" width=24px>** ou le bouton dans le menu de la barre d\'outils **Path** → **<img src="images/Path_Helix.svg" width=24px> Helix**. Cela ouvre le panneau de configuration.
-   Choisissez un contrôleur d\'outil et confirmez en appuyant sur **Apply**.
-   Tous les trous disponibles compatibles avec l\'outil Hélix du modèle de travail pourront être sélectionnés pour le traitement. Lors de l\'acquittement, l\'outil créera un chemin pour ceux répertoriés dans l\'onglet Géométrie de base. Confirmez que la liste correspond aux trous destinés au traitement. Ajustez avec ajouter, activer ou désactiver, si nécessaire. Notez que les trous peuvent également être sélectionnés par leur bord ainsi que par leurs côtés.
-   Assurez-vous que la profondeur de départ, la profondeur finale et l\'abaissement sont corrects et ajustez au besoin.
-   Assurez-vous que les hauteurs de sécurité et de dégagement sont correctes et ajustez-les au besoin.
-   Dans l\'onglet Opération, spécifiez le pourcentage du point de départ de Helix, de la direction et du dépassement.
-   Cliquez sur **Apply** pour créer ou mettre à jour le chemin, sur **OK** pour appliquer et fermer le panneau ou sur **Cancel** pour annuler et fermer le panneau.


<div class="mw-translate-fuzzy">

## Options

Empty


</div>

Empty

## Propriétés


<div class="mw-translate-fuzzy">

### Données

Empty


</div>

Empty


<div class="mw-translate-fuzzy">

### Vue

Empty


</div>

Empty

## Scripting


<div class="mw-translate-fuzzy">

## Script


**Voir aussi:**

[FreeCAD Script de base](FreeCAD_Scripting_Basics/fr.md).


</div>


<div class="mw-translate-fuzzy">

Exemple: 
```python#Place code example here.```


</div>


```python
#Place code example here.
```


<div class="mw-translate-fuzzy">





</div>


{{Path_Tools_navi

}} 