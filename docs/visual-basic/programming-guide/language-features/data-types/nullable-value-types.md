---
title: 可以为 Null 的值类型 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16df20be89a88aa68e06692594c208cee1ab2dea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="nullable-value-types-visual-basic"></a>可以为 Null 的值类型 (Visual Basic)
有时，你将使用在某些情况下没有已定义的值的值类型。 例如，数据库中的字段可能需要区分具有有意义的分配的值并不具有分配的值。 可以扩展值类型，以使其正常值或 null 值。 调用此类扩展*可以为 null 的类型*。  
  
 每个可以为 null 的类型从泛型构造<xref:System.Nullable%601>结构。 请考虑跟踪与工作相关的活动的数据库。 下面的示例构造一个可以为 null`Boolean`类型，并声明该类型的变量。 你可以通过三种方式编写声明：  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 变量`ridesBusToWork`可以保存的值`True`，值为`False`，或根本没有值。 其初始的默认值为没有值，这在此情况下可能意味着，信息具有尚未获得此人。 与此相反，`False`可能是获得的信息，而此人乘坐工作的总线不公共。  
  
 可以使用可以为 null 的类型来声明变量和属性，而您可以声明包含 null 的类型的元素的数组。 你可以使用作为参数，可以为 null 的类型声明过程并可以返回 null 的类型从`Function`过程。  
  
 无法构造 null 的类型，如数组、 一个引用类型上`String`，或类。 基础类型必须是值类型。 有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。  
  
## <a name="using-a-nullable-type-variable"></a>使用可以为 Null 的类型变量  
 可以为 null 的类型的最重要成员是其<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>属性。 变量的 null 的类型，<xref:System.Nullable%601.HasValue%2A>告知你此变量是否包含已定义的值。 如果<xref:System.Nullable%601.HasValue%2A>是`True`，你可以读取的值从<xref:System.Nullable%601.Value%2A>。 请注意，同时<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>是`ReadOnly`属性。  
  
### <a name="default-values"></a>默认值  
 当你声明一个具有变量可以为 null 的类型，其<xref:System.Nullable%601.HasValue%2A>属性具有默认值为`False`。 这意味着，默认情况下变量没有任何定义的值，而不是其基础值类型的默认值。 在下面的示例中，变量`numberOfChildren`最初具有任何定义的值，即使的默认值`Integer`类型为 0。  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 空值是用来表示未定义的或未知的值。 如果`numberOfChildren`假如被声明为`Integer`，将有可能表示信息不是当前可用的任何值。  
  
### <a name="storing-values"></a>将值存储  
 在典型的方式中，可以在变量或可以为 null 的类型的属性中存储值。 下面的示例将一个值分配给变量`numberOfChildren`声明在前面的示例。  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 如果变量或可以为 null 的类型的属性包含已定义的值，则可以使此可恢复到其初始状态，即未获分配的值。 执行此操作通过设置变量或属性`Nothing`，如下面的示例所示。  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  尽管你可以分配`Nothing`到可以为 null 的类型的变量，不能对其进行测试的`Nothing`使用等号。 比较过程中使用等号， `someVar = Nothing`，始终评估为`Nothing`。 你可以测试变量的<xref:System.Nullable%601.HasValue%2A>属性`False`，或通过使用测试`Is`或`IsNot`运算符。  
  
### <a name="retrieving-values"></a>检索值  
 若要检索的可以为 null 的类型的变量的值，应首先测试其<xref:System.Nullable%601.HasValue%2A>属性以确认它具有一个值。 如果你尝试读取值时<xref:System.Nullable%601.HasValue%2A>是`False`，Visual Basic 引发<xref:System.InvalidOperationException>异常。 下面的示例演示读取该变量的推荐的方式`numberOfChildren`的前面的示例。  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a>可以为 Null 的类型比较  
 可以为 null 时`Boolean`布尔表达式中使用变量，将会导致`True`， `False`，或`Nothing`。 以下是真值表`And`和`Or`。 因为`b1`和`b2`现在具有三个可能的值，有九个要计算的组合。  
  
|B1|B2|b1 和 b2|b1 或 b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 当布尔变量或表达式的值是`Nothing`，它既不是`true`也不`false`。 请看下面的示例。  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 在此示例中，`b1 And b2`计算结果为`Nothing`。 因此，`Else`子句执行在每个`If`语句，并输出是，如下所示：  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` 和`OrElse`，使用短路计算，必须计算其第二个操作数，当第一个计算结果为`Nothing`。  
  
## <a name="propagation"></a>传播  
 如果一个或两个操作数的算术、 比较、 shift 键或类型操作可以为 null，该操作的结果也是可以为 null。 如果两个操作数的值都不`Nothing`，操作数的基础值执行此操作，就像它们都不是 null 的类型。 在下面的示例中，变量`compare1`和`sum1`隐式类型。 如果鼠标指针停留在它们上时，你会看到编译器的这两个推断可以为 null 的类型。  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 如果一个或两个操作数都具有值为`Nothing`，结果将是`Nothing`。  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a>使用数据使用可以为 Null 的类型  
 数据库是一个最重要的位数，以将其可以为 null 的类型。 并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器。 请参阅中的"为 Null 的类型的 TableAdapter 支持" [TableAdapter 概述](/visualstudio/data-tools/tableadapter-overview)。
  
## <a name="see-also"></a>请参阅  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [使用可以为 null 的类型](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [TableAdapter 概述](/visualstudio/data-tools/tableadapter-overview)  
 [If 运算符](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)
