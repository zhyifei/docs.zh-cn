---
title: 可以为 null 的值类型
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249677"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="c8c75-102">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8c75-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="c8c75-103">有时，使用在某些情况下没有定义值的值类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="c8c75-104">例如，数据库中的字段可能必须区分具有有意义的赋值和没有赋值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="c8c75-105">可以扩展值类型以获取其正常值或空值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="c8c75-106">这种扩展称为*空类型*。</span><span class="sxs-lookup"><span data-stu-id="c8c75-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="c8c75-107">每个空值类型都是从泛型<xref:System.Nullable%601>结构构造的。</span><span class="sxs-lookup"><span data-stu-id="c8c75-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="c8c75-108">考虑跟踪与工作相关的活动的数据库。</span><span class="sxs-lookup"><span data-stu-id="c8c75-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="c8c75-109">下面的示例构造一个可`Boolean`null 的类型，并声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="c8c75-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="c8c75-110">您可以通过三种方式编写声明：</span><span class="sxs-lookup"><span data-stu-id="c8c75-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="c8c75-111">变量`ridesBusToWork`可以保存`True`值 ，`False`或根本不值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="c8c75-112">其初始默认值根本没有值，在这种情况下，这可能意味着尚未为此人获取信息。</span><span class="sxs-lookup"><span data-stu-id="c8c75-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="c8c75-113">相反，`False`可能意味着信息已经获得，并且此人不坐公共汽车去上班。</span><span class="sxs-lookup"><span data-stu-id="c8c75-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="c8c75-114">可以使用空值类型声明变量和属性，也可以声明具有空值类型的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="c8c75-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="c8c75-115">您可以将具有空值类型的过程声明为参数，也可以从`Function`过程返回空值类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="c8c75-116">不能在引用类型（如数组、a`String`或 类）上构造可 null 类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="c8c75-117">基础类型必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-117">The underlying type must be a value type.</span></span> <span data-ttu-id="c8c75-118">有关详细信息，请参阅[值类型和参考类型](value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c75-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="c8c75-119">使用可空类型变量</span><span class="sxs-lookup"><span data-stu-id="c8c75-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="c8c75-120">空值类型最重要的成员是其<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c8c75-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="c8c75-121">对于空值类型的变量，<xref:System.Nullable%601.HasValue%2A>告诉您该变量是否包含定义的值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="c8c75-122">如果是<xref:System.Nullable%601.HasValue%2A>`True`，则可以从<xref:System.Nullable%601.Value%2A>读取 值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="c8c75-123">请注意，两<xref:System.Nullable%601.HasValue%2A>者<xref:System.Nullable%601.Value%2A>都是`ReadOnly`属性。</span><span class="sxs-lookup"><span data-stu-id="c8c75-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="c8c75-124">默认值</span><span class="sxs-lookup"><span data-stu-id="c8c75-124">Default Values</span></span>

<span data-ttu-id="c8c75-125">当您声明具有空值类型的变量时，其<xref:System.Nullable%601.HasValue%2A>属性的默认值为`False`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="c8c75-126">这意味着默认情况下，变量没有定义的值，而不是其基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="c8c75-127">在下面的示例中，变量`numberOfChildren`最初没有定义的值，即使`Integer`类型的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="c8c75-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="c8c75-128">空值可用于指示未定义或未知值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="c8c75-129">如果`numberOfChildren`已声明为`Integer`，则没有任何值可以指示信息当前不可用。</span><span class="sxs-lookup"><span data-stu-id="c8c75-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="c8c75-130">存储值</span><span class="sxs-lookup"><span data-stu-id="c8c75-130">Storing Values</span></span>

<span data-ttu-id="c8c75-131">以典型方式将值存储在可 null 值类型的变量或属性中。</span><span class="sxs-lookup"><span data-stu-id="c8c75-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="c8c75-132">下面的示例将值分配给上一个示例中声明`numberOfChildren`的变量。</span><span class="sxs-lookup"><span data-stu-id="c8c75-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="c8c75-133">如果空值类型的变量或属性包含已定义的值，则可能导致它恢复到未分配值的初始状态。</span><span class="sxs-lookup"><span data-stu-id="c8c75-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="c8c75-134">为此，通过将变量或属性设置为`Nothing`（）来执行此操作，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="c8c75-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="c8c75-135">尽管可以分配给`Nothing`null 值类型的变量，但不能`Nothing`使用等号来测试它。</span><span class="sxs-lookup"><span data-stu-id="c8c75-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="c8c75-136">使用等号`someVar = Nothing`的比较， 始终计算为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="c8c75-137">可以使用<xref:System.Nullable%601.HasValue%2A>或`False``Is``IsNot`运算符测试变量的属性， 或测试。</span><span class="sxs-lookup"><span data-stu-id="c8c75-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="c8c75-138">检索值</span><span class="sxs-lookup"><span data-stu-id="c8c75-138">Retrieving Values</span></span>

<span data-ttu-id="c8c75-139">若要检索 null 值类型的变量的值，应首先测试其<xref:System.Nullable%601.HasValue%2A>属性以确认其具有值。</span><span class="sxs-lookup"><span data-stu-id="c8c75-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="c8c75-140">如果尝试读取值时<xref:System.Nullable%601.HasValue%2A>为`False`，Visual Basic 将引发异常<xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="c8c75-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="c8c75-141">下面的示例显示了读取前面示例变量`numberOfChildren`的建议方法。</span><span class="sxs-lookup"><span data-stu-id="c8c75-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="c8c75-142">比较可消除类型</span><span class="sxs-lookup"><span data-stu-id="c8c75-142">Comparing Nullable Types</span></span>

<span data-ttu-id="c8c75-143">当布尔表达式`Boolean`中使用空变量时，结果可以是`True`，`False`或`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="c8c75-144">下面是`And`和`Or`的真情况表。</span><span class="sxs-lookup"><span data-stu-id="c8c75-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="c8c75-145">因为`b1`现在有`b2`三个可能的值，因此有九个组合需要计算。</span><span class="sxs-lookup"><span data-stu-id="c8c75-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="c8c75-146">b1</span><span class="sxs-lookup"><span data-stu-id="c8c75-146">b1</span></span>|<span data-ttu-id="c8c75-147">b2</span><span class="sxs-lookup"><span data-stu-id="c8c75-147">b2</span></span>|<span data-ttu-id="c8c75-148">b1 和 b2</span><span class="sxs-lookup"><span data-stu-id="c8c75-148">b1 And b2</span></span>|<span data-ttu-id="c8c75-149">b1 或 b2</span><span class="sxs-lookup"><span data-stu-id="c8c75-149">b1 Or b2</span></span>|
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

<span data-ttu-id="c8c75-150">当布尔变量或表达式的值为`Nothing`时，它既不是 ，`true`也不是`false`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="c8c75-151">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="c8c75-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="c8c75-152">在此示例中，`b1 And b2`计算 到`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="c8c75-153">因此，子`Else`句在每个`If`语句中执行，输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8c75-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="c8c75-154">`AndAlso`和`OrElse`，使用短路评估时，必须评估其第二个操作数， 当第一个`Nothing`计算到 。</span><span class="sxs-lookup"><span data-stu-id="c8c75-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="c8c75-155">传播</span><span class="sxs-lookup"><span data-stu-id="c8c75-155">Propagation</span></span>

<span data-ttu-id="c8c75-156">如果算术、比较、移位或类型操作的一个或两个操作数是空值类型，则操作的结果也是空值类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="c8c75-157">如果两个操作数的值都不是`Nothing`，则对操作数的基础值执行操作，就像两者都不是空值类型一样。</span><span class="sxs-lookup"><span data-stu-id="c8c75-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="c8c75-158">在下面的示例中，变量`compare1`和`sum1`隐式类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="c8c75-159">如果将鼠标指针放在鼠标指针上，您将看到编译器推断它们两个指针的空值类型。</span><span class="sxs-lookup"><span data-stu-id="c8c75-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="c8c75-160">如果一个或两个操作数的值`Nothing`为 ， 则结果将为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c8c75-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="c8c75-161">将可空类型与数据一起使用</span><span class="sxs-lookup"><span data-stu-id="c8c75-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="c8c75-162">数据库是使用空值类型的最重要位置之一。</span><span class="sxs-lookup"><span data-stu-id="c8c75-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="c8c75-163">并非所有数据库对象当前都支持空值类型，但设计器生成的表适配器支持。</span><span class="sxs-lookup"><span data-stu-id="c8c75-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="c8c75-164">有关[空类型的表适配器支持，请参阅表适配器支持](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)。</span><span class="sxs-lookup"><span data-stu-id="c8c75-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8c75-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c75-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="c8c75-166">数据类型</span><span class="sxs-lookup"><span data-stu-id="c8c75-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="c8c75-167">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="c8c75-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="c8c75-168">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="c8c75-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="c8c75-169">使用 Tableadapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="c8c75-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="c8c75-170">If 运算符</span><span class="sxs-lookup"><span data-stu-id="c8c75-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="c8c75-171">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="c8c75-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="c8c75-172">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="c8c75-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="c8c75-173">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="c8c75-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="c8c75-174">空值类型 （C#）</span><span class="sxs-lookup"><span data-stu-id="c8c75-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
