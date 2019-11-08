---
title: 可以为 null 的值类型-Visual Basic
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
ms.openlocfilehash: 1fb8f8d1657b8eab6b15858c2a6607cbde82e542
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732932"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="7c74b-102">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c74b-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="7c74b-103">有时，您在某些情况下使用的值类型不具有定义的值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="7c74b-104">例如，数据库中的字段可能必须区分分配的值是否有意义，并且没有分配值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="7c74b-105">可以对值类型进行扩展，使其使用普通值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="7c74b-106">此类扩展称为*可以为 null 的类型*。</span><span class="sxs-lookup"><span data-stu-id="7c74b-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="7c74b-107">每个可以为 null 的类型都是从泛型 <xref:System.Nullable%601> 结构构造的。</span><span class="sxs-lookup"><span data-stu-id="7c74b-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="7c74b-108">考虑使用跟踪工作相关活动的数据库。</span><span class="sxs-lookup"><span data-stu-id="7c74b-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="7c74b-109">下面的示例构造一个可以为 null 的 `Boolean` 类型，并声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="7c74b-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="7c74b-110">可以通过三种方式编写声明：</span><span class="sxs-lookup"><span data-stu-id="7c74b-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="7c74b-111">变量 `ridesBusToWork` 可以保存 `True`值、`False`值或根本不包含值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="7c74b-112">默认情况下，它的初始默认值为 "无" 值，在这种情况下，这可能意味着尚未获取此人的信息。</span><span class="sxs-lookup"><span data-stu-id="7c74b-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="7c74b-113">与此相反，`False` 可能意味着获取了信息，并且该人不会在总线上运行。</span><span class="sxs-lookup"><span data-stu-id="7c74b-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="7c74b-114">可以声明具有可以为 null 的类型的变量和属性，并且可以使用可以为 null 的类型的元素声明数组。</span><span class="sxs-lookup"><span data-stu-id="7c74b-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="7c74b-115">您可以使用可以为 null 的类型作为参数来声明过程，并且可以从 `Function` 过程返回可为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="7c74b-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="7c74b-116">无法在引用类型（如数组、`String`或类）上构造可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="7c74b-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="7c74b-117">基础类型必须为值类型。</span><span class="sxs-lookup"><span data-stu-id="7c74b-117">The underlying type must be a value type.</span></span> <span data-ttu-id="7c74b-118">有关更多信息，请参见 [Value Types and Reference Types](value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="7c74b-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="7c74b-119">使用可以为 Null 的类型变量</span><span class="sxs-lookup"><span data-stu-id="7c74b-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="7c74b-120">可以为 null 的类型的最重要成员是其 <xref:System.Nullable%601.HasValue%2A> 和 <xref:System.Nullable%601.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="7c74b-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="7c74b-121">对于可以为 null 的类型的变量，<xref:System.Nullable%601.HasValue%2A> 会告诉您变量是否包含定义的值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="7c74b-122">如果 `True`<xref:System.Nullable%601.HasValue%2A>，则可以从 <xref:System.Nullable%601.Value%2A>中读取值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="7c74b-123">请注意，<xref:System.Nullable%601.HasValue%2A> 和 <xref:System.Nullable%601.Value%2A> 都是 `ReadOnly` 属性。</span><span class="sxs-lookup"><span data-stu-id="7c74b-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="7c74b-124">默认值</span><span class="sxs-lookup"><span data-stu-id="7c74b-124">Default Values</span></span>

<span data-ttu-id="7c74b-125">使用可以为 null 的类型声明变量时，其 <xref:System.Nullable%601.HasValue%2A> 属性的默认值为 `False`。</span><span class="sxs-lookup"><span data-stu-id="7c74b-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="7c74b-126">这意味着，默认情况下，该变量没有定义的值，而不是其基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="7c74b-127">在下面的示例中，变量 `numberOfChildren` 最初没有定义的值，即使 `Integer` 类型的默认值为0。</span><span class="sxs-lookup"><span data-stu-id="7c74b-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="7c74b-128">空值有助于指示未定义或未知的值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="7c74b-129">如果 `numberOfChildren` 已声明为 `Integer`，则没有任何值可指示该信息当前不可用。</span><span class="sxs-lookup"><span data-stu-id="7c74b-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="7c74b-130">存储值</span><span class="sxs-lookup"><span data-stu-id="7c74b-130">Storing Values</span></span>

<span data-ttu-id="7c74b-131">以典型方式将值存储在可以为 null 的类型的变量或属性中。</span><span class="sxs-lookup"><span data-stu-id="7c74b-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="7c74b-132">下面的示例将一个值赋给在上一个示例中声明 `numberOfChildren` 变量。</span><span class="sxs-lookup"><span data-stu-id="7c74b-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="7c74b-133">如果可为 null 的类型的变量或属性包含定义的值，则可以使其恢复到未分配值的初始状态。</span><span class="sxs-lookup"><span data-stu-id="7c74b-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="7c74b-134">为此，可将变量或属性设置为 "`Nothing`"，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="7c74b-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="7c74b-135">虽然可以将 `Nothing` 分配到可为 null 的类型的变量，但不能使用等号对其 `Nothing` 进行测试。</span><span class="sxs-lookup"><span data-stu-id="7c74b-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="7c74b-136">使用等号 `someVar = Nothing`的比较始终计算为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="7c74b-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="7c74b-137">您可以使用 `Is` 或 `IsNot` 运算符来测试 `False`的变量 <xref:System.Nullable%601.HasValue%2A> 属性，或测试该属性。</span><span class="sxs-lookup"><span data-stu-id="7c74b-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="7c74b-138">检索值</span><span class="sxs-lookup"><span data-stu-id="7c74b-138">Retrieving Values</span></span>

