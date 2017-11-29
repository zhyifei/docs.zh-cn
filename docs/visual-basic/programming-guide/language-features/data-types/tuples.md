---
title: "在 Visual Basic 中的元组"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be50b22e9acca9ff8cfbde798d78869ee1c72634
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="3517d-102">元组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3517d-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="3517d-103">从 Visual Basic 自 2017 年开始，Visual Basic 语言提供内置支持的元组，可创建元组和访问元组更容易的元素。</span><span class="sxs-lookup"><span data-stu-id="3517d-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="3517d-104">元组是具有特定的数量和值序列的轻量数据结构。</span><span class="sxs-lookup"><span data-stu-id="3517d-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="3517d-105">当实例化此元组时，你定义的数量以及每个值 （或元素） 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="3517d-106">例如的 2 元组 （或对） 有两个元素。</span><span class="sxs-lookup"><span data-stu-id="3517d-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="3517d-107">第一个可能`Boolean`值，而第二个是`String`。</span><span class="sxs-lookup"><span data-stu-id="3517d-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="3517d-108">元组建立方便地将多个值存储在单个对象，因为它们是通常用作一个简便的方法来从方法返回多个值。</span><span class="sxs-lookup"><span data-stu-id="3517d-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3517d-109">元组的支持，需要<xref:System.ValueTuple>类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="3517d-110">如果未安装.NET Framework 4.7，必须先添加 NuGet 包`System.ValueTuple`，即在 NuGet 库上可用。</span><span class="sxs-lookup"><span data-stu-id="3517d-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="3517d-111">而无需此包，你可能会收到编译错误类似于"预定义类型未定义或导入 ValueTuple(Of,,,)。</span><span class="sxs-lookup"><span data-stu-id="3517d-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="3517d-112">实例化并使用一个元组</span><span class="sxs-lookup"><span data-stu-id="3517d-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="3517d-113">通过将其以逗号分隔值 im 括号实例元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="3517d-114">每个这些值随后将成为此元组的字段。</span><span class="sxs-lookup"><span data-stu-id="3517d-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="3517d-115">例如，下面的代码定义三次 （或 3 元组），其中有`Date`作为其第一个值，`String`作为第二个操作数，和一个`Boolean`作为其第三个。</span><span class="sxs-lookup"><span data-stu-id="3517d-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="3517d-116">默认情况下，元组中每个字段的名称包含字符串`Item`以及字段的元组中的基于 1 的位置。</span><span class="sxs-lookup"><span data-stu-id="3517d-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="3517d-117">有关此 3 元组，`Date`字段是`Item1`、`String`字段是`Item2`，和`Boolean`字段是`Item3`。</span><span class="sxs-lookup"><span data-stu-id="3517d-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="3517d-118">下面的示例显示在之前的代码行中实例化此元组的字段的值</span><span class="sxs-lookup"><span data-stu-id="3517d-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="3517d-119">Visual Basic 元组的字段是读写;已实例化元组后，你可以修改其值。</span><span class="sxs-lookup"><span data-stu-id="3517d-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="3517d-120">下面的示例修改两个元组在前面的示例中创建的三个字段，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="3517d-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="3517d-121">实例化和使用命名的元组</span><span class="sxs-lookup"><span data-stu-id="3517d-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="3517d-122">而不是使用一个元组的字段的默认名称，可以实例化*名为元组*通过将您自己的名称分配给此元组的元素。</span><span class="sxs-lookup"><span data-stu-id="3517d-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="3517d-123">此元组的字段然后可由其分配名称访问*或*通过默认名称。</span><span class="sxs-lookup"><span data-stu-id="3517d-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="3517d-124">下面的示例实例化相同 3 元组作为以前，只不过它进行显式命名的第一个字段`EventDate`，第二个`Name`，第三个`IsHoliday`。</span><span class="sxs-lookup"><span data-stu-id="3517d-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="3517d-125">然后显示字段值，修改它们，并再次显示字段值。</span><span class="sxs-lookup"><span data-stu-id="3517d-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="tuples-versus-structures"></a><span data-ttu-id="3517d-126">与结构的元组</span><span class="sxs-lookup"><span data-stu-id="3517d-126">Tuples versus structures</span></span>

