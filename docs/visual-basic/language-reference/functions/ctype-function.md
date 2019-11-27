---
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 18b2d5a28cd6ef885ba8d237da6764dbbd108b59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348097"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="fb63e-102">CType 函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb63e-102">CType Function (Visual Basic)</span></span>

<span data-ttu-id="fb63e-103">返回将表达式显式转换为指定的数据类型、对象、结构、类或接口的结果。</span><span class="sxs-lookup"><span data-stu-id="fb63e-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb63e-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb63e-104">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="fb63e-105">部件</span><span class="sxs-lookup"><span data-stu-id="fb63e-105">Parts</span></span>

<span data-ttu-id="fb63e-106">`expression` 任意有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="fb63e-106">`expression` Any valid expression.</span></span> <span data-ttu-id="fb63e-107">如果 `expression` 的值超出 `typename`所允许的范围，Visual Basic 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="fb63e-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="fb63e-108">`typename` 在 `Dim` 语句的 `As` 子句内合法的任何表达式，即任何数据类型、对象、结构、类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="fb63e-108">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb63e-109">备注</span><span class="sxs-lookup"><span data-stu-id="fb63e-109">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="fb63e-110">你还可以使用以下函数来执行类型转换：</span><span class="sxs-lookup"><span data-stu-id="fb63e-110">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="fb63e-111">转换为特定数据类型的类型转换函数，例如 `CByte`、`CDbl`和 `CInt`。</span><span class="sxs-lookup"><span data-stu-id="fb63e-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="fb63e-112">有关详细信息，请参阅[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="fb63e-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>
> - <span data-ttu-id="fb63e-113">[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)或[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="fb63e-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="fb63e-114">这些运算符要求一个类型继承自或实现另一个类型。</span><span class="sxs-lookup"><span data-stu-id="fb63e-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="fb63e-115">与 `Object` 数据类型相互转换时，与 `CType` 相比，它们可以提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="fb63e-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="fb63e-116">`CType` 是内联编译的，这意味着转换代码是计算表达式的代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="fb63e-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="fb63e-117">在某些情况下，代码运行速度更快，因为没有调用任何过程来执行转换。</span><span class="sxs-lookup"><span data-stu-id="fb63e-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="fb63e-118">如果从 `expression` 到 `typename` （例如，从 `Integer` 到 `Date`）未定义转换，Visual Basic 将显示编译时错误消息。</span><span class="sxs-lookup"><span data-stu-id="fb63e-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="fb63e-119">如果转换在运行时失败，则会引发相应的异常。</span><span class="sxs-lookup"><span data-stu-id="fb63e-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="fb63e-120">如果收缩转换失败，最常见的结果是 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="fb63e-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="fb63e-121">如果未定义转换，则会引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="fb63e-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="fb63e-122">例如，如果 `expression` 类型 `Object` 并且其运行时类型没有转换为 `typename`，则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="fb63e-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="fb63e-123">如果 `expression` 或 `typename` 的数据类型是已定义的类或结构，则可以将该类或结构的 `CType` 定义为转换运算符。</span><span class="sxs-lookup"><span data-stu-id="fb63e-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="fb63e-124">这使得 `CType` 充当*重载运算符*。</span><span class="sxs-lookup"><span data-stu-id="fb63e-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="fb63e-125">如果执行此操作，则可以控制与类或结构的转换的行为，包括可能引发的异常。</span><span class="sxs-lookup"><span data-stu-id="fb63e-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="fb63e-126">重载</span><span class="sxs-lookup"><span data-stu-id="fb63e-126">Overloading</span></span>

<span data-ttu-id="fb63e-127">也可以在代码外部定义的类或结构上重载 `CType` 运算符。</span><span class="sxs-lookup"><span data-stu-id="fb63e-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="fb63e-128">如果你的代码在此类或结构之间进行转换，请确保了解其 `CType` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="fb63e-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="fb63e-129">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="fb63e-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="fb63e-130">转换动态对象</span><span class="sxs-lookup"><span data-stu-id="fb63e-130">Converting Dynamic Objects</span></span>

<span data-ttu-id="fb63e-131">动态对象的类型转换由使用 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 或 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 方法的用户定义的动态转换执行。</span><span class="sxs-lookup"><span data-stu-id="fb63e-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="fb63e-132">如果使用的是动态对象，请使用 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 方法转换动态对象。</span><span class="sxs-lookup"><span data-stu-id="fb63e-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="fb63e-133">示例</span><span class="sxs-lookup"><span data-stu-id="fb63e-133">Example</span></span>

<span data-ttu-id="fb63e-134">下面的示例使用 `CType` 函数将表达式转换为 `Single` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fb63e-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="fb63e-135">有关其他示例，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="fb63e-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb63e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb63e-136">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="fb63e-137">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="fb63e-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="fb63e-138">转换函数</span><span class="sxs-lookup"><span data-stu-id="fb63e-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="fb63e-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="fb63e-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="fb63e-140">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="fb63e-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="fb63e-141">.NET Framework 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="fb63e-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
