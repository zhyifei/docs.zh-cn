---
title: 默认属性“<propertyname1>”与“<propertyname2>”中的默认属性“<classname>”冲突，因此应声明为“Shadows”
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803683"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>默认属性\<propertyname1 > 与默认属性冲突\<propertyname2 > 中\<类名 >'，因此应声明为 Shadows
使用与基类中定义的属性相同的名称声明属性。 在这种情况下，在此类的属性应隐藏基类属性。  
  
 此消息是一个警告。 默认假定`Shadows` 。 若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40007  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 添加`Shadows`关键字为声明或将更改正在声明的属性的名称。  
  
## <a name="see-also"></a>请参阅

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [在 Visual Basic 中隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