<span data-ttu-id="3517d-127">Visual Basic 元组是值类型之一的实例**System.ValueTuple**泛型类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-127">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="3517d-128">例如，`holiday`是的一个实例，在前面的示例中定义的元组<xref:System.ValueTuple%603>结构。</span><span class="sxs-lookup"><span data-stu-id="3517d-128">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="3517d-129">它被旨在作为数据的轻量容器。</span><span class="sxs-lookup"><span data-stu-id="3517d-129">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="3517d-130">因为此元组的目标是要更加轻松地使用多个数据项创建对象，但它缺少一些自定义结构可能具有的功能。</span><span class="sxs-lookup"><span data-stu-id="3517d-130">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="3517d-131">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="3517d-131">These include:</span></span>

- <span data-ttu-id="3517d-132">客户成员。</span><span class="sxs-lookup"><span data-stu-id="3517d-132">Customer members.</span></span> <span data-ttu-id="3517d-133">不能定义自己的属性、 方法或元组的事件。</span><span class="sxs-lookup"><span data-stu-id="3517d-133">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="3517d-134">验证。</span><span class="sxs-lookup"><span data-stu-id="3517d-134">Validation.</span></span> <span data-ttu-id="3517d-135">无法验证分配给字段的数据。</span><span class="sxs-lookup"><span data-stu-id="3517d-135">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="3517d-136">不是可变性。</span><span class="sxs-lookup"><span data-stu-id="3517d-136">Immutability.</span></span> <span data-ttu-id="3517d-137">Visual Basic 元组是可变的。</span><span class="sxs-lookup"><span data-stu-id="3517d-137">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="3517d-138">与此相反，自定义结构允许你控制实例是否可变或不可变。</span><span class="sxs-lookup"><span data-stu-id="3517d-138">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="3517d-139">如果自定义成员、 属性和字段验证或不可变性很重要，则应使用 Visual Basic[结构](../../../language-reference/statements/structure-statement.md)语句以定义自定义值类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-139">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="3517d-140">Visual Basic 元组未继承的成员其**ValueTuple**类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-140">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="3517d-141">除了其字段，这些方法包括以下方法：</span><span class="sxs-lookup"><span data-stu-id="3517d-141">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="3517d-142">成员</span><span class="sxs-lookup"><span data-stu-id="3517d-142">Member</span></span> | <span data-ttu-id="3517d-143">描述</span><span class="sxs-lookup"><span data-stu-id="3517d-143">Description</span></span> |
| ---|---|
| <span data-ttu-id="3517d-144">CompareTo</span><span class="sxs-lookup"><span data-stu-id="3517d-144">CompareTo</span></span> | <span data-ttu-id="3517d-145">比较到具有相同数量的元素的另一个元组的当前元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-145">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="3517d-146">Equals</span><span class="sxs-lookup"><span data-stu-id="3517d-146">Equals</span></span> | <span data-ttu-id="3517d-147">确定是否等于另一个元组或对象的当前元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-147">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="3517d-148">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="3517d-148">GetHashCode</span></span> | <span data-ttu-id="3517d-149">计算当前实例的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="3517d-149">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="3517d-150">ToString</span><span class="sxs-lookup"><span data-stu-id="3517d-150">ToString</span></span> | <span data-ttu-id="3517d-151">返回此元组，它采用的形式的字符串表示`(Item1, Item2...)`，其中`Item1`和`Item2`表示元组的字段的值。</span><span class="sxs-lookup"><span data-stu-id="3517d-151">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="3517d-152">此外， **ValueTuple**类型实现<xref:System.Collections.IStructuralComparable>和<xref:System.Collections.IStructuralEquatable>接口，可用于定义客户比较器。</span><span class="sxs-lookup"><span data-stu-id="3517d-152">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="3517d-153">赋值和元组</span><span class="sxs-lookup"><span data-stu-id="3517d-153">Assignment and tuples</span></span>

