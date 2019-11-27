---
title: 声明上下文和默认访问级别
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354105"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>声明上下文和默认访问级别 (Visual Basic)
本主题介绍了哪些 Visual Basic 类型可以在哪些其他类型中进行声明，如果未指定，它们的访问级别将默认为。  
  
## <a name="declaration-context-levels"></a>声明上下文级别  
 编程元素的*声明上下文*是声明它的代码区域。 这通常是另一个编程元素，该元素称为 "*包含元素*"。  
  
 声明上下文的级别如下：  
  
- *命名空间级别*-在源文件或命名空间中，但不在类、结构、模块或接口中  
  
- *模块级别*-在类、结构、模块或接口中，但不在过程或块中  
  
- *过程级别*-在过程或块（如 `If` 或 `For`）内  
  
 下表显示了各种已声明的编程元素的默认访问级别，具体取决于它们的声明上下文。  
  
|已声明的元素|命名空间级别|模块级别|过程级别|  
|----------------------|---------------------|------------------|---------------------|  
|Variable （[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)）|不允许|`Private` （`Public` `Structure`，但 `Interface`中不允许）|`Public`|  
|常量（[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)）|不允许|`Private` （`Public` `Structure`，但 `Interface`中不允许）|`Public`|  
|枚举（[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)）|`Friend`|`Public`|不允许|  
|Class （[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)）|`Friend`|`Public`|不允许|  
|Structure （[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)）|`Friend`|`Public`|不允许|  
|Module （[Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)）|`Friend`|不允许|不允许|  
|Interface （[Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)）|`Friend`|`Public`|不允许|  
|Procedure （[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)， [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)）|不允许|`Public`|不允许|  
|外部引用（[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)）|不允许|`Public` （`Interface`不允许）|不允许|  
|运算符（[Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)）|不允许|`Public` （不允许 `Interface` 或 `Module`）|不允许|  
|属性（[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)）|不允许|`Public`|不允许|  
|Default 属性（[默认值](../../../visual-basic/language-reference/modifiers/default.md)）|不允许|`Public` （`Module`不允许）|不允许|  
|事件（[事件语句](../../../visual-basic/language-reference/statements/event-statement.md)）|不允许|`Public`|不允许|  
|委托（[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)）|`Friend`|`Public`|不允许|  
  
 有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="see-also"></a>另请参阅

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
