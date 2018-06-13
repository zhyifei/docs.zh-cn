---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: f88020c7407fb9c91e06bc2ee177773171e344fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599299"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
指定调用该过程时，可以省略过程自变量。  
  
## <a name="remarks"></a>备注  
 对于每个可选参数，你必须作为该参数的默认值指定的常量表达式。 如果表达式计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，值数据类型的默认值用作参数的默认值。  
  
 如果参数列表包含一个可选参数，则它后面的每个参数还必须是可选的。  
  
 `Optional` 修饰符可用于下面的上下文中：  
  
-   [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  当调用过程使用或不带可选参数，您可以按位置或按名称传递自变量。 有关详细信息，请参阅[按位置和按名称传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)。  
  
> [!NOTE]
>  你还可以通过使用重载定义带可选参数的过程。 如果你有一个可选参数，你可以定义过程，一个接受参数，一个不的两个重载的的版本。 有关详细信息，请参阅[过程重载](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。  
  
## <a name="example"></a>示例  
 下面的示例定义了具有一个可选参数的过程。  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何调用按位置传递自变量和自变量按名称传递过程。 过程有两个可选参数。  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
