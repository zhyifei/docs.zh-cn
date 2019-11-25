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
This topic describes which Visual Basic types can be declared within which other types, and what their access levels default to if not specified.  
  
## <a name="declaration-context-levels"></a>Declaration Context Levels  
 The *declaration context* of a programming element is the region of code in which it is declared. This is often another programming element, which is then called the *containing element*.  
  
 The levels for declaration contexts are the following:  
  
- *Namespace level* — within a source file or namespace but not within a class, structure, module, or interface  
  
- *Module level* — within a class, structure, module, or interface but not within a procedure or block  
  
- *Procedure level* — within a procedure or block (such as `If` or `For`)  
  
 The following table shows the default access levels for various declared programming elements, depending on their declaration contexts.  
  
|已声明的元素|Namespace level|Module level|Procedure level|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md))|不允许|`Private` (`Public` in `Structure`, not allowed in `Interface`)|`Public`|  
|Constant ([Const Statement](../../../visual-basic/language-reference/statements/const-statement.md))|不允许|`Private` (`Public` in `Structure`, not allowed in `Interface`)|`Public`|  
|Enumeration ([Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|不允许|  
|Class ([Class Statement](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|不允许|  
|Structure ([Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|不允许|  
|Module ([Module Statement](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|不允许|不允许|  
|Interface ([Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|不允许|  
|Procedure ([Function Statement](../../../visual-basic/language-reference/statements/function-statement.md), [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md))|不允许|`Public`|不允许|  
|External reference ([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md))|不允许|`Public` (not allowed in `Interface`)|不允许|  
|Operator ([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md))|不允许|`Public` (not allowed in `Interface` or `Module`)|不允许|  
|Property ([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md))|不允许|`Public`|不允许|  
|Default property ([Default](../../../visual-basic/language-reference/modifiers/default.md))|不允许|`Public` (not allowed in `Module`)|不允许|  
|Event ([Event Statement](../../../visual-basic/language-reference/statements/event-statement.md))|不允许|`Public`|不允许|  
|Delegate ([Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|不允许|  
  
 For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>请参阅

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [COMClassAttribute](../../../visual-basic/language-reference/modifiers/public.md)
