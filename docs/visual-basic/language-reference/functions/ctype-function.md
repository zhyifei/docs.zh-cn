---
title: CType 函数 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 77bff81efbd61a68c054519710bd671d90af1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694771"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="96d10-102">CType 函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96d10-102">CType Function (Visual Basic)</span></span>
<span data-ttu-id="96d10-103">返回表达式显式转换为指定的数据类型、 对象、 结构、 类或接口的结果。</span><span class="sxs-lookup"><span data-stu-id="96d10-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d10-104">语法</span><span class="sxs-lookup"><span data-stu-id="96d10-104">Syntax</span></span>  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a><span data-ttu-id="96d10-105">部件</span><span class="sxs-lookup"><span data-stu-id="96d10-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="96d10-106">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="96d10-106">Any valid expression.</span></span> <span data-ttu-id="96d10-107">如果的值`expression`超出了允许的范围`typename`，Visual Basic 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="96d10-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>  
  
 `typename`  
 <span data-ttu-id="96d10-108">任何表达式内合法`As`子句中的`Dim`语句中，任何数据类型、 对象、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="96d10-108">Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d10-109">备注</span><span class="sxs-lookup"><span data-stu-id="96d10-109">Remarks</span></span>  
  
> [!TIP]
>  <span data-ttu-id="96d10-110">此外可以使用以下函数来执行类型转换：</span><span class="sxs-lookup"><span data-stu-id="96d10-110">You can also use the following functions to perform a type conversion:</span></span>  
>   
>  -   <span data-ttu-id="96d10-111">类型转换函数，如`CByte`， `CDbl`，和`CInt`，可以执行到特定的数据类型的转换。</span><span class="sxs-lookup"><span data-stu-id="96d10-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="96d10-112">有关详细信息，请参阅[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="96d10-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
> -   <span data-ttu-id="96d10-113">[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)或[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="96d10-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="96d10-114">这些运算符要求一个类型继承自或实现另一个类型。</span><span class="sxs-lookup"><span data-stu-id="96d10-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="96d10-115">他们可以提供一定程度上更好的性能比`CType`来回进行转换时`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="96d10-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>  
  
 <span data-ttu-id="96d10-116">`CType` 采用内联方式编译，这意味着转换代码是计算表达式的值的代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="96d10-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="96d10-117">在某些情况下，代码运行速度更快由于未调用过程来执行此转换。</span><span class="sxs-lookup"><span data-stu-id="96d10-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>  
  
 <span data-ttu-id="96d10-118">如果未定义转换从`expression`到`typename`(例如，从`Integer`到`Date`)，Visual Basic 将显示一条编译时错误消息。</span><span class="sxs-lookup"><span data-stu-id="96d10-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>  
  
 <span data-ttu-id="96d10-119">如果在运行时转换失败，引发相应异常。</span><span class="sxs-lookup"><span data-stu-id="96d10-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="96d10-120">如果收缩转换失败，<xref:System.OverflowException>是最常见的结果。</span><span class="sxs-lookup"><span data-stu-id="96d10-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="96d10-121">如果未定义转换，<xref:System.InvalidCastException>中引发。</span><span class="sxs-lookup"><span data-stu-id="96d10-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="96d10-122">例如，可能的原因`expression`属于类型`Object`并且其运行时类型具有不转换为`typename`。</span><span class="sxs-lookup"><span data-stu-id="96d10-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>  
  
 <span data-ttu-id="96d10-123">如果的数据类型`expression`或`typename`是类或结构定义了，您可以定义`CType`类或结构为转换运算符上。</span><span class="sxs-lookup"><span data-stu-id="96d10-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="96d10-124">这使得`CType`充当*重载运算符*。</span><span class="sxs-lookup"><span data-stu-id="96d10-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="96d10-125">如果执行此操作，则可以控制之间的转换在类或结构，包括可能引发的异常的行为。</span><span class="sxs-lookup"><span data-stu-id="96d10-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="96d10-126">重载</span><span class="sxs-lookup"><span data-stu-id="96d10-126">Overloading</span></span>  
 <span data-ttu-id="96d10-127">`CType`还可以在类或结构在代码之外定义重载运算符。</span><span class="sxs-lookup"><span data-stu-id="96d10-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="96d10-128">如果你的代码需要在这样的类或结构之间进行转换，请确保您了解的行为及其`CType`运算符。</span><span class="sxs-lookup"><span data-stu-id="96d10-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="96d10-129">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="96d10-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="converting-dynamic-objects"></a><span data-ttu-id="96d10-130">转换动态对象</span><span class="sxs-lookup"><span data-stu-id="96d10-130">Converting Dynamic Objects</span></span>  
 <span data-ttu-id="96d10-131">通过用户定义的动态转换的使用进行的动态对象的类型转换<xref:System.Dynamic.DynamicObject.TryConvert%2A>或<xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="96d10-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="96d10-132">如果你正在使用动态对象，请使用<xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>方法转换动态对象。</span><span class="sxs-lookup"><span data-stu-id="96d10-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96d10-133">示例</span><span class="sxs-lookup"><span data-stu-id="96d10-133">Example</span></span>  
 <span data-ttu-id="96d10-134">下面的示例使用`CType`函数将转换为表达式`Single`数据类型。</span><span class="sxs-lookup"><span data-stu-id="96d10-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 <span data-ttu-id="96d10-135">有关其他示例，请参阅[隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="96d10-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d10-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="96d10-136">See also</span></span>
- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="96d10-137">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="96d10-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="96d10-138">转换函数</span><span class="sxs-lookup"><span data-stu-id="96d10-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="96d10-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="96d10-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="96d10-140">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="96d10-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="96d10-141">.NET Framework 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="96d10-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
