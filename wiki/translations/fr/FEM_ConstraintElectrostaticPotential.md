---
- GuiCommand   */fr
   Name   *FEM ConstraintElectrostaticPotential
   Name/fr   *FEM Contrainte potentiel électrostatique
   MenuLocation   *Modèle → Contraintes électrostatiques → Contrainte de potentiel électrostatique
   Workbenches   *[FEM](FEM_Workbench/fr.md)
   SeeAlso   *[FEM Exemple calcul capacité de deux sphères](FEM_Example_Capacitance_Two_Balls/fr.md), [FEM Tutoriel](FEM_tutorial/fr.md)
---

# FEM ConstraintElectrostaticPotential/fr

## Description

Crée une contrainte FEM pour le potentiel électrostatique. A utiliser avec [FEM Equation électrostatique](FEM_EquationElectrostatic/fr.md) ou [FEM Équation force électrique](FEM_EquationElectricforce/fr.md).

## Utilisation

#\* Appuyez soit sur le bouton **<img src="images/FEM_ConstraintElectrostaticPotential.svg" width=16px> [Contrainte de potentiel électrostatique](FEM_ConstraintElectrostaticPotential/fr.md)
**

#\* Ou utilisez le menu **Modèle → Contraintes électrostatiques → <img src="images/FEM_ConstraintElectrostaticPotential.svg" width=16px> Contrainte de potentiel électrostatique**.

1.  Dans la [Vue 3D](3D_view/fr.md), sélectionnez l\'objet auquel la contrainte doit être appliquée.
2.  Appuyez sur le bouton **Ajouter**.

## Options

La boîte de dialogue propose les paramètres suivants    *

![](images/FEM_ElectrostaticPotential_dialog.png )

-   **Potentiel**    * potentiel électrique en V.
-   **Potentiel constant**    * option pour définir un potentiel constant.
-   **Champ lointain/Infinité électrique**    * option pour faire l\'approximation sphérique que le volume au-dessus de la face s\'étend à l\'infini.
-   **Calculer la force électrqiue**    * option pour déclencher le calcul de la force électrique en utilisant [FEM Équation force électrique](FEM_EquationElectricforce/fr.md).
-   **Capacité du corps    ***    * compteur du corps (ou de la face) avec une capacitance.





{{FEM Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [FEM](Category_FEM.md) > FEM ConstraintElectrostaticPotential/fr
