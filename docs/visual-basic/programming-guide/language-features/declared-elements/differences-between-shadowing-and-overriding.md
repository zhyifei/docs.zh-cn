---
title: 隐藏和重写之间的差异 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 94ce3e7fe25b7942730e6e89a53654b03d91c42b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649628"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>隐藏和重写之间的差异 (Visual Basic)
在定义继承自基类的类时，你有时想要重新定义一个或多个派生类中的基类元素。 隐藏和重写均可用于此目的。  
  
## <a name="comparison"></a>比较  
 隐藏和重写同时时将使用派生的类继承自基类，并同时重新定义与另一个声明的元素。 但是，这两者之间的重大差异。  
  
 下表比较隐藏和重写。  
  
||||  
|---|---|---|  
|比较点|隐藏|重写|  
|目标|防止后续的基类修改引入你具有已定义在派生类中的成员|通过定义的过程或属性具有相同调用的序列的不同实现来实现多态性<sup>1</sup>|  
|重新定义的元素|任何声明的元素类型|只有过程 (`Function`， `Sub`，或`Operator`) 或属性|  
|重新定义元素|任何声明的元素类型|过程或属性与相同的调用序列<sup>1</sup>|  
|重定义元素的访问级别|任何访问级别|不能更改重写元素的访问的级别|  
|提高可读性并对可写性重新定义元素|任意组合|不能更改可读性或可写性的重写的属性|  
|控制重定义|不能强制或禁止隐藏基类元素|基类元素可指定`MustOverride`， `NotOverridable`，或 `Overridable`|  
|关键字的用法|`Shadows` 在派生类; 建议`Shadows`假定如果既不`Shadows`也不`Overrides`指定<sup>2</sup>|`Overridable` 或`MustOverride`所需基类; 中`Overrides`在派生类中所需|  
|重新元素定义由派生类中派生的类的继承|通过继承隐藏元素进一步派生类;隐藏的元素仍隐藏<sup>3</sup>|通过重写元素继承进一步派生类;重写的元素仍中重写|  
  
 <sup>1</sup> *调用序列*包含元素类型 (`Function`， `Sub`， `Operator`，或`Property`)，名称、 参数列表和返回类型。 不能重写属性，或另一种方法解决过程。 不能重写一种类型的过程 (`Function`， `Sub`，或`Operator`) 与另一个类型。  
  
 <sup>2</sup>如果不指定`Shadows`或`Overrides`，编译器会发出警告消息，以帮助您确定要使用哪种类型的重定义。 如果忽略该警告，则使用隐藏的机制。  
  
 <sup>3</sup>隐藏元素不可进一步的派生类中，如果没有继承隐藏。 例如，如果声明隐藏元素为`Private`，从派生类派生一个类继承的原始元素而不是隐藏的元素。  
  
## <a name="guidelines"></a>准则  
 你通常使用重写在以下情况：  
  
-   你定义的多态的派生的类。  
  
-   你想让编译器强制执行相同的元素类型和调用的序列的安全性。  
  
 你通常使用隐藏在以下情况：  
  
-   您希望您的基类可能会被修改，并定义与您使用的相同名称的元素。  
  
-   你希望可以随意更改的元素类型或调用序列。  
  
## <a name="see-also"></a>请参阅  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [如何：隐藏与你的变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [如何：访问被派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
