---
title: 算术运算符 (F#)
description: '了解有关 F # 编程语言中可用的算术运算符。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 04/04/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 75ddcfa3-564e-4382-80a3-f9da73d0f0ea
ms.openlocfilehash: 8f11e77457bed40cff081a73181689610871e654
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="arithmetic-operators"></a>算术运算符

本主题介绍对 F # 语言中可用的算术运算符。

## <a name="summary-of-binary-arithmetic-operators"></a>二进制算术运算符的摘要
下表总结了可用于未装箱的整型和浮点类型的二进制算术运算符。

|二元运算符|备注|
|---------------|-----|
|`+` (此外，加上)|未选中状态。 数字加在一起可能上溢条件和总和超过了最大绝对值的数值类型支持。|
|`-` (减法、 减号)|未选中状态。 可能的下溢条件时无符号的类型相减，或者如果浮点值太小而无法表示由类型。|
|`*` (乘号）|未选中状态。 可能的溢出时两个数相乘和产品超出最大绝对值的数值类型支持。|
|`/` （除号）|除数为零原因<xref:System.DivideByZeroException>对于整数类型。 对于浮点类型，以零作除数为你提供特殊的浮点值`+Infinity`或`-Infinity`。 此外还有一个可能的下溢条件太小，无法由类型表示的浮点数时。|
|`%` （剩余部分、 rem）|返回除法运算的余数。 结果的符号是第一操作数的符号相同。|
|`**` （的次幂求幂）|可能的溢出条件时的结果超出了最大绝对值的数值类型。<br /><br />Exponentiation 运算符仅适用于浮点类型。|

## <a name="summary-of-unary-arithmetic-operators"></a>一元算术运算符的摘要
下表总结了可用于整型和浮点型的一元算术运算符。


|一元运算符|说明|
|--------------|-----|
|`+` （正）|可以应用于任何算术表达式。 不会更改的值的符号。|
|`-` （求反，负）|可以应用于任何算术表达式。 更改的值的符号。|
在溢出或下的溢对于整数类型的行为是环绕在周围。 这将导致错误的结果。 整数溢出是软件不写入要为其帐户时，可能会导致安全问题的潜在的严重问题。 如果这是你的应用程序问题，请考虑使用中的选中的运算符`Microsoft.FSharp.Core.Operators.Checked`。


## <a name="summary-of-binary-comparison-operators"></a>二进制比较运算符摘要
下表显示可用于整型和浮点类型的二进制比较运算符。 这些运算符将返回类型的值`bool`。

浮点数字应永远不会进行直接比较相等性，因为 IEEE 浮点表示形式不支持完全相等运算。 可以轻松地对其进行验证要通过检查代码相等的两个数字实际上可能具有不同的位表示形式。



|运算符|说明|
|--------|-----|
|`=` （等于）|这不是赋值运算符。 它仅用于比较。 这是泛型的运算符。|
|`>` （大于）|这是泛型的运算符。|
|`<` （小于）|这是泛型的运算符。|
|`>=` (大于或等于)|这是泛型的运算符。|
|`<=` (小于或等于)|这是泛型的运算符。|
|`<>` （不等于）|这是泛型的运算符。|

## <a name="overloaded-and-generic-operators"></a>运算符重载和泛型运算符
所有本主题中讨论的运算符定义中**Microsoft.FSharp.Core.Operators**命名空间。 某些运算符使用定义的静态解析的类型参数。 这意味着每个适用于该运算符的特定类型的单个定义。 所有的一元和二元算术和按位运算符都在此类别。 比较运算符都是泛型方法，并因此处理任何类型，而不只是基元算术类型。 可区分的联合和记录类型具有由 F # 编译器生成其自己自定义实现。 类类型使用方法<xref:System.Object.Equals%2A>。

泛型运算符都是可自定义的。 若要自定义比较函数，请重写<xref:System.Object.Equals%2A>以提供您自己的自定义的相等性比较，，然后实现<xref:System.IComparable>。 <xref:System.IComparable?displayProperty=nameWithType>接口具有一个方法，<xref:System.IComparable.CompareTo%2A>方法。


## <a name="operators-and-type-inference"></a>运算符和类型推理
运算符在表达式中的使用限制在该运算符的类型推理。 此外，运算符使用可以防止自动泛化，因为运算符的使用意味着算术类型。 在没有任何其他信息的情况下，F # 编译器推断出`int`作为算术表达式的类型。 通过指定另一种类型，可以重写此行为。 因此的自变量类型和返回类型`function1`下面的代码中会被推断为`int`，但为类型`function2`推断为`float`。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]
    
## <a name="see-also"></a>另请参阅
[符号和运算符参考](index.md)

[运算符重载](../operator-overloading.md)

[位运算符](bitwise-operators.md)

[布尔运算符](boolean-operators.md)
