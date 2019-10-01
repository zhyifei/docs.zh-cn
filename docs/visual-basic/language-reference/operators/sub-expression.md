---
title: Sub 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 2330b410f54b54d8f6cb7d8ad6f9b39a3f4d31bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701338"
---
# <a name="sub-expression-visual-basic"></a>Sub 表达式 (Visual Basic)
声明定义子程序 lambda 表达式的参数和代码。  
  
## <a name="syntax"></a>语法  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`parameterlist`|可选。 表示过程参数的局部变量名称的列表。 即使此列表为空，也必须存在括号。 有关更多信息，请参见 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`statement`|必需。 单个语句。|  
|`statements`|必需。 语句的列表。|  
  
## <a name="remarks"></a>备注  
 *Lambda 表达式*是不具有名称并执行一个或多个语句的子例程。 除了作为 `RemoveHandler` 的参数之外，你还可以在可以使用委托类型的任何位置使用 lambda 表达式。 有关委托的详细信息以及对委托使用 lambda 表达式的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。  
  
## <a name="lambda-expression-syntax"></a>Lambda 表达式语法  
 Lambda 表达式的语法与标准子例程的语法相似。 不同之处如下：  
  
- Lambda 表达式没有名称。  
  
- Lambda 表达式不能具有修饰符，如 `Overloads` 或 @no__t 为-1。  
  
- 单行 lambda 表达式的主体必须是语句，而不能是表达式。 正文可以包含对 sub 过程的调用，但不能由对函数过程的调用组成。  
  
- 在 lambda 表达式中，所有参数都必须具有指定的数据类型，或者必须推断所有参数。  
  
- Lambda 表达式中不允许使用可选的和 @no__t 的参数。  
  
- Lambda 表达式中不允许使用泛型参数。  
  
## <a name="example"></a>示例  
 下面是将值写入控制台的 lambda 表达式的示例。 该示例显示了子程序的单行和多行 lambda 表达式语法。 有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>请参阅

- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
- [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
