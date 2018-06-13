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
ms.openlocfilehash: bb44ad85347b494b63dde964b2b407d8f038f2b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656014"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="e8721-102">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8721-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="e8721-103">有时，你将使用在某些情况下没有已定义的值的值类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="e8721-104">例如，数据库中的字段可能需要区分具有有意义的分配的值并不具有分配的值。</span><span class="sxs-lookup"><span data-stu-id="e8721-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="e8721-105">可以扩展值类型，以使其正常值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="e8721-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="e8721-106">调用此类扩展*可以为 null 的类型*。</span><span class="sxs-lookup"><span data-stu-id="e8721-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="e8721-107">每个可以为 null 的类型从泛型构造<xref:System.Nullable%601>结构。</span><span class="sxs-lookup"><span data-stu-id="e8721-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="e8721-108">请考虑跟踪与工作相关的活动的数据库。</span><span class="sxs-lookup"><span data-stu-id="e8721-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="e8721-109">下面的示例构造一个可以为 null`Boolean`类型，并声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="e8721-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="e8721-110">你可以通过三种方式编写声明：</span><span class="sxs-lookup"><span data-stu-id="e8721-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 <span data-ttu-id="e8721-111">变量`ridesBusToWork`可以保存的值`True`，值为`False`，或根本没有值。</span><span class="sxs-lookup"><span data-stu-id="e8721-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="e8721-112">其初始的默认值为没有值，这在此情况下可能意味着，信息具有尚未获得此人。</span><span class="sxs-lookup"><span data-stu-id="e8721-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="e8721-113">与此相反，`False`可能是获得的信息，而此人乘坐工作的总线不公共。</span><span class="sxs-lookup"><span data-stu-id="e8721-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="e8721-114">可以使用可以为 null 的类型来声明变量和属性，而您可以声明包含 null 的类型的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="e8721-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="e8721-115">你可以使用作为参数，可以为 null 的类型声明过程并可以返回 null 的类型从`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="e8721-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="e8721-116">无法构造 null 的类型，如数组、 一个引用类型上`String`，或类。</span><span class="sxs-lookup"><span data-stu-id="e8721-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="e8721-117">基础类型必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-117">The underlying type must be a value type.</span></span> <span data-ttu-id="e8721-118">有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e8721-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="e8721-119">使用可以为 Null 的类型变量</span><span class="sxs-lookup"><span data-stu-id="e8721-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="e8721-120">可以为 null 的类型的最重要成员是其<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e8721-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="e8721-121">变量的 null 的类型，<xref:System.Nullable%601.HasValue%2A>告知你此变量是否包含已定义的值。</span><span class="sxs-lookup"><span data-stu-id="e8721-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="e8721-122">如果<xref:System.Nullable%601.HasValue%2A>是`True`，你可以读取的值从<xref:System.Nullable%601.Value%2A>。</span><span class="sxs-lookup"><span data-stu-id="e8721-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="e8721-123">请注意，同时<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>是`ReadOnly`属性。</span><span class="sxs-lookup"><span data-stu-id="e8721-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="e8721-124">默认值</span><span class="sxs-lookup"><span data-stu-id="e8721-124">Default Values</span></span>  
 <span data-ttu-id="e8721-125">当你声明一个具有变量可以为 null 的类型，其<xref:System.Nullable%601.HasValue%2A>属性具有默认值为`False`。</span><span class="sxs-lookup"><span data-stu-id="e8721-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="e8721-126">这意味着，默认情况下变量没有任何定义的值，而不是其基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="e8721-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="e8721-127">在下面的示例中，变量`numberOfChildren`最初具有任何定义的值，即使的默认值`Integer`类型为 0。</span><span class="sxs-lookup"><span data-stu-id="e8721-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 <span data-ttu-id="e8721-128">空值是用来表示未定义的或未知的值。</span><span class="sxs-lookup"><span data-stu-id="e8721-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="e8721-129">如果`numberOfChildren`假如被声明为`Integer`，将有可能表示信息不是当前可用的任何值。</span><span class="sxs-lookup"><span data-stu-id="e8721-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="e8721-130">将值存储</span><span class="sxs-lookup"><span data-stu-id="e8721-130">Storing Values</span></span>  
 <span data-ttu-id="e8721-131">在典型的方式中，可以在变量或可以为 null 的类型的属性中存储值。</span><span class="sxs-lookup"><span data-stu-id="e8721-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="e8721-132">下面的示例将一个值分配给变量`numberOfChildren`声明在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="e8721-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e8721-133">如果变量或可以为 null 的类型的属性包含已定义的值，则可以使此可恢复到其初始状态，即未获分配的值。</span><span class="sxs-lookup"><span data-stu-id="e8721-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="e8721-134">执行此操作通过设置变量或属性`Nothing`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e8721-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="e8721-135">尽管你可以分配`Nothing`到可以为 null 的类型的变量，不能对其进行测试的`Nothing`使用等号。</span><span class="sxs-lookup"><span data-stu-id="e8721-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="e8721-136">比较过程中使用等号， `someVar = Nothing`，始终评估为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e8721-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="e8721-137">你可以测试变量的<xref:System.Nullable%601.HasValue%2A>属性`False`，或通过使用测试`Is`或`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="e8721-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="e8721-138">检索值</span><span class="sxs-lookup"><span data-stu-id="e8721-138">Retrieving Values</span></span>  
 <span data-ttu-id="e8721-139">若要检索的可以为 null 的类型的变量的值，应首先测试其<xref:System.Nullable%601.HasValue%2A>属性以确认它具有一个值。</span><span class="sxs-lookup"><span data-stu-id="e8721-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="e8721-140">如果你尝试读取值时<xref:System.Nullable%601.HasValue%2A>是`False`，Visual Basic 引发<xref:System.InvalidOperationException>异常。</span><span class="sxs-lookup"><span data-stu-id="e8721-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="e8721-141">下面的示例演示读取该变量的推荐的方式`numberOfChildren`的前面的示例。</span><span class="sxs-lookup"><span data-stu-id="e8721-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="e8721-142">可以为 Null 的类型比较</span><span class="sxs-lookup"><span data-stu-id="e8721-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="e8721-143">可以为 null 时`Boolean`布尔表达式中使用变量，将会导致`True`， `False`，或`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e8721-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="e8721-144">以下是真值表`And`和`Or`。</span><span class="sxs-lookup"><span data-stu-id="e8721-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="e8721-145">因为`b1`和`b2`现在具有三个可能的值，有九个要计算的组合。</span><span class="sxs-lookup"><span data-stu-id="e8721-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="e8721-146">B1</span><span class="sxs-lookup"><span data-stu-id="e8721-146">b1</span></span>|<span data-ttu-id="e8721-147">B2</span><span class="sxs-lookup"><span data-stu-id="e8721-147">b2</span></span>|<span data-ttu-id="e8721-148">b1 和 b2</span><span class="sxs-lookup"><span data-stu-id="e8721-148">b1 And b2</span></span>|<span data-ttu-id="e8721-149">b1 或 b2</span><span class="sxs-lookup"><span data-stu-id="e8721-149">b1 Or b2</span></span>|  
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
  
 <span data-ttu-id="e8721-150">当布尔变量或表达式的值是`Nothing`，它既不是`true`也不`false`。</span><span class="sxs-lookup"><span data-stu-id="e8721-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="e8721-151">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="e8721-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 <span data-ttu-id="e8721-152">在此示例中，`b1 And b2`计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e8721-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="e8721-153">因此，`Else`子句执行在每个`If`语句，并输出是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8721-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="e8721-154">`AndAlso` 和`OrElse`，使用短路计算，必须计算其第二个操作数，当第一个计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e8721-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="e8721-155">传播</span><span class="sxs-lookup"><span data-stu-id="e8721-155">Propagation</span></span>  
 <span data-ttu-id="e8721-156">如果一个或两个操作数的算术、 比较、 shift 键或类型操作可以为 null，该操作的结果也是可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e8721-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="e8721-157">如果两个操作数的值都不`Nothing`，操作数的基础值执行此操作，就像它们都不是 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="e8721-158">在下面的示例中，变量`compare1`和`sum1`隐式类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="e8721-159">如果鼠标指针停留在它们上时，你会看到编译器的这两个推断可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 <span data-ttu-id="e8721-160">如果一个或两个操作数都具有值为`Nothing`，结果将是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e8721-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="e8721-161">使用数据使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="e8721-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="e8721-162">数据库是一个最重要的位数，以将其可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="e8721-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="e8721-163">并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器。</span><span class="sxs-lookup"><span data-stu-id="e8721-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="e8721-164">请参阅中的"为 Null 的类型的 TableAdapter 支持" [TableAdapter 概述](/visualstudio/data-tools/tableadapter-overview)。</span><span class="sxs-lookup"><span data-stu-id="e8721-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8721-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8721-165">See Also</span></span>  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [<span data-ttu-id="e8721-166">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="e8721-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="e8721-167">数据类型</span><span class="sxs-lookup"><span data-stu-id="e8721-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e8721-168">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e8721-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e8721-169">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="e8721-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="e8721-170">TableAdapter 概述</span><span class="sxs-lookup"><span data-stu-id="e8721-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)  
 [<span data-ttu-id="e8721-171">If 运算符</span><span class="sxs-lookup"><span data-stu-id="e8721-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="e8721-172">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="e8721-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="e8721-173">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="e8721-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="e8721-174">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="e8721-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
