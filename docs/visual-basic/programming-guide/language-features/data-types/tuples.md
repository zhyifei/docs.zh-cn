---
title: 在 Visual Basic 中的元组
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 146e9c2360cea153d2f487769d5b983516861e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663292"
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="5b33b-102">元组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b33b-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="5b33b-103">从 Visual Basic 2017 开始，Visual Basic 语言提供了对元组构成的内置支持创建元组和访问的元素的元组更容易。</span><span class="sxs-lookup"><span data-stu-id="5b33b-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="5b33b-104">元组是具有特定数量和值序列的轻量级数据结构。</span><span class="sxs-lookup"><span data-stu-id="5b33b-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="5b33b-105">时实例化元组，您定义的数量以及每个值 （或元素） 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="5b33b-106">例如，2 元组 （或对） 具有两个元素。</span><span class="sxs-lookup"><span data-stu-id="5b33b-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="5b33b-107">第一个可能`Boolean`值，而第二个是`String`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="5b33b-108">元组，能够轻松存储单个对象中的多个值，因为它们通常用作简便的方法从方法返回多个值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b33b-109">元组支持需要<xref:System.ValueTuple>类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="5b33b-110">如果未安装.NET Framework 4.7，则必须添加 NuGet 包`System.ValueTuple`，即在 NuGet 库上可用。</span><span class="sxs-lookup"><span data-stu-id="5b33b-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="5b33b-111">无此包，您可能会收到编译错误类似于"'ValueTuple(Of,,,) 未定义或导入预定义类型。"</span><span class="sxs-lookup"><span data-stu-id="5b33b-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="5b33b-112">实例化并使用元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="5b33b-113">您通过封闭它以逗号分隔的值的 im 括号实例化一个元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="5b33b-114">每个这些值然后将成为元组的字段。</span><span class="sxs-lookup"><span data-stu-id="5b33b-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="5b33b-115">下面的代码，如与定义了三次 （或 3 元组）`Date`作为其第一个值，`String`作为其第二，和一个`Boolean`作为其第三个。</span><span class="sxs-lookup"><span data-stu-id="5b33b-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="5b33b-116">默认情况下，元组中每个字段的名称包含字符串的`Item`以及字段的元组中的基于 1 的位置。</span><span class="sxs-lookup"><span data-stu-id="5b33b-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="5b33b-117">对于此 3-元组，`Date`字段是`Item1`，则`String`字段是`Item2`，并`Boolean`字段是`Item3`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="5b33b-118">下面的示例显示在上一行代码中实例化的元组字段的值</span><span class="sxs-lookup"><span data-stu-id="5b33b-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="5b33b-119">Visual Basic 元组字段是可读写;已实例化一个元组后，可以修改其值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="5b33b-120">下面的示例修改两个元组在上一示例中创建的三个字段，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="5b33b-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="5b33b-121">实例化和使用命名元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="5b33b-122">而不是使用元组的字段的默认名称，可以实例化*命名元组*通过将自己的名称分配给此元组的元素。</span><span class="sxs-lookup"><span data-stu-id="5b33b-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="5b33b-123">可以通过分配名称访问元组的字段*或*按其默认名称。</span><span class="sxs-lookup"><span data-stu-id="5b33b-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="5b33b-124">下面的示例实例化同一个 3 元组，不同之处在于它进行显式命名的第一个字段`EventDate`，第二个`Name`，第三个`IsHoliday`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="5b33b-125">然后显示字段值，修改它们，并再次显示字段值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="5b33b-126">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="5b33b-126">Inferred tuple element names</span></span>

<span data-ttu-id="5b33b-127">从 Visual Basic 15.3 开始，Visual Basic 可以推断元组元素，则名称不需要显式将其分配。</span><span class="sxs-lookup"><span data-stu-id="5b33b-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="5b33b-128">初始化的变量，一组元组，并且想要为变量的名称相同的元组元素名称时，推断元组名称很有用。</span><span class="sxs-lookup"><span data-stu-id="5b33b-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="5b33b-129">下面的示例创建`stateInfo`显式包含三个元组命名的元素， `state`， `stateName`，和`capital`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="5b33b-130">请注意，在命名元素，元组初始化语句只需将分配已命名的元素具有相同名称的变量的值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="5b33b-131">元素和变量具有相同的名称，因为 Visual Basic 编译器可以推断出的字段的名称，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5b33b-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="5b33b-132">若要启用推断元组元素名称，必须定义要在 Visual Basic 项目中使用的 Visual Basic 编译器的版本 (\*.vbproj) 文件：</span><span class="sxs-lookup"><span data-stu-id="5b33b-132">To enable inferred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

