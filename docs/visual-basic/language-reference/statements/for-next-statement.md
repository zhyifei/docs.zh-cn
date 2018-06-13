---
title: For...Next 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 8c54189499b7d5b52cf93b4a0ae6cc47356bf57e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605324"
---
# <a name="fornext-statement-visual-basic"></a>For...Next 语句 (Visual Basic)
将一组语句重复指定的次数。  
  
## <a name="syntax"></a>语法  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a>部件  
  
|部件|描述|  
|----------|-----------------|  
|`counter`|中所需`For`语句。 数值变量。 For 循环控制变量。 有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。|  
|`datatype`|可选。 数据类型的`counter`。 有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。|  
|`start`|必须的。 数值表达式。 `counter` 的初始值。|  
|`end`|必须的。 数值表达式。 最终值`counter`。|  
|`step`|可选。 数值表达式。 依据的数量`counter`执行循环时，每次都会递增。|  
|`statements`|可选。 一个或多个语句之间`For`和`Next`运行指定的次数。|  
|`Continue For`|可选。 将控制转移到下一步的循环迭代。|  
|`Exit For`|可选。 将扩展的控制转移`For`循环。|  
|`Next`|必须的。 终止的定义`For`循环。|  
  
> [!NOTE]
>  `To`关键字用于在此语句中指定计数器的范围。 你还可以使用此关键字在[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)和数组声明中。 有关数组声明的详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。  
  
## <a name="simple-examples"></a>简单的示例  
 你使用`For`...`Next`结构时要重复次数的一组语句。  
  
 在下面的示例中，`index`变量开头的值为 1，并与每个迭代循环，结束后的值递增`index`达到 5。  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 在下面的示例中，`number`变量从 2 开始，并通过循环，结束后的值的每个迭代上的 0.25 减少`number`达到 0。 `Step`参数`-.25`降低 0.25 循环的每个迭代上的值。  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  A[时...While 语句结束](../../../visual-basic/language-reference/statements/while-end-while-statement.md)或[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)可以有效地工作时你不知道提前多少次，以在循环中运行语句。 但是，如果你希望运行特定次数的循环`For`...`Next`循环是更好的选择。 当您首次进入循环时确定迭代的数。  
  
