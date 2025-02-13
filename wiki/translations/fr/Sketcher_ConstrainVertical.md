---
- GuiCommand   */fr
   Name   *Sketcher ConstrainVertical
   Name/fr   *Sketcher Contrainte verticale
   MenuLocation   *Sketch → Contraintes d'esquisse → Contrainte verticale
   Workbenches   *[Sketcher](Sketcher_Workbench/fr.md)
   Shortcut   ***V**
   SeeAlso   *[Sketcher Contrainte horizontale](Sketcher_ConstrainHorizontal/fr.md)
---

# Sketcher ConstrainVertical/fr

## Description

Permet de créér une contrainte de verticalité sur les lignes ou segments de polylignes sélectionnés. {{VersionPlus/fr|0.17}}on peut aussi contraindre des sommets verticalement. Plus d\'un élément peut être sélectionné.

## Utilisation

1.  Sélectionnez les lignes ou les sommets à contraindre verticalement
2.  Pour lancer la commande de contrainte verticale    *
    -   Appuyez sur l\'icône **[<img src=images/Sketcher_ConstrainVertical.svg style="width   *16px"> [Contrainte verticale](Sketcher_ConstrainVertical/fr.md)**.
    -   Utilisez le raccourci clavier **V**.
    -   Utilisez l\'entrée **Sketch → Contraintes d'esquisse → [<img src=images/Sketcher_ConstrainVertical.svg style="width   *16px"> Contrainte verticale** dans le menu déroulant de Sketch.
3.  Alternativement, l\'outil peut être démarré sans sélection préalable et il attendra une sélection mais seules les lignes seront sélectionnables.
4.  Faites un clic droit ou appuyez une fois sur **Echap** pour quitter l\'outil.

## Script


```pythonSketch.addConstraint(Sketcher.Constraint('Vertical', Line))```

La page [Sketcher Scripts](Sketcher_scripting/fr.md) explique les valeurs qui peuvent être utilisées pour `Line` et contient d\'autres exemples sur la façon de créer des contraintes à partir de scripts Python.





{{Sketcher_Tools_navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Sketcher](Sketcher_Workbench.md) > Sketcher ConstrainVertical/fr