<span data-ttu-id="7c74b-139">若要检索可为 null 的类型的变量的值，您应该首先测试其 <xref:System.Nullable%601.HasValue%2A> 属性以确认它具有值。</span><span class="sxs-lookup"><span data-stu-id="7c74b-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="7c74b-140">如果在 `False`<xref:System.Nullable%601.HasValue%2A> 时尝试读取该值，Visual Basic 将引发 <xref:System.InvalidOperationException> 异常。</span><span class="sxs-lookup"><span data-stu-id="7c74b-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="7c74b-141">下面的示例演示了读取前面示例的变量 `numberOfChildren` 的建议方法。</span><span class="sxs-lookup"><span data-stu-id="7c74b-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="7c74b-142">比较可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="7c74b-142">Comparing Nullable Types</span></span>

<span data-ttu-id="7c74b-143">在布尔表达式中使用可以为 null 的 `Boolean` 变量时，结果可以是 `True`、`False`或 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="7c74b-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="7c74b-144">下面是 `And` 和 `Or`的事实数据表。</span><span class="sxs-lookup"><span data-stu-id="7c74b-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="7c74b-145">因为 `b1` 和 `b2` 现在具有三个可能的值，所以有九个计算组合。</span><span class="sxs-lookup"><span data-stu-id="7c74b-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="7c74b-146">B1</span><span class="sxs-lookup"><span data-stu-id="7c74b-146">b1</span></span>|<span data-ttu-id="7c74b-147">b2</span><span class="sxs-lookup"><span data-stu-id="7c74b-147">b2</span></span>|<span data-ttu-id="7c74b-148">b1 和 b2</span><span class="sxs-lookup"><span data-stu-id="7c74b-148">b1 And b2</span></span>|<span data-ttu-id="7c74b-149">b1 或 b2</span><span class="sxs-lookup"><span data-stu-id="7c74b-149">b1 Or b2</span></span>|
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

<span data-ttu-id="7c74b-150">如果 `Nothing`布尔变量或表达式的值，则既不 `true` 也不 `false`。</span><span class="sxs-lookup"><span data-stu-id="7c74b-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="7c74b-151">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="7c74b-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="7c74b-152">在此示例中，`b1 And b2` 的计算结果为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="7c74b-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="7c74b-153">因此，在每个 `If` 语句中执行 `Else` 子句，输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="7c74b-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="7c74b-154">如果 `AndAlso` 和 `OrElse`使用短路计算，则在第一次计算为 `Nothing`时，必须计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="7c74b-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="7c74b-155">传播</span><span class="sxs-lookup"><span data-stu-id="7c74b-155">Propagation</span></span>

<span data-ttu-id="7c74b-156">如果算术、比较、移位或类型运算的一个或两个操作数可以为 null，则该运算的结果也可以为 null。</span><span class="sxs-lookup"><span data-stu-id="7c74b-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="7c74b-157">如果两个操作数都没有 `Nothing`的值，则对操作数的基础值执行运算，就好像这两个操作数都不是可以为 null 的类型一样。</span><span class="sxs-lookup"><span data-stu-id="7c74b-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="7c74b-158">在下面的示例中，变量 `compare1` 和 `sum1` 被隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="7c74b-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="7c74b-159">如果将鼠标指针停留在其上，则会看到编译器将为这两个文件推断可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="7c74b-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="7c74b-160">如果一个或两个操作数的值为 `Nothing`，则将 `Nothing`结果。</span><span class="sxs-lookup"><span data-stu-id="7c74b-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="7c74b-161">对数据使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="7c74b-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="7c74b-162">数据库是使用可以为 null 的类型的最重要的地方之一。</span><span class="sxs-lookup"><span data-stu-id="7c74b-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="7c74b-163">并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器则执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7c74b-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="7c74b-164">请参阅[对可以为 null 的类型的 TableAdapter 支持](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)。</span><span class="sxs-lookup"><span data-stu-id="7c74b-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c74b-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c74b-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="7c74b-166">数据类型</span><span class="sxs-lookup"><span data-stu-id="7c74b-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="7c74b-167">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="7c74b-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="7c74b-168">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="7c74b-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="7c74b-169">使用 Tableadapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="7c74b-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="7c74b-170">If 运算符</span><span class="sxs-lookup"><span data-stu-id="7c74b-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="7c74b-171">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="7c74b-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="7c74b-172">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="7c74b-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="7c74b-173">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="7c74b-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="7c74b-174">可以为 null 的C#值类型（）</span><span class="sxs-lookup"><span data-stu-id="7c74b-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
