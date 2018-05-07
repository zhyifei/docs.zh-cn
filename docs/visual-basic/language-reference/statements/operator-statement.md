---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="operator-statement"></a>Operator Statement
声明运算符，操作数，并在类或结构定义运算符过程的代码。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>部件  
 `attrlist`  
 可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。  
  
 `Public`  
 必须的。 指示此运算符过程具有[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。  
  
 `Overloads`  
 可选。 请参阅[重载](../../../visual-basic/language-reference/modifiers/overloads.md)。  
  
 `Shared`  
 必须的。 指示此运算符过程是[共享](../../../visual-basic/language-reference/modifiers/shared.md)过程。  
  
 `Shadows`  
 可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。  
  
 `Widening`  
 除非另行指定，所需的转换运算符`Narrowing`。 指示此运算符过程定义[Widening](../../../visual-basic/language-reference/modifiers/widening.md)转换。 此帮助页上，请参见"扩大转换和收缩转换"。  
  
 `Narrowing`  
 除非另行指定，所需的转换运算符`Widening`。 指示此运算符过程定义[Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)转换。 此帮助页上，请参见"扩大转换和收缩转换"。  
  
 `operatorsymbol`  
 必须的。 符号或运算符的此运算符过程所定义的标识符。  
  
 `operand1`  
 必须的。 名称和的一元运算符 （包括转换运算符） 的单个操作数或二元运算符的左的操作数的类型。  
  
 `operand2`  
 所需的二元运算符。 名称和二元运算符的右操作数的类型。  
  
 `operand1` 和`operand2`具有以下语法和部件：  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|部件|描述|  
|----------|-----------------|  
|`ByVal`|可选，但的传递机制必须[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。|  
|`operandname`|必须的。 表示此操作数的变量的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`operandtype`|可选除非`Option Strict`是`On`。 此操作数的数据类型。|  
  
 `type`  
 可选除非`Option Strict`是`On`。 运算符过程的值的数据类型返回。  
  
 `statements`  
 可选。 运算符过程运行的语句块。  
  
 `returnvalue`  
 必须的。 运算符过程返回到调用代码的值。  
  
 `End` `Operator`  
 必须的。 终止此运算符过程的定义。  
  
## <a name="remarks"></a>备注  
 你可以使用`Operator`只能在类或结构中。 这意味着*声明上下文*运算符不能是源文件、 命名空间、 模块、 接口、 过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 所有运算符必须都是`Public Shared`。 不能指定`ByRef`， `Optional`，或`ParamArray`为其中一个操作数。  
  
 不能使用运算符或标识符保留返回值。 必须使用`Return`语句，并且它必须指定一个值。 任意数量的`Return`语句可以在过程中任何位置显示。  
  
 以这种方式定义一个运算符调用*运算符重载*，而无论你使用`Overloads`关键字。 下表列出了可定义的运算符。  
  
|类型|运算符|  
|----------|---------------|  
|一元|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|二进制|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|转换（一元）|`CType`|  
  
 请注意，`=`二元列表中的运算符是比较运算符，而不是赋值运算符。  
  
 在定义`CType`，您必须指定`Widening`或`Narrowing`。  
  
## <a name="matched-pairs"></a>匹配的对  
 你必须定义匹配对某些运算符。 如果定义此类对任一运算符时，必须定义对其他。 匹配的对如下所示：  
  
-   `=` 和 `<>`  
  
-   `>` 和 `<`  
  
-   `>=` 和 `<=`  
  
-   `IsTrue` 和 `IsFalse`  
  
## <a name="data-type-restrictions"></a>数据类型限制  
 你定义每个运算符必须包含在其上定义的类或结构。 这意味着类或结构必须显示为以下数据类型：  
  
-   一元运算符的操作数。  
  
-   至少一个二元运算符的操作数。  
  
-   操作数或转换运算符的返回类型。  
  
 某些运算符具有额外的数据类型限制，如下所示：  
  
-   如果你定义`IsTrue`和`IsFalse`运算符，它们必须都返回`Boolean`类型。  
  
-   如果你定义`<<`和`>>`运算符，它们必须同时指定`Integer`键入`operandtype`的`operand2`。  
  
 返回类型没有对应于其中一个操作数的类型。 例如，如一个比较运算符`=`或`<>`可以返回`Boolean`即使两个操作数是`Boolean`。  
  
## <a name="logical-and-bitwise-operators"></a>逻辑和按位运算符  
 `And`， `Or`， `Not`，和`Xor`运算符可以在 Visual Basic 中执行逻辑或位运算。 但是，如果你在类或结构上定义这些运算符之一，你可以定义仅其按位运算。  
  
 不能定义`AndAlso`直接与运算符`Operator`语句。 但是，你可以使用`AndAlso`如果你已满足以下条件：  
  
-   已定义`And`在你想要用于对同一操作数类型`AndAlso`。  
  
-   你定义`And`返回与在其上定义它的类或结构相同的类型。  
  
-   已定义`IsFalse`运算符在其上具有定义的类或结构`And`。  
  
 同样，你可以使用`OrElse`如果已定义`Or`对相同的操作数与返回类型的类或结构，并且你已定义`IsTrue`在类或结构上。  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 A*扩大转换*在运行时，始终成功时*收缩转换*可以在运行时失败。 有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。  
  
 如果声明转换过程要`Widening`，过程代码一定不会产生任何故障。 这意味着：  
  
-   它必须始终返回类型的有效值`type`。  
  
-   它必须处理所有可能的异常和其他错误条件。  
  
-   它必须处理从它调用任何过程返回的任何错误。  
  
 如果没有任何可能转换过程可能不成功，或者它可能会导致未经处理的异常，必须将其声明`Narrowing`。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Operator`语句以定义一个结构，其中包括运算符的过程的轮廓`And`， `Or`， `IsFalse`，和`IsTrue`运算符。 `And` 和`Or`每个都采用类型的两个操作数`abc`和返回类型`abc`。 `IsFalse` 和`IsTrue`个各自采用单个类型的操作数的`abc`并返回`Boolean`。 这些定义使调用代码以使用`And`， `AndAlso`， `Or`，和`OrElse`类型操作数`abc`。  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [如何：调用运算符过程](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [如何：使用定义运算符的类](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