<span data-ttu-id="5b33b-133">版本号可以是任何版本的 Visual Basic 编译器从 15.3 开始。</span><span class="sxs-lookup"><span data-stu-id="5b33b-133">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="5b33b-134">而不是硬编码特定编译器版本，您还可以指定"Latest"的值作为`LangVersion`使用 Visual Basic 编译器在系统上安装的最新版本进行编译。</span><span class="sxs-lookup"><span data-stu-id="5b33b-134">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="5b33b-135">有关详细信息，请参阅[设置的 Visual Basic 语言版本](../../../language-reference/configure-language-version.md)。</span><span class="sxs-lookup"><span data-stu-id="5b33b-135">For more information, see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="5b33b-136">在某些情况下，Visual Basic 编译器无法推断元组元素名称从候选名称，并且仅可以使用其默认名称，例如引用元组字段`Item1`， `Item2`，等等。这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="5b33b-136">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="5b33b-137">候选名称是元组成员的名称相同例如`Item3`， `Rest`，或`ToString`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-137">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="5b33b-138">候选名称重复元组中。</span><span class="sxs-lookup"><span data-stu-id="5b33b-138">The candidate name is duplicated in the tuple.</span></span>
 
<span data-ttu-id="5b33b-139">当字段名称推理失败时，Visual Basic 不会生成编译器错误，也不是在运行时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="5b33b-139">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="5b33b-140">相反，元组字段必须引用按预定义名称，如`Item1`和`Item2`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-140">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span> 
  
## <a name="tuples-versus-structures"></a><span data-ttu-id="5b33b-141">与结构的元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-141">Tuples versus structures</span></span>

<span data-ttu-id="5b33b-142">Visual Basic 元组是值类型之一的实例**System.ValueTuple**泛型类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-142">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="5b33b-143">例如，`holiday`在上一示例中定义的元组是的一个实例<xref:System.ValueTuple%603>结构。</span><span class="sxs-lookup"><span data-stu-id="5b33b-143">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="5b33b-144">它被旨在作为数据的轻量容器。</span><span class="sxs-lookup"><span data-stu-id="5b33b-144">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="5b33b-145">由于元组的目的是为了更加轻松地使用多个数据项创建一个对象，它缺乏一些自定义结构可能具有的功能。</span><span class="sxs-lookup"><span data-stu-id="5b33b-145">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="5b33b-146">这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="5b33b-146">These include:</span></span>

- <span data-ttu-id="5b33b-147">自定义成员。</span><span class="sxs-lookup"><span data-stu-id="5b33b-147">Custom members.</span></span> <span data-ttu-id="5b33b-148">不能定义自己的属性、 方法或事件的元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-148">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="5b33b-149">验证。</span><span class="sxs-lookup"><span data-stu-id="5b33b-149">Validation.</span></span> <span data-ttu-id="5b33b-150">无法验证指派给字段的数据。</span><span class="sxs-lookup"><span data-stu-id="5b33b-150">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="5b33b-151">保持不变。</span><span class="sxs-lookup"><span data-stu-id="5b33b-151">Immutability.</span></span> <span data-ttu-id="5b33b-152">Visual Basic 元组是可变的。</span><span class="sxs-lookup"><span data-stu-id="5b33b-152">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="5b33b-153">与此相反，自定义结构允许您控制实例是否为可变或不可变。</span><span class="sxs-lookup"><span data-stu-id="5b33b-153">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="5b33b-154">如果自定义成员、 属性和字段验证或不可变性很重要，则应使用 Visual Basic[结构](../../../language-reference/statements/structure-statement.md)语句来定义自定义值类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-154">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="5b33b-155">Visual Basic 元组的成员来继承其**ValueTuple**类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-155">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="5b33b-156">除了其字段，其中包括以下方法：</span><span class="sxs-lookup"><span data-stu-id="5b33b-156">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="5b33b-157">成员</span><span class="sxs-lookup"><span data-stu-id="5b33b-157">Member</span></span> | <span data-ttu-id="5b33b-158">描述</span><span class="sxs-lookup"><span data-stu-id="5b33b-158">Description</span></span> |
| ---|---|
| <span data-ttu-id="5b33b-159">CompareTo</span><span class="sxs-lookup"><span data-stu-id="5b33b-159">CompareTo</span></span> | <span data-ttu-id="5b33b-160">比较具有相同的元素数的另一个元组的当前元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-160">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="5b33b-161">Equals</span><span class="sxs-lookup"><span data-stu-id="5b33b-161">Equals</span></span> | <span data-ttu-id="5b33b-162">确定是否等于另一个元组或对象的当前元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-162">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="5b33b-163">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="5b33b-163">GetHashCode</span></span> | <span data-ttu-id="5b33b-164">计算当前实例的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="5b33b-164">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="5b33b-165">ToString</span><span class="sxs-lookup"><span data-stu-id="5b33b-165">ToString</span></span> | <span data-ttu-id="5b33b-166">返回此元组，其形式的字符串表示形式`(Item1, Item2...)`，其中`Item1`和`Item2`表示元组的字段的值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-166">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="5b33b-167">此外， **ValueTuple**类型可实现<xref:System.Collections.IStructuralComparable>和<xref:System.Collections.IStructuralEquatable>接口，使您可以定义客户比较器。</span><span class="sxs-lookup"><span data-stu-id="5b33b-167">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="5b33b-168">赋值和元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-168">Assignment and tuples</span></span>

