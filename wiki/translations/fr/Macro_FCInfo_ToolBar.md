# Macro FCInfo ToolBar/fr
{{Macro
|Name=Macro FCCInfo ToolBar
|Icon=FCInfoToolBar.png
|Description=Donne des informations sur la forme sélectionnée et peut afficher une conversion de rayon, diamètre, longueur, surface, volume ... dans différentes unités (métriques et impériales) dans une barre d'outils. Les informations à afficher sont paramétrables dans le Paramètre de FreeCAD.
|Author=Mario52
|Version=00.01
|Date=2022/02/16
|FCVersion=0.18 and more
|Download= [https://wiki.freecadweb.org/images/9/9d/FCInfoToolBar.png The toolBar icon]
|SeeAlso = [Arch Survey](Arch_Survey/fr.md) <img src="images/Arch_Survey.svg" width=32px></br>[Macro FCInfo](Macro_FCInfo/fr.md) <img src="images/FCInfo.png" width=32px></br>[Macro FCInfoGlass](Macro_FCInfoGlass/fr.md) <img src="images/Macro_FCInfoGlass.png" width=32px>
}}

## Description

Donne des informations sur la forme sélectionnée et peut afficher une conversion de rayon, diamètre, longueur, surface, volume \... dans différentes unités (métriques et impériales) dans une barre d\'outils. Les informations à afficher sont paramétrables dans le Paramètre de FreeCAD.


{{Codeextralink|https://gist.githubusercontent.com/mario52a/e382adbe41747788ad15a18eb206a872/raw/988f17e458a4160a6f3a772c1d6c8b6a948c8748/FCInfo_ToolBar.FCMacro}}

![FCInfo\_ToolBar](images/Macro_FCInfo_ToolBar_00.png ) 
*FCInfo_ToolBar*

## Utilisation

Après avoir exécuté la macro, allez dans Menu → Outils → Éditer paramètres \... :BaseApp/Preferences/Macros/FCMmacros/FCInfo\_ToolBar

et validez les infos que vous voulez afficher.

Les informations complètes sont affichées dans la fenêtre ToolTip, l\'option cochée est visible si le \"\*\" est affiché.

Utilisez le bouton de réinitialisation après avoir modifié une option dans la fenêtre des paramètres.

L\'unité de longueur peut être sélectionnée : km, hm, dam, m, dm, cm, mm, µm, nm, pm, fm, inch, link, foot, yard, perch, chain, furlong, mile, league, nautique.

![FCInfo\_ToolBar the info toolTip](images/Macro_FCInfo_ToolBar_01.png ) 
*FCInfo_ToolBar the info toolTip*

## Options

Les options sont situées dans les paramètres de FreeCAD.

*Menu → Outils → Éditer les parametres \... :BaseApp/Preferences/Macros/FCMmacros/FCInfo\_ToolBar*

-   ***switch\_User\_ToolbarIconSize***
    -   si = `False` : l\'icône de la barre d\'outils respecte la valeur FreeCAD pour la taille de l\'icône
    -   si = `True` : l\'icône prend les valeurs des variables **seT\_User\_sizeIconX** et **seT\_User\_sizeIconY**

-   ***seT\_User\_sizeIconX***
    -   donne la valeur X de l\'icône

-   ***seT\_User\_sizeIconY***
    -   donne la valeur Y de l\'icône

-   ***seT\_User\_StyleSheetColorToolBar***
    -   donne une couleur à la barra d\'outils en format HTML exemple : **\#F8E6E0**
    -   si la valeur est **0** la barre d\'outils respecte les couleurs du système

-   ***seT\_User\_DecimalValue***
    -   détermine le nombre de décimales a afficher (Defaut **2**)

-   ***seT\_User\_TextHeigthValue***
    -   donne un hauteur au texte affiché dans la barre d\'outils

-   ***switch\_User\_Display\_SubElementName***
    -   affiche le SubElementName

-   ***switch\_User\_Display\_ShapeType***
    -   affiche le Shape type

-   ***switch\_User\_Display\_TypeId***
    -   affiche le TypeId

-   ***switch\_User\_Display\_RadiusObject***
    -   affiche le rayon et le diametre si un cercle est détecté

-   ***switch\_User\_Display\_LengthObject***
    -   affiche la longueur du bord sélectionné ou le périmètre de la face si une face est sélectionnée

-   ***switch\_User\_Display\_NumberFacesMesh***
    -   affiche le nombre de faces de l\'objet Mesh

-   ***switch\_User\_Display\_NumberPointsMeshPoints***
    -   affiche le nombre de points de l\'objet Mesh

-   ***switch\_User\_Display\_NumberEdgesMesh***
    -   -   affiche le nombre de bords de l\'objet Mesh

-   ***switch\_User\_Display\_AreaObject***
    -   affiche la surface de l\'objet

-   ***switch\_User\_Display\_AreaSubObject***
    -   affiche la surface de la face selectionnée

-   ***switch\_User\_Display\_VolumeObject***
    -   affiche le volume de l\'objet

-   ***switch\_User\_Display\_BsplineObject***
    -   affiche le nombre de noeuds du Bspline sélectionné

-   ***switch\_User\_Display\_CentreObject***
    -   affiche le centre du cercle (si un cercle est détecté)

-   ***switch\_User\_Display\_CentreBoundBoxObject***
    -   affiche le center du boundingBox de l\'objet

-   ***switch\_User\_Display\_Position***
    -   affiche les coordonnées du point cliqué par la souris

-   ***switch\_User\_NotInfoOnBeginning***
    -   s\'il est `False` les infos (ces informations) sont affichées
    -   s\'il est `True` les infos ne sont pas affichées

-   ***seT\_User\_UnitSymbolSquare***
    -   donne le symbole carré (Défaut **2**)

-   ***seT\_User\_UnitSymbolCube***
    -   donne le symbole cube (Défaut **3**)

-   ***seT\_User\_UnitSymbolMicro***
    -   donne le symbole micro (Défaut **u**)

## Démarrage automatique 

#### avec ligne de commande 

Dans votre raccourci *vérifiez votre droit chemin*.

\"Chemin\_complet\_de\_FreeCAD\" \"Chemin\_complet\_de\_la\_macro.FCMacro\"

exemple:


```python
"C:/FreeCAD_0.20.26858_Win-LPv12.5.4_vc17.x-x86-64/bin/FreeCAD.exe" "C:/Users/User/AppData/Roaming/FreeCAD/Macro/FCInfo_ToolBar.FCMacro"
```

#### Dans le répertoire Mod 

1.  Après avoir installé la macro avec AddonManager
2.  Créez le répertoire *FCInfo\_ToolBar*.
3.  Copiez la macro FCInfo\_ToolBar.FCMacro (copier et non déplacer) dans le répertoire *FCInfo\_ToolBar* et renommez-la en FCInfo\_ToolBar.py
4.  Créez un fichier nommé InitGui.py
5.  Collez ce code dans InitGui.py:


```python
#### FC Version: 0.1 #16/02/2022
#### Mario52
#### FCInfo_ToolBar : mini FCInfo ####
#
import importlib
from importlib import reload
import FreeCAD, FreeCADGui
App = FreeCAD
Gui = FreeCADGui


switch_User_NotRunAuto = FreeCAD.ParamGet("User parameter:BaseApp/Preferences/Macros/FCMmacros/FCInfo_ToolBar").GetBool("switch_User_NotRunAuto")
## switch_User_NotRunAuto 0 (False) = run the macro in begin
## switch_User_NotRunAuto 1 (True)  = not run automatic the macro


if switch_User_NotRunAuto == False:
    import FCInfo_ToolBar
    #reload(FCInfo_ToolBar)
    FreeCAD.ParamGet("User parameter:BaseApp/Preferences/Macros/FCMmacros/FCInfo_ToolBar").SetBool("switch_User_NotRunAuto", False)
    #FreeCAD.Console.PrintMessage("InitGui Ok FCInfo_ToolBar" + "\n")
```

1.  sauvez le fichier
2.  Exécuter FreeCAD
3.  Si la macro n\'est pas exécutée (normal), exécutez la macro FCInfo\_ToolBar.FCMacro comme une macro normale.
4.  Au prochain démarrage de FreeCAD, la macro doit démarrer automatiquement.

## Liens

## Version

version: 00.01 2022/02/16 :



---
![](images/Right_arrow.png) [documentation index](../README.md) > Macro FCInfo ToolBar/fr