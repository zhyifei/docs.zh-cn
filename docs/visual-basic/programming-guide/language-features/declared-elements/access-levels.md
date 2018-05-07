---
title: Visual Basic 中的访问级别
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 6f8fda62e468e3735e3ae36afdebe440a8e4bc04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="access-levels-in-visual-basic"></a>Visual Basic 中的访问级别
*访问级别*的已声明的元素是能够访问它的范围，哪些代码，即有权读取或写入到它。 这确定如何声明元素本身，不仅还由元素的容器的访问级别。 无法访问包含元素的代码不能访问任何其包含的元素，甚至那些声明为`Public`。 例如，`Public`变量中`Private`结构可以从访问，在类中包含表的结构，但不是能从该类的外部。  
  
## <a name="public"></a>Public  
 [公共](../../../../visual-basic/language-reference/modifiers/public.md)关键字声明语句中的指定从任何位置中同一项目的代码、 其他引用该项目的项目和项目中生成的任何程序集可以访问的元素。 下面的代码显示了一个示例`Public`声明。  
  
```  
Public Class classForEverybody  
```  
  
 你可以使用`Public`只能在模块、 接口或命名空间级别。 这意味着你可以声明中的源文件或命名空间，或在接口、 模块、 类或结构，但不是能在过程级别公共元素。  
  
## <a name="protected"></a>Protected  
 [受保护](../../../../visual-basic/language-reference/modifiers/protected.md)关键字声明语句中的指定在相同的类中，或从派生自此类的类可以仅从访问的元素。 下面的代码显示了一个示例`Protected`声明。  
  
```  
Protected Class classForMyHeirs  
```  
  
 你可以使用`Protected`只能在类级别，且仅当你声明一个类的成员。 这意味着你可以声明受保护的元素在类中，但不是能在源文件或命名空间，或在接口、 模块、 结构或过程内的级别。  
  
## <a name="friend"></a>Friend  
 [友元](../../../../visual-basic/language-reference/modifiers/friend.md)关键字声明语句中的指定元素，可以从同一程序集中，而不是从访问程序集外部的。 下面的代码显示了一个示例`Friend`声明。  
  
```  
Friend stringForThisProject As String  
```  
  
 你可以使用`Friend`只能在模块、 接口或命名空间级别。 这意味着你可以声明友元元素中的源文件或命名空间，或在接口、 模块、 类或结构，但不是能在过程级别。  
  
## <a name="protected-friend"></a>受保护的友元  
 `Protected`和`Friend`关键字一起在声明语句中指定的派生类中或在可以访问的元素和 / 或同一程序集中。 下面的代码显示了一个示例`Protected Friend`声明。  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 你可以使用`Protected Friend`只能在类级别，且仅当你声明一个类的成员。 这意味着你可以声明一个受保护的友元元素在类中，但不是能在源文件或命名空间，或在接口、 模块、 结构或过程内的级别。  
  
## <a name="private"></a>Private  
 [私有](../../../../visual-basic/language-reference/modifiers/private.md)关键字声明语句中的指定只能从相同模块、 类或结构中，可以访问的元素。 下面的代码显示了一个示例`Private`声明。  
  
```  
Private numberForMeOnly As Integer  
```  
  
 只能在模块级别使用 `Private`。 这意味着你可以声明一个私有元素内模块、 类或结构，但不是能在源文件或命名空间，内部接口，或在过程中的级别。  
  
 在模块级别`Dim`不含任何访问级别关键字的语句是等效于`Private`声明。 但是，你可能想要使用`Private`关键字，以使代码更易于读取和解释。  
  
## <a name="access-modifiers"></a>访问修饰符  
 指定的访问级别的关键字称为*访问修饰符*。 下表比较的访问修饰符。  
  
|访问修饰符|授予的访问级别|可以使用此访问级别声明的元素|可以在其中使用此修饰符声明上下文|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|不受限制:<br /><br /> 任何可以看到公共元素的代码可以访问它|接口<br /><br /> 模块<br /><br /> 类<br /><br /> 结构<br /><br /> 结构成员<br /><br /> 过程<br /><br /> 属性<br /><br /> 成员变量<br /><br /> 常量<br /><br /> 枚举<br /><br /> 事件<br /><br /> 外部声明<br /><br /> 委托|源文件<br /><br /> 命名空间<br /><br /> 接口<br /><br /> 模块<br /><br /> 类<br /><br /> 结构|  
|`Protected`|派生：<br /><br /> 声明一个受保护的元素或从中派生的类可以访问的元素的类中的代码|接口<br /><br /> 类<br /><br /> 结构<br /><br /> 过程<br /><br /> 属性<br /><br /> 成员变量<br /><br /> 常量<br /><br /> 枚举<br /><br /> 事件<br /><br /> 外部声明<br /><br /> 委托|类|  
|`Friend`|程序集：<br /><br /> 声明友元元素可以访问它的程序集内的代码|接口<br /><br /> 模块<br /><br /> 类<br /><br /> 结构<br /><br /> 结构成员<br /><br /> 过程<br /><br /> 属性<br /><br /> 成员变量<br /><br /> 常量<br /><br /> 枚举<br /><br /> 事件<br /><br /> 外部声明<br /><br /> 委托|源文件<br /><br /> 命名空间<br /><br /> 接口<br /><br /> 模块<br /><br /> 类<br /><br /> 结构|  
|`Protected` `Friend`|联合的`Protected`和`Friend`:<br /><br /> 在同一个类或相同的程序集用作受保护的友元元素，或从元素的类派生的任何类中的代码，可以访问它|接口<br /><br /> 类<br /><br /> 结构<br /><br /> 过程<br /><br /> 属性<br /><br /> 成员变量<br /><br /> 常量<br /><br /> 枚举<br /><br /> 事件<br /><br /> 外部声明<br /><br /> 委托|类|  
|`Private`|声明上下文：<br /><br /> 声明一个私有元素，包括中包含的类型的代码可以访问的元素的类型中的代码|接口<br /><br /> 类<br /><br /> 结构<br /><br /> 结构成员<br /><br /> 过程<br /><br /> 属性<br /><br /> 成员变量<br /><br /> 常量<br /><br /> 枚举<br /><br /> 事件<br /><br /> 外部声明<br /><br /> 委托|模块<br /><br /> 类<br /><br /> 结构|  
  
## <a name="see-also"></a>请参阅  
 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [在 Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [如何：控制变量的可用性](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)  
 [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
