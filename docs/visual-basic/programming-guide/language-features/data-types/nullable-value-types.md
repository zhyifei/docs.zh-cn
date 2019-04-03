---
title: 可以为 Null 的值类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 437107bb522e1635dffa4a2de88c5d10d6707592
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825128"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="d55f3-102">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d55f3-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="d55f3-103">有时，你将使用在某些情况下没有已定义的值的值类型。</span><span class="sxs-lookup"><span data-stu-id="d55f3-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="d55f3-104">例如，在数据库中的字段可能需要区分具有分配的值有意义的而不让分配的值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="d55f3-105">值类型可以扩展以使其正常值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="d55f3-106">调用此类扩展*为 null 的类型*。</span><span class="sxs-lookup"><span data-stu-id="d55f3-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="d55f3-107">每个可以为 null 的类型从泛型构造<xref:System.Nullable%601>结构。</span><span class="sxs-lookup"><span data-stu-id="d55f3-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="d55f3-108">假设有一个数据库，用于跟踪与工作相关的活动。</span><span class="sxs-lookup"><span data-stu-id="d55f3-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="d55f3-109">下面的示例构造一个可以为 null`Boolean`类型，并声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="d55f3-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="d55f3-110">以下三种方式，可以编写以下声明：</span><span class="sxs-lookup"><span data-stu-id="d55f3-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 <span data-ttu-id="d55f3-111">在变量`ridesBusToWork`可以保存的值`True`，值为`False`，或者根本没有值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="d55f3-112">其初始默认值是没有值，这在此情况下可能意味着，信息具有尚未获得此人。</span><span class="sxs-lookup"><span data-stu-id="d55f3-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="d55f3-113">与此相反，`False`可能是获得的信息，而该人员未乘坐公共汽车去上班。</span><span class="sxs-lookup"><span data-stu-id="d55f3-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="d55f3-114">可以使用可以为 null 的类型来声明变量和属性，并可以声明具有可以为 null 的类型的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="d55f3-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="d55f3-115">可以使用作为参数，可以为 null 的类型来声明过程和可以返回 null 的类型从`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="d55f3-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="d55f3-116">无法构造为 null 的类型，如数组、 引用类型上`String`，或类。</span><span class="sxs-lookup"><span data-stu-id="d55f3-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="d55f3-117">基础类型必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="d55f3-117">The underlying type must be a value type.</span></span> <span data-ttu-id="d55f3-118">有关更多信息，请参见 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d55f3-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="d55f3-119">使用可以为 Null 的类型变量</span><span class="sxs-lookup"><span data-stu-id="d55f3-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="d55f3-120">可以为 null 的类型的最重要成员是其<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d55f3-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="d55f3-121">变量的为 null 的类型，<xref:System.Nullable%601.HasValue%2A>告诉您此变量是否包含定义的值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="d55f3-122">如果<xref:System.Nullable%601.HasValue%2A>是`True`，你可以读取的值从<xref:System.Nullable%601.Value%2A>。</span><span class="sxs-lookup"><span data-stu-id="d55f3-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="d55f3-123">请注意，这两<xref:System.Nullable%601.HasValue%2A>并<xref:System.Nullable%601.Value%2A>是`ReadOnly`属性。</span><span class="sxs-lookup"><span data-stu-id="d55f3-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="d55f3-124">默认值</span><span class="sxs-lookup"><span data-stu-id="d55f3-124">Default Values</span></span>  
 <span data-ttu-id="d55f3-125">使用可以为 null 的类型和声明变量时其<xref:System.Nullable%601.HasValue%2A>属性具有默认值为`False`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="d55f3-126">这意味着默认情况下该变量具有未定义的值，而不是其基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="d55f3-127">在下面的示例中，变量`numberOfChildren`最初有没有定义的值，即使的默认值`Integer`类型为 0。</span><span class="sxs-lookup"><span data-stu-id="d55f3-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 <span data-ttu-id="d55f3-128">Null 值可用于指示未定义或未知值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="d55f3-129">如果`numberOfChildren`已声明为`Integer`，会有任何可能表示信息不是当前可用的值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="d55f3-130">将值存储</span><span class="sxs-lookup"><span data-stu-id="d55f3-130">Storing Values</span></span>  
 <span data-ttu-id="d55f3-131">以典型方式，可以在变量或可以为 null 的类型的属性中存储值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="d55f3-132">下面的示例将一个值分配给变量`numberOfChildren`上一示例中声明。</span><span class="sxs-lookup"><span data-stu-id="d55f3-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 <span data-ttu-id="d55f3-133">如果变量或可以为 null 的类型的属性包含已定义的值，则可以使此恢复到其初始状态不具有分配的值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="d55f3-134">为此，可设置的变量或属性设置为`Nothing`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d55f3-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="d55f3-135">尽管可以将分配`Nothing`不能为 null 的类型的变量，测试其用于`Nothing`使用等号。</span><span class="sxs-lookup"><span data-stu-id="d55f3-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="d55f3-136">使用等号的比较`someVar = Nothing`，计算结果始终为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="d55f3-137">你可以测试的变量<xref:System.Nullable%601.HasValue%2A>属性`False`，或使用测试`Is`或`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="d55f3-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="d55f3-138">检索值</span><span class="sxs-lookup"><span data-stu-id="d55f3-138">Retrieving Values</span></span>  
 <span data-ttu-id="d55f3-139">若要检索的可以为 null 的类型的变量的值，应该首先测试其<xref:System.Nullable%601.HasValue%2A>属性来确认它具有值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="d55f3-140">如果您尝试读取值时<xref:System.Nullable%601.HasValue%2A>是`False`，Visual Basic 将引发<xref:System.InvalidOperationException>异常。</span><span class="sxs-lookup"><span data-stu-id="d55f3-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="d55f3-141">下面的示例演示读取该变量的建议的方法`numberOfChildren`的前面的示例。</span><span class="sxs-lookup"><span data-stu-id="d55f3-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="d55f3-142">可以为 Null 的类型比较</span><span class="sxs-lookup"><span data-stu-id="d55f3-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="d55f3-143">可以为 null 时`Boolean`在布尔表达式中使用变量，结果可以是`True`， `False`，或`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="d55f3-144">下面是真值表`And`和`Or`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="d55f3-145">因为`b1`和`b2`现在有三个可能值有九个组合来评估。</span><span class="sxs-lookup"><span data-stu-id="d55f3-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="d55f3-146">b1</span><span class="sxs-lookup"><span data-stu-id="d55f3-146">b1</span></span>|<span data-ttu-id="d55f3-147">b2</span><span class="sxs-lookup"><span data-stu-id="d55f3-147">b2</span></span>|<span data-ttu-id="d55f3-148">b1 和 b2</span><span class="sxs-lookup"><span data-stu-id="d55f3-148">b1 And b2</span></span>|<span data-ttu-id="d55f3-149">b1 或 b2</span><span class="sxs-lookup"><span data-stu-id="d55f3-149">b1 Or b2</span></span>|  
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
  
 <span data-ttu-id="d55f3-150">当布尔型变量或表达式的值是`Nothing`，它既不是`true`也不`false`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="d55f3-151">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="d55f3-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 <span data-ttu-id="d55f3-152">在此示例中，`b1 And b2`计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="d55f3-153">因此，`Else`子句中每个执行`If`语句，并输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="d55f3-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="d55f3-154">`AndAlso` 并`OrElse`，可使用该技术短路计算，必须评估其第二个操作数时第一个计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="d55f3-155">传播</span><span class="sxs-lookup"><span data-stu-id="d55f3-155">Propagation</span></span>  
 <span data-ttu-id="d55f3-156">如果一个或两个操作数的算术、 比较、 shift 键或类型操作可以为 null，该操作的结果也是可以为 null。</span><span class="sxs-lookup"><span data-stu-id="d55f3-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="d55f3-157">如果两个操作数的值`Nothing`，对底层的操作数，值执行此操作，因为如果它们都不是 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="d55f3-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="d55f3-158">在下面的示例中，变量`compare1`和`sum1`隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="d55f3-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="d55f3-159">如果将鼠标指针停留在其上时，将看到编译器将为 null 的类型推断为这两个值。</span><span class="sxs-lookup"><span data-stu-id="d55f3-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 <span data-ttu-id="d55f3-160">如果一个或两个操作数具有值为`Nothing`，结果将是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d55f3-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="d55f3-161">数据中使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="d55f3-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="d55f3-162">数据库是一个最重要的地方使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="d55f3-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="d55f3-163">并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器。</span><span class="sxs-lookup"><span data-stu-id="d55f3-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="d55f3-164">请参阅中的"TableAdapter 支持可以为 Null 的类型" [TableAdapter 概述](/visualstudio/data-tools/tableadapter-overview)。</span><span class="sxs-lookup"><span data-stu-id="d55f3-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d55f3-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="d55f3-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="d55f3-166">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="d55f3-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="d55f3-167">数据类型</span><span class="sxs-lookup"><span data-stu-id="d55f3-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="d55f3-168">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="d55f3-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="d55f3-169">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="d55f3-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d55f3-170">TableAdapter 概述</span><span class="sxs-lookup"><span data-stu-id="d55f3-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)
- [<span data-ttu-id="d55f3-171">If 运算符</span><span class="sxs-lookup"><span data-stu-id="d55f3-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="d55f3-172">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="d55f3-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d55f3-173">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="d55f3-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="d55f3-174">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="d55f3-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
