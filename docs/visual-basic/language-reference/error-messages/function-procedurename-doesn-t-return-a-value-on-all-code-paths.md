---
title: 函数&#39;&lt;过程名称&gt;&#39;不&#39;t 在所有代码路径上返回值
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 4c18c6229eb170e8a688aaa2734ae8fbfa081061
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>函数&#39;&lt;过程名称&gt;&#39;不&#39;t 在所有代码路径上返回值
函数\<过程名称 > 没有在所有代码路径上返回一个值。 是否缺少 Return 语句？  
  
 A`Function`过程有至少一个通过其代码不会返回一个值的可能路径。  
  
 你可以返回一个介于`Function`处于以下任一过程：  
  
-   包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。  
  
-   将值赋给`Function`过程名，然后执行`Exit Function`语句。  
  
-   将值赋给`Function`过程名，然后执行`End Function`语句。  
  
 如果控制权传递给`Exit Function`或`End Function`和未将任何值分配到过程名称，该过程返回的返回数据类型的默认值。 有关详细信息，请参阅"行为" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42105  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   请检查控制流逻辑并确保导致返回每个语句之前赋值。  
  
     很容易地保证每个返回从过程返回一个值，如果始终使用`Return`语句。 如果你这样做，请在之前的最后一个语句`End Function`应`Return`语句。  
  
## <a name="see-also"></a>请参阅  
 [Function 过程](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [“项目设计器”->“编译”页 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