## <a name="nesting-loops"></a>嵌套循环  
 可以嵌套`For`置于另一个循环内的循环。 下面的示例演示嵌套`For`...`Next`具有不同的单步值的结构。 外部循环创建循环的每次迭代的字符串。 内部循环递减循环的每次迭代循环计数器变量。  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 每个循环时嵌套循环，必须具有唯一`counter`变量。  
  
 你可嵌套不同类型控制结构彼此内部。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-for-and-continue-for"></a>退出的针对并继续  
 `Exit For`语句将立即退出`For`...`Next` 到后面的语句的循环，并将控制权`Next`语句。  
  
 `Continue For`语句将控制权立即到循环的下一个迭代。 有关详细信息，请参阅[继续语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
 下面的示例演示如何使用`Continue For`和`Exit For`语句。  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 你可以放置任意数量的`Exit For`中的语句`For`...`Next` 循环。 当使用内嵌套`For`...`Next` 循环，`Exit For`退出最内层的循环，并将控制转移到下一步较高级别的嵌套。  
  
 `Exit For` 后你评估一些条件通常使用 (例如，在`If`...`Then`...`Else`结构)。 你可能想要使用`Exit For`在以下情况：  
  
-   继续循环是不必要或无法完成。 错误的值或终止请求可能要创建此条件。  
  
-   A `Try`...`Catch`...`Finally`语句会捕捉异常。 你可以使用`Exit For`末尾`Finally`块。  
  
-   具有无限循环，即无法运行大型或甚至无限数量的次数的循环。 如果检测到此类条件，则可以使用`Exit For`来退出循环。 有关详细信息，请参阅[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。  
  
## <a name="technical-implementation"></a>技术实现  
 当`For`...`Next`循环开始，Visual Basic 的计算结果`start`， `end`，和`step`。 Visual Basic 计算这些值仅在此时间，然后将分配`start`到`counter`。 在之前的语句块将运行，Visual Basic 比较`counter`到`end`。 如果`counter`已大于`end`值 (或较小如果`step`为负)，则`For`循环结束并将控制权传递到后面的语句`Next`语句。 否则，在运行此语句块。  
  
 每次 Visual Basic 遇到`Next`语句，都将增大`counter`通过`step`并返回到`For`语句。 它将再次比较`counter`到`end`，并再次运行块或者退出循环，具体取决于结果。 此过程将继续，直至`counter`传递`end`或`Exit For`遇到语句。  
  
 循环不会阻止直到`counter`经过`end`。 如果`counter`等同于`end`，循环继续。 确定是否运行块的比较是`counter`  <=  `end`如果`step`为正和`counter`  >=  `end`如果`step`为负。  
  
 如果你更改的值`counter`循环内, 你的代码可能会更难读取和调试。 更改的值`start`， `end`，或`step`不会影响已确定第一次键入循环的迭代值。  
  
 如果嵌套循环，编译器将发出错误信号它是否会遇到`Next`语句之前外部嵌套级别`Next`内部级别的语句。 但是，编译器可以检测到这只有在指定重叠错误`counter`中每个`Next`语句。  
  
### <a name="step-argument"></a>步骤参数  
 值`step`可以是正数或负数。 此参数确定循环处理根据下表：  
  
|**步长值**|**循环执行的条件**|  
|--------------------|--------------------------|  
|正或零|`counter` <= `end`|  
|负数|`counter` >= `end`|  
  
 默认值`step`为 1。  
  
###  <a name="BKMK_Counter"></a> 计数器自变量  
 下表指示是否`counter`定义新的本地变量为作用域为整个`For…Next`循环。 此决定取决于是否`datatype`存在以及是否`counter`已定义。  
  
|是`datatype`存在？|是`counter`已定义？|结果 (是否`counter`定义新的本地变量为作用域为整个`For...Next`循环)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|否|是|否，因为`counter`已定义。 如果的作用域`counter`不在本地进行过程： 出现编译时警告。|  
|否|否|可以。 数据类型，则从推断`start`， `end`，和`step`表达式。 类型推理有关的信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。|  
|是|是|是，但仅当现有`counter`外部过程定义变量。 该变量保持独立。 如果现有的作用域`counter`变量是本地的过程，则发生编译时错误。|  
|是|否|可以。|  
  
 数据类型`counter`确定的一种迭代中，它必须是以下类型之一：  
  
-   A `Byte`， `SByte`， `UShort`， `Short`， `UInteger`， `Integer`， `ULong`， `Long`， `Decimal`， `Single`，或`Double`。  
  
-   可使用声明的枚举[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。  
  
-   一个 `Object`。  
  
-   一种类型`T`具有以下运算符，其中`B`是一种可在`Boolean`表达式。  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 你可以选择指定`counter`变量中`Next`语句。 此语法提高您的程序的可读性，尤其是在具有嵌套`For`循环。 必须在相应指定出现的变量`For`语句。  
  
 `start`， `end`，和`step`表达式可以计算为任何数据类型扩大到的一种`counter`。 如果你使用的用户定义类型`counter`，可能需要定义`CType`转换运算符以转换的类型`start`， `end`，或`step`为的类型`counter`。  
  
## <a name="example"></a>示例  
 下面的示例从泛型列表中移除所有元素。 而不是[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)的示例所示`For`...`Next`循环以降序顺序的语句。 该示例使用此技术，因为`removeAt`方法将导致触发 after 已删除的元素具有较低的索引值的元素。  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a>示例  
 下面的示例循环访问一个枚举，通过使用声明[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a>示例  
 在下面的示例中，语句参数使用具有运算符重载的类`+`， `-`， `>=`，和`<=`运算符。  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Collections.Generic.List%601>  
 [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [集合](../../programming-guide/concepts/collections.md)