<span data-ttu-id="3517d-154">Visual Basic 支持具有相同数目的字段的元组类型之间的分配。</span><span class="sxs-lookup"><span data-stu-id="3517d-154">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="3517d-155">如果下列其中一项为 true，则可以转换的字段类型：</span><span class="sxs-lookup"><span data-stu-id="3517d-155">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="3517d-156">源和目标字段均为相同的类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-156">The source and target field are of the same type.</span></span>

- <span data-ttu-id="3517d-157">扩大 （或隐式） 转换的源类型，为目标类型定义。</span><span class="sxs-lookup"><span data-stu-id="3517d-157">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="3517d-158">`Option Strict`是`On`，和收缩 （或显式） 转换的源类型，为目标类型定义。</span><span class="sxs-lookup"><span data-stu-id="3517d-158">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="3517d-159">如果源值超出了目标类型的范围，此转换可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="3517d-159">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="3517d-160">对于其他转换，不考虑进行赋值。</span><span class="sxs-lookup"><span data-stu-id="3517d-160">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="3517d-161">让我们看一下元组类型之间允许的赋值类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-161">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="3517d-162">注意以下示例中使用的这些变量：</span><span class="sxs-lookup"><span data-stu-id="3517d-162">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="3517d-163">前两个变量，`unnamed`和`anonymous`，没有为字段提供的语义名称。</span><span class="sxs-lookup"><span data-stu-id="3517d-163">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="3517d-164">其字段名称就是默认`Item1`和`Item2`。</span><span class="sxs-lookup"><span data-stu-id="3517d-164">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="3517d-165">最后两个变量，`named`和`differentName`具有语义的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="3517d-165">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="3517d-166">请注意，这两个元组具有不同的字段名称。</span><span class="sxs-lookup"><span data-stu-id="3517d-166">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="3517d-167">这些元组的所有四个具有相同数目的字段 （称为 arity），并且这些字段的类型相同。</span><span class="sxs-lookup"><span data-stu-id="3517d-167">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="3517d-168">因此可进行以下赋值：</span><span class="sxs-lookup"><span data-stu-id="3517d-168">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="3517d-169">请注意，元组的名称未赋值。</span><span class="sxs-lookup"><span data-stu-id="3517d-169">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="3517d-170">字段的赋值顺序遵循字段在元组中的顺序。</span><span class="sxs-lookup"><span data-stu-id="3517d-170">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="3517d-171">最后，请注意，我们可以将分配`named`到的元组`conversion`元组，即使的第一个字段`named`是`Integer`，和的第一个字段`conversion`是`Long`。</span><span class="sxs-lookup"><span data-stu-id="3517d-171">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="3517d-172">此分配将成功，因为转换`Integer`到`Long`的扩大转换。</span><span class="sxs-lookup"><span data-stu-id="3517d-172">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="3517d-173">元组具有不同数量的字段不能分配：</span><span class="sxs-lookup"><span data-stu-id="3517d-173">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="3517d-174">作为方法返回值的元组</span><span class="sxs-lookup"><span data-stu-id="3517d-174">Tuples as method return values</span></span>

