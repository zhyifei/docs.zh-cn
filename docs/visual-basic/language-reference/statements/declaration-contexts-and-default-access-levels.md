---
title: 声明上下文和默认访问级别 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: b30b1068fe662d5f0318a1712dc4690b79bd739d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605441"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>声明上下文和默认访问级别 (Visual Basic)
本主题介绍了哪些 Visual Basic 类型可声明内的其他类型，以及什么其访问级别默认为如果未指定。  
  
## <a name="declaration-context-levels"></a>声明上下文级别  
 *声明上下文*编程元素的是元素的声明它的代码区域。 这通常是另一个编程元素，然后调用*包含元素*。  
  
 声明上下文的级别如下所示：  
  
-   *Namespace 级别*— 在源文件或命名空间，但不是在类、 结构、 模块或接口  
  
-   *模块级别*— 在类、 结构、 模块或接口，但不是在过程或块  
  
-   *过程级别*-过程或块中 (如`If`或`For`)  
  
 下表显示各种已声明的编程元素，具体取决于其声明上下文的默认访问级别。  
  
|已声明的元素|Namespace 级别|模块级别|过程级别|  
|----------------------|---------------------|------------------|---------------------|  
|变量 ([Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md))|不允许|`Private` (`Public`中`Structure`、 中不允许`Interface`)|`Public`|  
|常量 ([Const 语句](../../../visual-basic/language-reference/statements/const-statement.md))|不允许|`Private` (`Public`中`Structure`、 中不允许`Interface`)|`Public`|  
|枚举 ([Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|不允许|  
|类 ([Class 语句](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|不允许|  
|结构 ([结构语句](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|不允许|  
|模块 ([模块语句](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|不允许|不允许|  
|接口 ([Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|不允许|  
|过程 ([函数语句](../../../visual-basic/language-reference/statements/function-statement.md)， [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md))|不允许|`Public`|不允许|  
|外部引用 ([声明语句](../../../visual-basic/language-reference/statements/declare-statement.md))|不允许|`Public` (不允许在`Interface`)|不允许|  
|运算符 ([Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md))|不允许|`Public` (不允许在`Interface`或`Module`)|不允许|  
|属性 ([属性语句](../../../visual-basic/language-reference/statements/property-statement.md))|不允许|`Public`|不允许|  
|默认属性 ([默认](../../../visual-basic/language-reference/modifiers/default.md))|不允许|`Public` (不允许在`Module`)|不允许|  
|事件 ([Event 语句](../../../visual-basic/language-reference/statements/event-statement.md))|不允许|`Public`|不允许|  
|委托 ([Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|不允许|  
  
 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="see-also"></a>请参阅  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)
