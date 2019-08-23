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
ms.openlocfilehash: 9a9aed51f6d7bf3233e6e89116b8209b22f3d15d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912408"
---
# <a name="fornext-statement-visual-basic"></a>For...Next 语句 (Visual Basic)
按指定次数重复一组语句。  
  
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
|`counter`|`For`语句中必需。 数值变量。 循环的控制变量。 有关详细信息, 请参阅本主题后面的[计数器参数](#BKMK_Counter)。|  
|`datatype`|可选。 的`counter`数据类型。 有关详细信息, 请参阅本主题后面的[计数器参数](#BKMK_Counter)。|  
|`start`|必需。 数值表达式。 `counter` 的初始值。|  
|`end`|必需。 数值表达式。 的最终值`counter`。|  
|`step`|可选。 数值表达式。 每次通过循环`counter`增加的量。|  
|`statements`|可选。 `For` 与`Next`之间运行指定次数的一个或多个语句。|  
|`Continue For`|可选。 将控制转移到下一个循环迭代。|  
|`Exit For`|可选。 将控制转移到`For`循环外。|  
|`Next`|必需。 终止`For`循环的定义。|  
  
> [!NOTE]
> 此语句使用关键字来指定计数器的范围。 `To` 你还可以在[Select 。Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)和数组声明。 有关数组声明的详细信息, 请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。  
  
## <a name="simple-examples"></a>简单示例  
 使用`For`。`Next`当您想要将一组语句重复一组次数时的结构。  
  
 在下面的示例中, `index`变量的值为 1, 并与循环的每次迭代递增, 在的`index`值达到5之后结束。  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 在下面的示例中, `number`变量从2开始, 在循环的每次迭代后减 0.25, 截止值为`number` 0。 的`Step` 自变量会在循环的每次迭代时`-.25`减少值0.25。  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  ... [End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)或[Do 。](../../../visual-basic/language-reference/statements/do-loop-statement.md)当您事先不知道在循环中运行语句的次数时, Loop 语句可以正常工作。 但是, 当你希望将循环运行特定次数时, `For`。`Next`循环是更好的选择。 您在第一次进入循环时确定迭代次数。  
  
## <a name="nesting-loops"></a>嵌套循环  
 可以通过在`For`另一个循环中放置循环来嵌套循环。 下面的示例演示了`For`嵌套 。`Next`具有不同步长值的结构。 外部循环为循环的每次迭代创建字符串。 内部循环为循环的每次迭代递减循环计数器变量。  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 嵌套循环时, 每个循环必须具有唯一`counter`变量。  
  
 你还可以在彼此之间嵌套不同种类的控制结构。 有关详细信息, 请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-for-and-continue-for"></a>退出并继续进行  
 `Exit For`语句立即`For`退出 。`Next` 循环并将控制转移到`Next`语句后面的语句。  
  
 `Continue For`语句将控制立即传输到循环的下一次迭代。 有关详细信息, 请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
 下面的示例演示如何使用`Continue For`和`Exit For`语句。  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 可以将任意数量的`Exit For`语句`For`放入 。`Next` 圈. 当在嵌套`For`。`Next` 循环, `Exit For`退出最内层的循环, 并将控制转移到下一个更高的嵌套级别。  
  
 `Exit For`在你计算某个条件 (例如, 在`If`。`Then`...`Else`结构)。 你可能想要将`Exit For`用于以下情况:  
  
- 不需要继续循环访问。 错误的值或终止请求可能会创建此条件。  
  
- `Try`。`Catch`...`Finally`语句捕获异常。 可以在`Finally`块`Exit For`的末尾使用。  
  
- 您有一个无限循环, 该循环是一种循环, 它可以运行很大甚至无限次。 如果检测到这种情况, 则可以使用`Exit For`来转义循环。 有关详细信息, 请参阅[Do 。循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。  
  
## <a name="technical-implementation"></a>技术实现  
 `For`当 。循环开始, Visual Basic 计算`start`、 `end`和`step`。 `Next` Visual Basic 此时仅计算这些值, 然后将赋值`start`给。 `counter` 在语句块运行之前, Visual Basic 与`counter` `end`进行比较。 `counter` `Next` `For`如果已大于`step`值 (如果为负, 则为较小的值), 循环将结束并控制传递到语句后面的语句。 `end` 否则, 语句块将运行。  
  
 每`Next`次 Visual Basic 遇到语句时, 它会`counter` `step`递增并返回到`For`语句。 同样`end`, 它`counter`与进行比较, 并再次运行该块或退出循环, 具体取决于结果。 此过程将一直`counter`继续`end` , 直到`Exit For`遇到传递或语句。  
  
 直到经过传递`end`后循环`counter`才会停止。 `counter` 如果`end`等于, 则循环将继续。 确定`counter`是否运行块 <=  `end` 的比较`end`是否为正且`counter`  >= 为负。`step` `step`  
  
 如果在循环内更改的`counter`值, 则可能会更难读取和调试代码。 更改`start`、 `end`或的值不会影响在第一次输入循环时确定的迭代值。`step`  
  
 如果嵌套循环, 编译器在内部级别的`Next` `Next`语句之前遇到外部嵌套级别的语句时, 会发出错误信号。 但是, 只有在每个`counter` `Next`语句中指定时, 编译器才能检测到此重叠错误。  
  
### <a name="step-argument"></a>步骤参数  
 的`step`值可以是正数也可以是负数。 此参数根据下表确定循环处理:  
  
|**步骤值**|**如果**|  
|--------------------|--------------------------|  
|正或零|`counter` <= `end`|  
|负数|`counter` >= `end`|  
  
 的默认值`step`为1。  
  
### <a name="BKMK_Counter"></a>计数器参数  
 下表指示是否`counter`定义了作用域为整个`For…Next`循环的新局部变量。 此确定取决于`datatype`是否存在以及是否`counter`已定义。  
  
|是否`datatype`存在？|`counter`已定义？|Result (是否`counter`定义一个作用域为整个`For...Next`循环的新局部变量)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|No|是|不是, `counter`因为已定义。 如果该过程的`counter`作用域不是本地的, 则会发生编译时警告。|  
|No|No|可以。 数据类型是从`start`、 `end`和`step`表达式中推断出来的。 有关类型推理的信息, 请参阅[选项推断语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。|  
|是|是|是, 但仅当现有变量`counter`在过程外定义时才存在。 该变量保持独立。 如果现有`counter`变量的作用域是过程的本地值, 则会发生编译时错误。|  
|是|No|可以。|  
  
 的数据类型`counter`确定迭代的类型, 该类型必须是以下类型之一:  
  
- `Byte` 、`SByte` 、、`UInteger`、、 、`ULong`、 、、`Double`或。`Single` `Long` `Short` `UShort` `Integer` `Decimal`  
  
- 使用[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)声明的枚举。  
  
- 一个 `Object`。  
  
- 具有以下`T`运算符的类型, 其中`B`是`Boolean`可在表达式中使用的类型。  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 您可以选择`Next`在语句`counter`中指定变量。 此语法可提高程序的可读性, 尤其是在具有嵌套`For`循环的情况下。 您必须指定出现在相应`For`语句中的变量。  
  
 、 `start`和表达式`step`的计算结果可以是扩大到类型的`counter`任何数据类型。 `end` 如果对`counter`使用用户定义的类型, 则可能需要`CType`定义转换运算符`start`, 以将、 `end`或`step`的类型转换为类型`counter`。  
  
## <a name="example"></a>示例  
 下面的示例从泛型列表中移除所有元素。 而不是[为每个 。下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md), 示例显示`For`。`Next`按降序循环访问的语句。 该示例使用此方法, 因为`removeAt`方法会使删除的元素之后的元素具有更低的索引值。  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>示例  
 下面的示例循环访问通过使用[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)声明的枚举。  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>示例  
 在下面的示例中, 语句参数`+`使用具有`>=`、 `-`、和`<=`运算符的运算符重载的类。  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Collections.Generic.List%601>
- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [集合](../../programming-guide/concepts/collections.md)