<span data-ttu-id="5b33b-169">Visual Basic 支持具有相同数量的字段的元组类型之间的赋值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-169">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="5b33b-170">如果以下项之一为 true，则可以转换的字段类型：</span><span class="sxs-lookup"><span data-stu-id="5b33b-170">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="5b33b-171">源和目标字段是属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-171">The source and target field are of the same type.</span></span>

- <span data-ttu-id="5b33b-172">扩大 （或隐式） 转换的源类型，为目标类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b33b-172">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="5b33b-173">`Option Strict` 是`On`，和收缩 （或显式） 转换的源类型，为目标类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b33b-173">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="5b33b-174">如果源值为目标类型的范围之外，此转换可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="5b33b-174">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="5b33b-175">对于其他转换，不考虑进行赋值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-175">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="5b33b-176">让我们看一下元组类型之间允许的赋值类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-176">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="5b33b-177">注意以下示例中使用的这些变量：</span><span class="sxs-lookup"><span data-stu-id="5b33b-177">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="5b33b-178">前两个变量，`unnamed`和`anonymous`，没有为字段提供语义名称。</span><span class="sxs-lookup"><span data-stu-id="5b33b-178">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="5b33b-179">其字段名称，则进行默认`Item1`和`Item2`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-179">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="5b33b-180">两个变量`named`和`differentName`具有语义的字段名称。</span><span class="sxs-lookup"><span data-stu-id="5b33b-180">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="5b33b-181">请注意，这两个元组具有不同的字段名称。</span><span class="sxs-lookup"><span data-stu-id="5b33b-181">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="5b33b-182">这四个元组具有相同数量的字段 （称为实参数量），并且这些字段的类型也完全一样。</span><span class="sxs-lookup"><span data-stu-id="5b33b-182">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="5b33b-183">因此可进行以下赋值：</span><span class="sxs-lookup"><span data-stu-id="5b33b-183">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="5b33b-184">请注意，元组的名称未赋值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-184">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="5b33b-185">字段的赋值顺序遵循字段在元组中的顺序。</span><span class="sxs-lookup"><span data-stu-id="5b33b-185">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="5b33b-186">最后，请注意，我们可以将分配`named`元组`conversion`元组，即使的第一个字段`named`是`Integer`，和的第一个字段`conversion`是`Long`。</span><span class="sxs-lookup"><span data-stu-id="5b33b-186">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="5b33b-187">此分配将成功，因为转换`Integer`到`Long`的扩大转换。</span><span class="sxs-lookup"><span data-stu-id="5b33b-187">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="5b33b-188">具有不同数量的字段的元组不可赋值：</span><span class="sxs-lookup"><span data-stu-id="5b33b-188">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="5b33b-189">作为方法返回值的元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-189">Tuples as method return values</span></span>

