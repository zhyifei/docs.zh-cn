---
title: "可以为 null 的值类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
dev_langs:
- VB
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 226ffb8a329e31576c9a8120940c683ad10a030b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="0229e-102">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0229e-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="0229e-103">有时，您将使用的值类型，在某些情况下没有已定义的值。</span><span class="sxs-lookup"><span data-stu-id="0229e-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="0229e-104">例如，数据库中的字段可能需要区分具有分配的值有意义，而不让分配的值。</span><span class="sxs-lookup"><span data-stu-id="0229e-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="0229e-105">可以扩展值类型，以使其正常值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="0229e-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="0229e-106">调用此类扩展*可空类型*。</span><span class="sxs-lookup"><span data-stu-id="0229e-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="0229e-107">每个可以为 null 的类型从泛型构造<xref:System.Nullable%601>结构。</xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="0229e-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="0229e-108">请考虑用于跟踪与工作相关的活动数据库。</span><span class="sxs-lookup"><span data-stu-id="0229e-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="0229e-109">下面的示例构造一个可以为 null`Boolean`类型，并声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="0229e-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="0229e-110">你可以以下三种方式来编写声明︰</span><span class="sxs-lookup"><span data-stu-id="0229e-110">You can write the declaration in three ways:</span></span>  
  
 <span data-ttu-id="0229e-111">[!code-vb[VbVbalrNullableValue #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-111">[!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]</span></span>  
  
 <span data-ttu-id="0229e-112">该变量`ridesBusToWork`可以包含的值`True`，值为`False`，或者根本没有值。</span><span class="sxs-lookup"><span data-stu-id="0229e-112">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="0229e-113">它的初始默认值根本没有值，它在这种情况下可能意味着，信息具有尚未获得此人。</span><span class="sxs-lookup"><span data-stu-id="0229e-113">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="0229e-114">与此相反，`False`可能是获取的信息，而此人未乘坐公共汽车去上班。</span><span class="sxs-lookup"><span data-stu-id="0229e-114">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="0229e-115">可以使用可以为 null 的类型来声明变量和属性，而您可以声明具有可以为 null 的类型的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="0229e-115">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="0229e-116">可以使用作为参数，可以为 null 的类型来声明过程，并可以返回 null 的类型从`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="0229e-116">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="0229e-117">无法构造上如数组、 引用类型的可以为 null 类型`String`，或类。</span><span class="sxs-lookup"><span data-stu-id="0229e-117">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="0229e-118">基础类型必须是值类型。</span><span class="sxs-lookup"><span data-stu-id="0229e-118">The underlying type must be a value type.</span></span> <span data-ttu-id="0229e-119">有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0229e-119">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="0229e-120">使用可以为 Null 的类型变量</span><span class="sxs-lookup"><span data-stu-id="0229e-120">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="0229e-121">可以为 null 的类型的最重要的成员是其<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>属性。</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-121">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="0229e-122">对于可空类型的变量<xref:System.Nullable%601.HasValue%2A>告诉您此变量是否包含已定义的值。</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-122">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="0229e-123">如果<xref:System.Nullable%601.HasValue%2A>是`True`，你可以读取的值从<xref:System.Nullable%601.Value%2A>。</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-123">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="0229e-124">请注意，这两<xref:System.Nullable%601.HasValue%2A>和<xref:System.Nullable%601.Value%2A>是`ReadOnly`属性。</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-124">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="0229e-125">默认值</span><span class="sxs-lookup"><span data-stu-id="0229e-125">Default Values</span></span>  
 <span data-ttu-id="0229e-126">在与 null 的类型，声明一个变量时其<xref:System.Nullable%601.HasValue%2A>属性具有默认值为`False`。</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-126">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="0229e-127">这意味着默认情况下该变量具有未定义的值，而不是其基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="0229e-127">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="0229e-128">在下面的示例中，该变量`numberOfChildren`最初具有未定义的值，即使默认值的`Integer`类型为 0。</span><span class="sxs-lookup"><span data-stu-id="0229e-128">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 <span data-ttu-id="0229e-129">[!code-vb[VbVbalrNullableValue #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-129">[!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]</span></span>  
  
 <span data-ttu-id="0229e-130">空值可用于指示未定义的或未知的值。</span><span class="sxs-lookup"><span data-stu-id="0229e-130">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="0229e-131">如果`numberOfChildren`已声明为`Integer`，不会有任何值，则表明，信息当前不可用。</span><span class="sxs-lookup"><span data-stu-id="0229e-131">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="0229e-132">将值存储</span><span class="sxs-lookup"><span data-stu-id="0229e-132">Storing Values</span></span>  
 <span data-ttu-id="0229e-133">典型方式，可以在变量或可以为 null 的类型的属性中存储一个值。</span><span class="sxs-lookup"><span data-stu-id="0229e-133">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="0229e-134">下面的示例将值赋给变量`numberOfChildren`在前面的示例中声明。</span><span class="sxs-lookup"><span data-stu-id="0229e-134">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 <span data-ttu-id="0229e-135">[!code-vb[VbVbalrNullableValue #&3;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-135">[!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]</span></span>  
  
 <span data-ttu-id="0229e-136">如果变量或可以为 null 的类型的属性中包含已定义的值，则可以使此恢复到其初始状态，即未获分配的值。</span><span class="sxs-lookup"><span data-stu-id="0229e-136">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="0229e-137">执行此操作通过设置该变量或属性设置为`Nothing`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="0229e-137">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 <span data-ttu-id="0229e-138">[!code-vb[VbVbalrNullableValue #&4;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-138">[!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0229e-139">虽然您可分配`Nothing`给可以为 null 的类型的变量，不能测试它以`Nothing`使用等号。</span><span class="sxs-lookup"><span data-stu-id="0229e-139">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="0229e-140">比较过程中使用等号`someVar = Nothing`，计算结果始终为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0229e-140">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="0229e-141">您可以测试该变量<xref:System.Nullable%601.HasValue%2A>属性`False`，或通过使用测试`Is`或`IsNot`运算符。</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-141">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="0229e-142">检索值</span><span class="sxs-lookup"><span data-stu-id="0229e-142">Retrieving Values</span></span>  
 <span data-ttu-id="0229e-143">若要检索的值可以为 null 的类型的变量，应该首先测试其<xref:System.Nullable%601.HasValue%2A>属性，以确认它具有值。</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-143">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="0229e-144">如果您尝试读取值时<xref:System.Nullable%601.HasValue%2A>是`False`，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]引发<xref:System.InvalidOperationException>异常。</xref:System.InvalidOperationException> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-144">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="0229e-145">下面的示例演示读取该变量的推荐的方式`numberOfChildren`的前面的示例。</span><span class="sxs-lookup"><span data-stu-id="0229e-145">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 <span data-ttu-id="0229e-146">[!code-vb[VbVbalrNullableValue #&5;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-146">[!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]</span></span>  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="0229e-147">比较 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="0229e-147">Comparing Nullable Types</span></span>  
 <span data-ttu-id="0229e-148">可以为 null 时`Boolean`在布尔表达式中使用变量，结果可能`True`， `False`，或`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0229e-148">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="0229e-149">下面是真值表`And`和`Or`。</span><span class="sxs-lookup"><span data-stu-id="0229e-149">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="0229e-150">因为`b1`和`b2`现在具有三个可能值有九种组合来评估。</span><span class="sxs-lookup"><span data-stu-id="0229e-150">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="0229e-151">b1</span><span class="sxs-lookup"><span data-stu-id="0229e-151">b1</span></span>|<span data-ttu-id="0229e-152">b2</span><span class="sxs-lookup"><span data-stu-id="0229e-152">b2</span></span>|<span data-ttu-id="0229e-153">b1 和 b2</span><span class="sxs-lookup"><span data-stu-id="0229e-153">b1 And b2</span></span>|<span data-ttu-id="0229e-154">b1 或 b2</span><span class="sxs-lookup"><span data-stu-id="0229e-154">b1 Or b2</span></span>|  
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
  
 <span data-ttu-id="0229e-155">一个布尔型变量或表达式的值时`Nothing`，它既不是`true`也`false`。</span><span class="sxs-lookup"><span data-stu-id="0229e-155">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="0229e-156">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="0229e-156">Consider the following example.</span></span>  
  
 <span data-ttu-id="0229e-157">[!code-vb[VbVbalrNullableValue #&6;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-157">[!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]</span></span>  
  
 <span data-ttu-id="0229e-158">在此示例中，`b1 And b2`的计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0229e-158">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="0229e-159">因此，`Else`子句执行在每个`If`语句，并输出如下所述︰</span><span class="sxs-lookup"><span data-stu-id="0229e-159">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
> <span data-ttu-id="0229e-160"> `AndAlso`和`OrElse`，可使用该技术短路计算，必须评估其第二个操作数，当第一个计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0229e-160"> `AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="0229e-161">传播</span><span class="sxs-lookup"><span data-stu-id="0229e-161">Propagation</span></span>  
 <span data-ttu-id="0229e-162">如果一个或两个操作数的算术、 比较、 shift 键或类型运算可以为空，操作的结果也是可以为 null。</span><span class="sxs-lookup"><span data-stu-id="0229e-162">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="0229e-163">如果这两个操作数的值不是`Nothing`，如同它们都不是，对底层的操作数，值执行此操作可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="0229e-163">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="0229e-164">在下面的示例中，变量`compare1`和`sum1`隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="0229e-164">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="0229e-165">如果将鼠标指针停留在其上时，您将看到编译器将为 null 的类型推断为它们两个。</span><span class="sxs-lookup"><span data-stu-id="0229e-165">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 <span data-ttu-id="0229e-166">[!code-vb[VbVbalrNullableValue #&7;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-166">[!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]</span></span>  
  
 <span data-ttu-id="0229e-167">如果一个或两个操作数都具有值为`Nothing`，结果将是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0229e-167">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 <span data-ttu-id="0229e-168">[!code-vb[VbVbalrNullableValue #&8;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="0229e-168">[!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]</span></span>  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="0229e-169">数据中使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="0229e-169">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="0229e-170">数据库是一个最重要的地方使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="0229e-170">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="0229e-171">并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器。</span><span class="sxs-lookup"><span data-stu-id="0229e-171">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="0229e-172">请参阅中的"为 Null 的类型的 TableAdapter 支持" [TableAdapter 概述](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)。</span><span class="sxs-lookup"><span data-stu-id="0229e-172">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0229e-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0229e-173">See Also</span></span>  
 <span data-ttu-id="0229e-174"><xref:System.InvalidOperationException></xref:System.InvalidOperationException></span><span class="sxs-lookup"><span data-stu-id="0229e-174"><xref:System.InvalidOperationException></span></span>   
 <span data-ttu-id="0229e-175"><xref:System.Nullable%601.HasValue%2A></xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="0229e-175"><xref:System.Nullable%601.HasValue%2A></span></span>   
<span data-ttu-id="0229e-176"> [使用可以为 null 的类型](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-176"> [Using Nullable Types](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md) </span></span>  
<span data-ttu-id="0229e-177"> [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-177"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="0229e-178"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-178"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="0229e-179"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-179"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="0229e-180"> [TableAdapter 概述](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview) </span><span class="sxs-lookup"><span data-stu-id="0229e-180"> [TableAdapter Overview](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview) </span></span>  
<span data-ttu-id="0229e-181"> [如果运算符](../../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-181"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="0229e-182"> [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-182"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="0229e-183"> [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="0229e-183"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="0229e-184"> [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)</span><span class="sxs-lookup"><span data-stu-id="0229e-184"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)</span></span>
