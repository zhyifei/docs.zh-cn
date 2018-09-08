---
title: 度量单位 (F#)
description: '了解如何浮点和 F # 中的带符号的整数值可以具有关联的度量值，这些信息通常用于指示长度、 卷和大容量单位。'
ms.date: 05/16/2016
ms.openlocfilehash: ad2193e25f3c0cee6e73cd529ab43d1e4b6b549b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187882"
---
# <a name="units-of-measure"></a><span data-ttu-id="c0a54-103">度量单位</span><span class="sxs-lookup"><span data-stu-id="c0a54-103">Units of Measure</span></span>

<span data-ttu-id="c0a54-104">F # 中的浮点点和带符号的整数值可以具有关联之类的度量单位通常用于指示长度、 体积、 成批，依此类推。</span><span class="sxs-lookup"><span data-stu-id="c0a54-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="c0a54-105">通过使用个单位的数量，使编译器无法验证算术关系具有正确的单位，从而有助于防止出现编程错误。</span><span class="sxs-lookup"><span data-stu-id="c0a54-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0a54-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0a54-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="c0a54-107">备注</span><span class="sxs-lookup"><span data-stu-id="c0a54-107">Remarks</span></span>

<span data-ttu-id="c0a54-108">上述语法中定义*单元名称*作为一个单元的度量值。</span><span class="sxs-lookup"><span data-stu-id="c0a54-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="c0a54-109">可选部分用于定义新的度量值根据以前定义的单位。</span><span class="sxs-lookup"><span data-stu-id="c0a54-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="c0a54-110">例如，以下行定义度量值`cm`（厘米）。</span><span class="sxs-lookup"><span data-stu-id="c0a54-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="c0a54-111">下面的行定义度量值`ml`（毫升） 为立方厘米 (`cm^3`)。</span><span class="sxs-lookup"><span data-stu-id="c0a54-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="c0a54-112">在上述语法中，*度量值*是涉及到单元的公式。</span><span class="sxs-lookup"><span data-stu-id="c0a54-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="c0a54-113">在涉及单元的公式，（正值和负值） 支持整数幂，单位之间的空格指示两个单位的产品`*`还表示的单位，产品和`/`指示的单位的商。</span><span class="sxs-lookup"><span data-stu-id="c0a54-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="c0a54-114">对于相应的单元，可以使用负的整数幂或`/`，该值指示分子和分母的单元公式之间的分隔。</span><span class="sxs-lookup"><span data-stu-id="c0a54-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="c0a54-115">在分母中的多个单元应由括号括起来。</span><span class="sxs-lookup"><span data-stu-id="c0a54-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="c0a54-116">用后的空格分隔的单位`/`被解释为属于分母，但后面的任何单位`*`将被解释为分子的一部分。</span><span class="sxs-lookup"><span data-stu-id="c0a54-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="c0a54-117">在单元表达式中，可以单独以指示纲数量，或者与其他单位，例如分子，可以使用 1。</span><span class="sxs-lookup"><span data-stu-id="c0a54-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="c0a54-118">例如，速率的单位将写为`1/s`，其中`s`表示秒。</span><span class="sxs-lookup"><span data-stu-id="c0a54-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="c0a54-119">在单元公式中不使用括号。</span><span class="sxs-lookup"><span data-stu-id="c0a54-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="c0a54-120">不到单元的公式; 中指定数值转换常量但是，可以单独定义单位使用的转换常量和单元检查计算中使用它们。</span><span class="sxs-lookup"><span data-stu-id="c0a54-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="c0a54-121">表示同一事物的单元公式可以用不同的等效方法。</span><span class="sxs-lookup"><span data-stu-id="c0a54-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="c0a54-122">因此，编译器将转换形式一致，这将负数幂倒数、 组单位转换为单一的分子和分母，并按字母顺序排列的分子和分母中的单元为单位的公式。</span><span class="sxs-lookup"><span data-stu-id="c0a54-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="c0a54-123">例如，单元公式`kg m s^-2`并`m /s s * kg`将转换为`kg m/s^2`。</span><span class="sxs-lookup"><span data-stu-id="c0a54-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="c0a54-124">浮点表达式中使用度量的单位。</span><span class="sxs-lookup"><span data-stu-id="c0a54-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="c0a54-125">使用浮点数与关联的单元的度量值将添加另一个级别的类型安全，并有助于避免使用弱类型化的浮点数时可能出现在公式中的单元不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="c0a54-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="c0a54-126">如果您编写的浮点使用单位的点表达式，必须与匹配表达式中的单元。</span><span class="sxs-lookup"><span data-stu-id="c0a54-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="c0a54-127">下面的示例中所示，你可以批注文本与中尖括号内的单元公式。</span><span class="sxs-lookup"><span data-stu-id="c0a54-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="c0a54-128">您不要将数和尖括号; 之间有空格但是，如包含的文本后缀`f`，如下面的示例。</span><span class="sxs-lookup"><span data-stu-id="c0a54-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="c0a54-129">此类批注更改文字的类型从其基元类型 (如`float`) 为划分维度的类型，如`float<cm>`或在这种情况下， `float<miles/hour>`。</span><span class="sxs-lookup"><span data-stu-id="c0a54-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="c0a54-130">单位批注`<1>`指示纲数量和其类型是等效于没有单元参数的基元类型。</span><span class="sxs-lookup"><span data-stu-id="c0a54-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="c0a54-131">是浮点数或带符号整型类型以及额外的单位批注，在括号中指示的测量单位的类型。</span><span class="sxs-lookup"><span data-stu-id="c0a54-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="c0a54-132">因此，当你编写从转换的类型时，才`g`（元语法） 到`kg`（千克） 描述的类型，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c0a54-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="c0a54-133">度量单位用于检查的编译时间单位，但不是会保留在运行时环境。</span><span class="sxs-lookup"><span data-stu-id="c0a54-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="c0a54-134">因此，它们不会影响性能。</span><span class="sxs-lookup"><span data-stu-id="c0a54-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="c0a54-135">度量单位可以应用于任何类型，而不仅仅浮点类型;但是，唯一的浮点类型，已签名的整型类型和十进制类型确定了维度的支持数量。</span><span class="sxs-lookup"><span data-stu-id="c0a54-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="c0a54-136">因此，它仅有意义使用基元类型和包含这些基元类型的聚合的度量单位。</span><span class="sxs-lookup"><span data-stu-id="c0a54-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="c0a54-137">下面的示例演示如何使用度量单位。</span><span class="sxs-lookup"><span data-stu-id="c0a54-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="c0a54-138">下面的代码示例说明了如何将从纲浮点数转换为划分维度的浮点值。</span><span class="sxs-lookup"><span data-stu-id="c0a54-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="c0a54-139">您只需与 1.0 相乘，将维度应用于 1.0。</span><span class="sxs-lookup"><span data-stu-id="c0a54-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="c0a54-140">可以将此抽象到所示的函数`degreesFahrenheit`。</span><span class="sxs-lookup"><span data-stu-id="c0a54-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="c0a54-141">此外，当将划分维度的值传递到期望纲浮点数的函数中，则必须取消扩展单位或强制转换为`float`通过使用`float`运算符。</span><span class="sxs-lookup"><span data-stu-id="c0a54-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="c0a54-142">在此示例中，您除以`1.0<degC>`的参数`printf`因为`printf`需要纲数量。</span><span class="sxs-lookup"><span data-stu-id="c0a54-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="c0a54-143">下面的示例会话显示的输出和此代码的输入。</span><span class="sxs-lookup"><span data-stu-id="c0a54-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="c0a54-144">使用泛型单位</span><span class="sxs-lookup"><span data-stu-id="c0a54-144">Using Generic Units</span></span>

<span data-ttu-id="c0a54-145">对具有关联的单元的度量值的数据，可以编写运行的泛型函数。</span><span class="sxs-lookup"><span data-stu-id="c0a54-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="c0a54-146">您为此，指定一个类型与泛型单元一起作为一个类型参数，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c0a54-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="c0a54-147">使用泛型单位创建聚合类型</span><span class="sxs-lookup"><span data-stu-id="c0a54-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="c0a54-148">下面的代码演示如何创建单个浮动点具有的值都是泛型方法的单元组成的聚合类型。</span><span class="sxs-lookup"><span data-stu-id="c0a54-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="c0a54-149">这使单个类型来创建适用于各种单位。</span><span class="sxs-lookup"><span data-stu-id="c0a54-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="c0a54-150">此外，泛型单位可以通过确保泛型类型具有一组单元相同的泛型类型具有一组不同的单元与不同的类型保留类型安全。</span><span class="sxs-lookup"><span data-stu-id="c0a54-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="c0a54-151">此技术的基础是`Measure`特性可以应用于类型参数。</span><span class="sxs-lookup"><span data-stu-id="c0a54-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="c0a54-152">在运行时的单位</span><span class="sxs-lookup"><span data-stu-id="c0a54-152">Units at Runtime</span></span>

<span data-ttu-id="c0a54-153">度量单位用于静态类型检查。</span><span class="sxs-lookup"><span data-stu-id="c0a54-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="c0a54-154">浮点值编译时，将消除的度量单位，以便在运行时的单位是丢失。</span><span class="sxs-lookup"><span data-stu-id="c0a54-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="c0a54-155">因此，任何尝试实现取决于在运行时检查单元的功能是不可能。</span><span class="sxs-lookup"><span data-stu-id="c0a54-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="c0a54-156">例如，实现`ToString`函数来打印出单位不能。</span><span class="sxs-lookup"><span data-stu-id="c0a54-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="c0a54-157">转换</span><span class="sxs-lookup"><span data-stu-id="c0a54-157">Conversions</span></span>

<span data-ttu-id="c0a54-158">要转换具有单位的类型 (例如， `float<'u>`) 到一个没有单元的类型，可以使用标准的转换函数。</span><span class="sxs-lookup"><span data-stu-id="c0a54-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="c0a54-159">例如，可以使用`float`将转换为`float`不具有单元，如下面的代码中所示的值。</span><span class="sxs-lookup"><span data-stu-id="c0a54-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="c0a54-160">若要将无单位的值转换为具有单元的值，可以用适当的单位乘以 1 或 1.0 进行批注的值。</span><span class="sxs-lookup"><span data-stu-id="c0a54-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="c0a54-161">但是，为编写的互操作性层，也有一些可用于与单元将无单位值转换为值的显式函数。</span><span class="sxs-lookup"><span data-stu-id="c0a54-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="c0a54-162">这些对象位于[Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3)模块。</span><span class="sxs-lookup"><span data-stu-id="c0a54-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="c0a54-163">例如，若要从无单位转换`float`到`float<cm>`，使用[FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="c0a54-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="c0a54-164">F # 核心库中的度量单位</span><span class="sxs-lookup"><span data-stu-id="c0a54-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="c0a54-165">单元库现已推出`FSharp.Data.UnitSystems.SI`命名空间。</span><span class="sxs-lookup"><span data-stu-id="c0a54-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="c0a54-166">它包括这两个符号形式的 SI 单位 (如`m`测定仪) 中`UnitSymbols`子命名空间和其完整名称 (如`meter`测定仪) 中`UnitNames`子命名空间。</span><span class="sxs-lookup"><span data-stu-id="c0a54-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0a54-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a54-167">See also</span></span>

- [<span data-ttu-id="c0a54-168">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="c0a54-168">F# Language Reference</span></span>](index.md)