<span data-ttu-id="5b33b-190">一种方法可以返回单个值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-190">A method can return only a single value.</span></span> <span data-ttu-id="5b33b-191">通常情况下，不过，您可能希望方法调用返回多个值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-191">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="5b33b-192">有几种方法来解决此限制：</span><span class="sxs-lookup"><span data-stu-id="5b33b-192">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="5b33b-193">您可以创建自定义类或结构，其属性或字段表示该方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-193">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="5b33b-194">因此是一个重量级解决方案;它需要定义其唯一用途是从方法调用中检索值的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-194">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="5b33b-195">可以从方法返回单个值，并返回剩余的值，向它们传递到方法的引用。</span><span class="sxs-lookup"><span data-stu-id="5b33b-195">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="5b33b-196">这涉及到的实例化变量和风险无意中覆盖通过引用传递的变量的值的开销。</span><span class="sxs-lookup"><span data-stu-id="5b33b-196">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="5b33b-197">可以使用元组，提供了一种轻量型解决方案检索多个返回值。</span><span class="sxs-lookup"><span data-stu-id="5b33b-197">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="5b33b-198">例如， **TryParse**方法在.NET 返回`Boolean`值，该值指示是否在分析操作成功。</span><span class="sxs-lookup"><span data-stu-id="5b33b-198">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="5b33b-199">在分析操作的结果中的变量通过引用传递给该方法返回。</span><span class="sxs-lookup"><span data-stu-id="5b33b-199">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="5b33b-200">通常情况下，调用分析方法如<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b33b-200">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="5b33b-201">我们可以从在分析操作返回一个元组，如果我们换行到调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>我们自己的方法中的方法。</span><span class="sxs-lookup"><span data-stu-id="5b33b-201">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="5b33b-202">在以下示例中，`NumericLibrary.ParseInteger`调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法，并返回具有两个元素的命名元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-202">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="5b33b-203">然后可以调用的方法，如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="5b33b-203">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="5b33b-204">Visual Basic 元组和.NET Framework 中的元组</span><span class="sxs-lookup"><span data-stu-id="5b33b-204">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="5b33b-205">Visual Basic 元组是之一的实例**System.ValueTuple**泛型类型，.NET Framework 4.7 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5b33b-205">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="5b33b-206">.NET Framework 还包括一组泛型**System.Tuple**类。</span><span class="sxs-lookup"><span data-stu-id="5b33b-206">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="5b33b-207">但是，这些类，与 Visual Basic 元组的不同， **System.ValueTuple**通过多种方式中的泛型类型：</span><span class="sxs-lookup"><span data-stu-id="5b33b-207">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="5b33b-208">元素**元组**类是属性名为`Item1`， `Item2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="5b33b-208">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="5b33b-209">在 Visual Basic 元组中， **ValueTuple**元组元素类型是字段。</span><span class="sxs-lookup"><span data-stu-id="5b33b-209">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="5b33b-210">不能将有意义的名称分配到的元素**元组**实例或**ValueTuple**实例。</span><span class="sxs-lookup"><span data-stu-id="5b33b-210">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="5b33b-211">Visual Basic 可以为分配通信的字段的含义的名称。</span><span class="sxs-lookup"><span data-stu-id="5b33b-211">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="5b33b-212">属性**元组**实例是只读的; 元组是固定不变。</span><span class="sxs-lookup"><span data-stu-id="5b33b-212">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="5b33b-213">在 Visual Basic 元组中， **ValueTuple**类型，元组字段是可读写; 元组是可变。</span><span class="sxs-lookup"><span data-stu-id="5b33b-213">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="5b33b-214">泛型**元组**类型是引用类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-214">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="5b33b-215">使用这些**元组**类型即意味着分配对象。</span><span class="sxs-lookup"><span data-stu-id="5b33b-215">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="5b33b-216">在热路径中，这可能会对应用程序性能产生明显的影响。</span><span class="sxs-lookup"><span data-stu-id="5b33b-216">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="5b33b-217">Visual Basic 元组和**ValueTuple**类型是值类型。</span><span class="sxs-lookup"><span data-stu-id="5b33b-217">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="5b33b-218">中的扩展方法<xref:System.TupleExtensions>类轻松地转换 Visual Basic 元组和.NET 之间**元组**对象。</span><span class="sxs-lookup"><span data-stu-id="5b33b-218">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="5b33b-219">**ToTuple**方法将 Visual Basic 元组转换为.NET**元组**对象，并且**ToValueTuple**方法将为.NET**元组**为 Visual Basic 元组的对象。</span><span class="sxs-lookup"><span data-stu-id="5b33b-219">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="5b33b-220">以下示例创建的元组，将其转换为.NET**元组**对象，并将转换回 Visual Basic 元组。</span><span class="sxs-lookup"><span data-stu-id="5b33b-220">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="5b33b-221">然后，该示例比较了此元组，其原始的一个，以确保它们相等。</span><span class="sxs-lookup"><span data-stu-id="5b33b-221">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="5b33b-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b33b-222">See also</span></span>

- [<span data-ttu-id="5b33b-223">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="5b33b-223">Visual Basic Language Reference</span></span>](index.md)
