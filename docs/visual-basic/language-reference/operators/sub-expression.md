---
title: Sub 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 602212e664fa3362742fb1ba0dc033610272d3af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603530"
---
# <a name="sub-expression-visual-basic"></a>Sub 表达式 (Visual Basic)
声明的参数和定义子例程 lambda 表达式的代码。  
  
## <a name="syntax"></a>语法  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`parameterlist`|可选。 表示的参数的过程的本地变量名称的列表。 括号必须存在，即使列表为空。 有关详细信息，请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`statement`|必须的。 一条语句。|  
|`statements`|必须的。 语句的列表。|  
  
## <a name="remarks"></a>备注  
 A *lambda 表达式*是不具有名称一个子例程，并执行一个或多个语句。 你可以任意位置使用 lambda 表达式，可用作委托类型，除外的自变量`RemoveHandler`。 有关委托，而使用与委托的 lambda 表达式的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。  
  
## <a name="lambda-expression-syntax"></a>Lambda 表达式语法  
 Lambda 表达式的语法类似于标准子例程。 差异如下所示：  
  
-   Lambda 表达式不具有名称。  
  
-   Lambda 表达式不能有修饰符，如`Overloads`或`Overrides`。  
  
-   单行 lambda 表达式的主体必须是一条语句，不能是表达式。 主体可以包含一个 sub 过程中，对的调用，但不是调用函数的过程。  
  
-   在 lambda 表达式，必须必须推断数据类型或所有参数指定所有参数。  
  
-   可选和`ParamArray`lambda 表达式中不允许使用参数。  
  
-   在 lambda 表达式中不允许泛型参数。  
  
## <a name="example"></a>示例  
 下面是一个值写入控制台 lambda 表达式的示例。 该示例显示的子程序这两个单行和多行 lambda 表达式语法。 有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)  
 [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
