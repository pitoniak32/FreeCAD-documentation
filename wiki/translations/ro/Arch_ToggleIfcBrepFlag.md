---
- GuiCommand:/ro   Name:Arch ToggleIfcBrepFlag   Name/ro:Arch ToggleIfcBrepFlag   Workbenches:[[Arch Module/ro   Arch]]|MenuLocation:Arch → Utilities → Toggle Ifc Brep flag   Shortcut:   SeeAlso:---


</div>

## Descriere


<div class="mw-translate-fuzzy">

Acest instrument permite / dezactivează funcția IfcBrep a unui obiect Arch selectat (valoarea implicită este întotdeauna dezactivată). Dacă indicatorul/steagul este activat la exportul obiectului în format IFC, obiectul va fi exportat ca IfcFacetedBrep, chiar dacă este posibil un export de nivel superior, cum ar fi IfcExtrudedAreaSolid sau IfcBooleanResult. Deși obiectele IfcFacetedBrep sunt mai grele și mai puțin editabile (pierd informații de geometrie cum ar fi istoricul de modelare), ele sunt mai puțin predispuse la erori. În unele cazuri, setarea acestui indicator rezolvă probleme cu obiectele care nu sunt exportate corect atunci când acest indicator nu este setat.

Acest instrument activează / dezactivează opțiunea IfcBrep a unui obiect [Mod Modul](Mod_Modul.md) (valoarea implicită este întotdeauna dezactivată). Dacă instrumentul este activat la exportul obiectului în format IFC, obiectul va fi exportat ca [ifcgeometricmodelresource / lexical / ifcfacetedbrep.htm IfcFacetedBrep](http://www.buildingsmart-tech.org/ifc/IFC4/final/html/schema/), chiar dacă este posibil un export de nivel superior, cum ar fi IfcExtrudedAreaSolid sau IfcBooleanResult. Deși obiectele IfcFacetedBrep sunt mai grele și mai puțin editabile (pierd informații de geometrie cum ar fi istoricul de modelare), ele fac adesea mai puține erori. În unele cazuri, setarea acestui steag rezolvă probleme cu obiectele care nu sunt exportate corect atunci când acest indicator/steag nu este setat.


</div>


<div class="mw-translate-fuzzy">

## Cum se folosește 


</div>


<div class="mw-translate-fuzzy">

1.  Selectați un obiect Arch
2.  Selectați meniul pe traseul Arch → Utilities → **<img src="images/Arch_ToggleIfcBrepFlag.png" width=16px> [Toggle IfcBrepFlag](Arch_ToggleIfcBrepFlag.md)
**


</div>








