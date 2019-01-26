---
title: 函数&#39;&lt;过程名称&gt;&#39;没有&#39;t 上的所有代码路径都返回值
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: b6cc5143aafb6c2554b183a1fc5fb3b1331ec5d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552185"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>函数&#39;&lt;过程名称&gt;&#39;没有&#39;t 上的所有代码路径都返回值
函数\<过程名称 > 没有在所有代码路径上返回一个值。 是否缺少 Return 语句？  
  
 一个`Function`过程包含至少一个可能不会返回一个值的代码路径。  
  
 可以返回一个介于`Function`处于以下任一过程：  
  
-   包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。  
  
-   向其分配值`Function`过程名，然后执行`Exit Function`语句。  
  
-   向其分配值`Function`过程名，然后执行`End Function`语句。  
  
 控制权将传递给`Exit Function`或`End Function`和没有分配到过程名称的任何值，该过程返回的返回数据类型的默认值。 详细信息，请参阅"行为"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42105  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   检查控制流逻辑，并确保分配导致返回每个语句前的值。  
  
     它是更轻松地保证每个返回从过程返回一个值，如果始终使用`Return`语句。 如果之前的最后一个语句执行此操作，`End Function`应为`Return`语句。  
  
## <a name="see-also"></a>请参阅
- [Function 过程](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [“项目设计器”->“编译”页 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