<span data-ttu-id="3517d-175">方法可以返回单个值。</span><span class="sxs-lookup"><span data-stu-id="3517d-175">A method can return only a single value.</span></span> <span data-ttu-id="3517d-176">通常情况下，不过，你想要的方法调用返回多个值。</span><span class="sxs-lookup"><span data-stu-id="3517d-176">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="3517d-177">有多种，若要解决此限制：</span><span class="sxs-lookup"><span data-stu-id="3517d-177">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="3517d-178">你可以创建自定义类或结构，其属性或字段表示由该方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="3517d-178">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="3517d-179">因此是一种 heavyweight 解决方案;它需要定义其唯一目的是从方法调用中检索值的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-179">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="3517d-180">你可以从方法返回单个值，并通过将它们传递通过对该方法的引用返回剩下的值。</span><span class="sxs-lookup"><span data-stu-id="3517d-180">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="3517d-181">这涉及到的实例化变量和风险无意中重写的变量通过引用传递的值的开销。</span><span class="sxs-lookup"><span data-stu-id="3517d-181">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="3517d-182">你可以使用一个元组，它提供一种轻量型解决方案检索多个返回值。</span><span class="sxs-lookup"><span data-stu-id="3517d-182">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="3517d-183">例如， **TryParse** .NET 返回中的方法`Boolean`值，该值指示是否在分析操作成功。</span><span class="sxs-lookup"><span data-stu-id="3517d-183">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="3517d-184">在分析操作的结果在变量通过引用传递给该方法返回。</span><span class="sxs-lookup"><span data-stu-id="3517d-184">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="3517d-185">通常情况下，调用分析方法如<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>如下所示：</span><span class="sxs-lookup"><span data-stu-id="3517d-185">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="3517d-186">我们可以从在分析操作返回一个元组，如果我们包装对调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>在我们自己的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="3517d-186">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="3517d-187">在下面的示例中，`NumericLibrary.ParseInteger`调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法并返回具有两个元素的命名元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-187">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="3517d-188">然后，可以调用此方法的代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="3517d-188">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="3517d-189">Visual Basic 元组和.NET Framework 中的元组</span><span class="sxs-lookup"><span data-stu-id="3517d-189">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="3517d-190">Visual Basic 元组是之一的实例**System.ValueTuple**在.NET Framework 4.7 中引入的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-190">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="3517d-191">.NET Framework 还包括一套泛型**System.Tuple**类。</span><span class="sxs-lookup"><span data-stu-id="3517d-191">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="3517d-192">这些类，但是，不同于 Visual Basic 元组和**System.ValueTuple**通过多种方式中的泛型类型：</span><span class="sxs-lookup"><span data-stu-id="3517d-192">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="3517d-193">元素**元组**类是属性名为`Item1`， `Item2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3517d-193">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="3517d-194">在 Visual Basic 元组和**ValueTuple**类型，对元组元素是字段。</span><span class="sxs-lookup"><span data-stu-id="3517d-194">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="3517d-195">不能将有意义的名称分配到的元素**元组**实例或**ValueTuple**实例。</span><span class="sxs-lookup"><span data-stu-id="3517d-195">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="3517d-196">Visual Basic，可分配传达的含义的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="3517d-196">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="3517d-197">属性**元组**实例是只读的; 元组是不可变。</span><span class="sxs-lookup"><span data-stu-id="3517d-197">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="3517d-198">在 Visual Basic 元组和**ValueTuple**类型，元组字段是可读写; 元组是可变的。</span><span class="sxs-lookup"><span data-stu-id="3517d-198">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="3517d-199">泛型**元组**类型是引用类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-199">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="3517d-200">使用这些**元组**类型分配对象的方式。</span><span class="sxs-lookup"><span data-stu-id="3517d-200">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="3517d-201">在热路径中，这可能会对应用程序性能产生明显的影响。</span><span class="sxs-lookup"><span data-stu-id="3517d-201">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="3517d-202">Visual Basic 元组和**ValueTuple**类型是值类型。</span><span class="sxs-lookup"><span data-stu-id="3517d-202">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="3517d-203">中的扩展方法<xref:System.TupleExtensions>类，更易于 Visual Basic 元组和.NET 之间转换**元组**对象。</span><span class="sxs-lookup"><span data-stu-id="3517d-203">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="3517d-204">**ToTuple**方法将 Visual Basic 元组转换为.NET**元组**对象，与**ToValueTuple**方法将转换.NET**元组**Visual Basic 元组对象。</span><span class="sxs-lookup"><span data-stu-id="3517d-204">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="3517d-205">下面的示例中创建元组，将其转换为.NET**元组**对象，并将转换回 Visual Basic 元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-205">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="3517d-206">然后，示例进行比较以确保它们相等替换为原始此元组。</span><span class="sxs-lookup"><span data-stu-id="3517d-206">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="3517d-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="3517d-207">See also</span></span>

[<span data-ttu-id="3517d-208">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="3517d-208">Visual Basic Language Reference</span></span>](index.md)  
