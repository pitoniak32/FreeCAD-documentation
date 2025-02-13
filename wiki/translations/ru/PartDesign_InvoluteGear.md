---
- GuiCommand   */ru
   Name/ru   *Шестерня с эвольвентным профилем
   Name   *PartDesign_InvoluteGear
   MenuLocation   *Part Design → Шестерня с эвольвентным профилем...
   Workbenches   *[PartDesign](PartDesign_Workbench/ru.md)
   SeeAlso   *[Верстак FCGear](FCGear_Workbench/ru.md)
---

# PartDesign InvoluteGear/ru

## Описание

Инструмент позволяет создать двумерный профиль эвольвентного зубчатого колеса (шестерни). Этот профиль полностью параметрический настраиваемый, и может быть преобразован в твердое тело с помощью [выдавливания](PartDesign_Pad/ru.md) или инструмента [Аддитивная спираль](PartDesign_AdditiveHelix.md).

For more detailed information see Wikipedia\'s entries for   * [Gear](https   *//en.wikipedia.org/wiki/Gear) and [Involute Gear](https   *//en.wikipedia.org/wiki/Involute_gear)

![](images/PartDesign_Involute_Gear_01.png )

## Применение

### Создание профиля 

1.  По желанию активируйте подходящее тело (необязательно) .
2.  Выберите пункт меню **Part Design → [<img src=images/PartDesign_InternalExternalGear.svg style="width   *16px"> Шестерня с эвольвентным профилем...**.
3.  Установите параметры эвольвентного зацепления.
4.  Нажмите **OK**.
5.  Если при создании профиля активного Тело не было выбрано, тогда переместите сформированный профиль в какое-нибудь Тело чтобы в дальнейшем выдавить или вырезать полученный профиль.

### Формирование зубчатого колеса из профиля 

1.  Выберите уже сформированный профиль зубчатого колеса в [иерархии проекта](Tree_view/ru.md).
2.  Примените инструмент **<img src="images/PartDesign_Pad.svg" width=16px> [Выдавливание](PartDesign_Pad/ru.md)**.
3.  Установите величину выдавливания **Length** чтобы получить зубчатое колесо желаемой толщины.
4.  Нажмите **OK**

### Создание косозубого зубчатого колеса 


{{Version/ru|0.19}}

1.  Select the gear profile in the [Tree view](Tree_view.md).
2.  Press the **<img src="images/PartDesign_AdditiveHelix.svg" width=16px> [PartDesign AdditiveHelix](PartDesign_AdditiveHelix.md)** button.
3.  Choose as Axis the normal of the gear profile, that is **Normal sketch axis** <small>(v0.20)</small> . (In earlier versions the **Base Z axis** can be used as long as the profile\'s plane has not been altered.)
4.  Choose a **Height-Turns** mode.
5.  Set the **Height** to the desired face width of the gear.
6.  To set the desired helical angle an [Expression](Expressions.md) for the **Turns** is required.
    1.  Click the blue <img alt="" src=images/Bound-expression.svg  style="width   *16px;"> icon at the right of the input field.
    2.  Enter the following formula   * `Height * tan(25°) / (InvoluteGear.NumberOfTeeth * InvoluteGear.Modules * pi)`, where `25°` is an example for the desired helical angle (also known as beta-value) and `InvoluteGear` is the **Name** of the profile.
    3.  Click **OK** to close the formula editor.
7.  Click **OK** to close the task panel.

Hint   * To make the helical angle an accessible parameter, use a *dynamic property*   *

1.  Select the profile.
2.  In the [Property editor](Property_editor.md) activate the **Show all** option in the context menu.
3.  Again in the context menu, select **Add Property**. Note   * this entry is only available when **Show all** is active.
4.  In the **Add Property** dialog   *
    1.  Choose `App   *   *PropertyAngle` as Type.
    2.  Set `Gear` as Group.
    3.  Set `HelicalAngle` as Name (without a space).
    4.  Click **OK**
5.  Now a new property **Helical Angle** (space added automatically), with an initial value of `0.0°`, becomes available.
6.  Assign the desired helical angle to the new property.
7.  In the formula of the **Turns** property of the AdditiveHelix, you can now reference `InvoluteGear.HelicalAngle` instead of the hard coded value of e.g. `25°`; again assuming `InvoluteGear` is the **Name** of the profile.

## Свойства

-    **External Gear**   * Внешнее зацепление - Да или Нет

-    **High Precision**   * Высокая точность - Да или Нет

-    **Modules**   * Модуль - Диаметр делительной окружности, деленный на количество зубцов.

-    **Number Of Teeth**   * Задает количество зубьев.

-    **Pressure Angle**   * Acute angle between the line of action and a normal to the line connecting the gear centers. Default is 20 degrees. ([More info](https   *//en.wikipedia.org/wiki/Involute_gear))

## Ограничения

-   It is currently not possible to adjust the tooth thickness. Tooth and tooth space are distributed equally on the pitch circle. Thus the only way to control backlash is to adjust the center distance in a gear paring.
-   There is currently no [undercut](https   *//www.tec-science.com/mechanical-power-transmission/involute-gear/undercut/) in the generated gear profile. That means gears with a low number of teeth can interfere with the teeth of the mating gear. The lower limit depends on the **Pressure Angle** and is around 17 teeth for 20° and 32 for 14.5°. Most practical applications tolerate a missing undercut for gears a little smaller than this theoretical limit though.

## Материалы для изучения 

[Как создавать шестерни в FreeCAD](https   *//www.youtube.com/watch?v=8VNhTrnFMfE)

## Сопутствующая информация 

-   [Верстак FCGear](FCGear_Workbench/ru.md)





{{PartDesign Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [PartDesign](PartDesign_Workbench.md) > PartDesign InvoluteGear/ru
