---
title: "抛弃 - C# 指南"
description: "介绍 C# 对抛弃的支持（抛弃是未赋值的可丢弃变量），以及抛弃的使用方式。"
keywords: .NET,.NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 07/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 800a27d2d186c738dceb6838aa669377a0c07b01
ms.sourcegitcommit: 882e02b086d7cb9c75f748494cf7a8d3377c5874
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="discards---c-guide"></a><span data-ttu-id="199dc-104">抛弃 - C# 指南</span><span class="sxs-lookup"><span data-stu-id="199dc-104">Discards - C# Guide</span></span>

<span data-ttu-id="199dc-105">从 C# 7 开始，C# 支持抛弃，这是一种在应用程序代码中人为取消使用的临时虚拟变量。</span><span class="sxs-lookup"><span data-stu-id="199dc-105">Starting with C# 7, C# supports discards, which are temporary, dummy variables that are intentionally unused in application code.</span></span> <span data-ttu-id="199dc-106">抛弃相当于未赋值的变量；它们没有值。</span><span class="sxs-lookup"><span data-stu-id="199dc-106">Discards are equivalent to unassigned variables; they do not have a value.</span></span> <span data-ttu-id="199dc-107">因为只有一个抛弃变量，并且甚至不为该变量分配存储空间，所以抛弃可减少内存分配。</span><span class="sxs-lookup"><span data-stu-id="199dc-107">Because there is only a single discard variable, and that variable may not even be allocated storage, discards can reduce memory allocations.</span></span> <span data-ttu-id="199dc-108">因为它们使代码的意图清楚，增强了其可读性和可维护性。</span><span class="sxs-lookup"><span data-stu-id="199dc-108">Because they make the intent of your code clear, they enhance its readability and maintainability.</span></span>

<span data-ttu-id="199dc-109">通过将下划线 (`_`) 赋给一个变量作为其变量名，指示该变量为一个抛弃。</span><span class="sxs-lookup"><span data-stu-id="199dc-109">You indicate that a variable is a discard by assigning it the underscore (`_`) as its name.</span></span> <span data-ttu-id="199dc-110">例如，下面的方法调用返回在其中的第一个和第二个值是抛弃-3 元组和*区域*是一个以前声明的变量将设置为相应的第三个组件返回*GetCityInformation*:</span><span class="sxs-lookup"><span data-stu-id="199dc-110">For example, the following method call returns a 3-tuple in which the first and second values are discards and *area* is a previously declared variable to be set to the corresponding third component returned by *GetCityInformation*:</span></span>

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

<span data-ttu-id="199dc-111">在 C# 7 中，支持在以下上下文中的分配中使用抛弃：</span><span class="sxs-lookup"><span data-stu-id="199dc-111">In C# 7, discards are supported in assignments in the following contexts:</span></span>

- <span data-ttu-id="199dc-112">元组和对象[析构](deconstruct.md)。</span><span class="sxs-lookup"><span data-stu-id="199dc-112">Tuple and object [deconstruction](deconstruct.md).</span></span>
- <span data-ttu-id="199dc-113">使用 [is](language-reference/keywords/is.md) 和 [switch](language-reference/keywords/switch.md) 的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="199dc-113">Pattern matching with [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md).</span></span>
- <span data-ttu-id="199dc-114">对具有 `out` 参数的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="199dc-114">Calls to methods with `out` parameters.</span></span>
- <span data-ttu-id="199dc-115">当范围内没有 `_` 时，独立的 `_`。</span><span class="sxs-lookup"><span data-stu-id="199dc-115">A standalone `_` when no `_` is in scope.</span></span>

<span data-ttu-id="199dc-116">当 `_` 是有效抛弃时，尝试检索其值或在赋值操作中使用它时会生成编译器错误 CS0301：当前上下文中不存在名称 "\_"。</span><span class="sxs-lookup"><span data-stu-id="199dc-116">When `_` is a valid discard, attempting to retrieve its value or use it in an assignment operation generates compiler error CS0301, "The name '\_' does not exist in the current context".</span></span> <span data-ttu-id="199dc-117">这是因为 `_` 未赋值，甚至可能未分配存储位置。</span><span class="sxs-lookup"><span data-stu-id="199dc-117">This is because `_` is not assigned a value, and may not even be assigned a storage location.</span></span> <span data-ttu-id="199dc-118">如果它是一个实际变量，则不能像之前的示例那样抛弃多个值。</span><span class="sxs-lookup"><span data-stu-id="199dc-118">If it were an actual variable, you could not discard more than one value, as the previous example did.</span></span>

## <a name="tuple-and-object-deconstruction"></a><span data-ttu-id="199dc-119">元组和对象析构</span><span class="sxs-lookup"><span data-stu-id="199dc-119">Tuple and object deconstruction</span></span>

<span data-ttu-id="199dc-120">如果应用程序代码使用某些元组元素但忽略其他元素，这时使用抛弃来处理元组就会特别有用。</span><span class="sxs-lookup"><span data-stu-id="199dc-120">Discards are particularly useful in working with tuples when your application code uses some tuple elements but ignores others.</span></span> <span data-ttu-id="199dc-121">例如，以下的 `QueryCityDataForYears` 方法返回一个 6 元组，包含城市名称、城市面积、一个年份、该年份的城市人口、另一个年份及该年份的城市人口。</span><span class="sxs-lookup"><span data-stu-id="199dc-121">For example, the following `QueryCityDataForYears` method returns a 6-tuple with the name of a city, its area, a year, the city's population for that year, a second year, and the city's population for that second year.</span></span> <span data-ttu-id="199dc-122">该示例显示了两个年份之间人口的变化。</span><span class="sxs-lookup"><span data-stu-id="199dc-122">The example shows the change in population between those two years.</span></span> <span data-ttu-id="199dc-123">对于元组提供的数据，我们不关注城市面积，并在一开始就知道城市名称和两个日期。</span><span class="sxs-lookup"><span data-stu-id="199dc-123">Of the data available from the tuple, we're unconcerned with the city area, and we know the city name and the two dates at design-time.</span></span> <span data-ttu-id="199dc-124">因此，我们只关注存储在元组中的两个人口数量值，可将其余值作为抛弃处理。</span><span class="sxs-lookup"><span data-stu-id="199dc-124">As a result, we're only interested in the two population values stored in the tuple, and can handle its remaining values as discards.</span></span>  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="199dc-125">有关使用抛弃析构元组的详细信息，请参阅[析构元组和其他类型](deconstruct.md#deconstructing-tuple-elements-with-discards)。</span><span class="sxs-lookup"><span data-stu-id="199dc-125">For more information on deconstructing tuples with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-tuple-elements-with-discards).</span></span>

<span data-ttu-id="199dc-126">类、结构或接口的 `Deconstruct` 方法还允许从对象中检索和析构一组特定的数据。</span><span class="sxs-lookup"><span data-stu-id="199dc-126">The `Deconstruct` method of a class, structure, or interface also allows you to retrieve and deconstruct a specific set of data from an object.</span></span> <span data-ttu-id="199dc-127">如果想只使用析构值的一个子集时，可使用抛弃。</span><span class="sxs-lookup"><span data-stu-id="199dc-127">You can use discards when you are interested in working with only a subset of the deconstructed values.</span></span> <span data-ttu-id="199dc-128">以下示例将 `Person` 对象析构为四个字符串（名字、姓氏、城市和省/市/自治区），但舍弃姓氏和省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="199dc-128">Ihe following example deconstructs a `Person` object into four strings (the first and last names, the city, and the state), but discards the last name and the state.</span></span>

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]

<span data-ttu-id="199dc-129">有关使用抛弃析构用户定义的类型的详细信息，请参阅[析构元组和其他类型](deconstruct.md#deconstructing-a-user-defined-type-with-discards)。</span><span class="sxs-lookup"><span data-stu-id="199dc-129">For more information on deconstructing user-defined types with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-a-user-defined-type-with-discards).</span></span>

## <a name="pattern-matching-with-switch-and-is"></a><span data-ttu-id="199dc-130">使用 `switch` 和 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="199dc-130">Pattern matching with `switch` and `is`</span></span>

<span data-ttu-id="199dc-131">抛弃模式可通过 [is](language-reference/keywords/is.md) 和 [switch](language-reference/keywords/switch.md) 关键字用于模式匹配。</span><span class="sxs-lookup"><span data-stu-id="199dc-131">The *discard pattern* can be used in pattern matching with the [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md) keywords.</span></span> <span data-ttu-id="199dc-132">每个表达式始终匹配抛弃模式。</span><span class="sxs-lookup"><span data-stu-id="199dc-132">Every expression always matches the discard pattern.</span></span>

<span data-ttu-id="199dc-133">以下示例定义了一个 `ProvidesFormatInfo` 方法，该方法使用 [is](language-reference/keywords/is.md) 语句来确定对象是否提供 <xref:System.IFormatProvider> 实现并测试对象是否为 `null`。</span><span class="sxs-lookup"><span data-stu-id="199dc-133">The following example defines a `ProvidesFormatInfo` method that uses [is](language-reference/keywords/is.md) statements to determine whether an object provides an <xref:System.IFormatProvider> implementation and tests whether the object is `null`.</span></span> <span data-ttu-id="199dc-134">它还使用抛弃模式来处理任何其他类型的非 null 对象。</span><span class="sxs-lookup"><span data-stu-id="199dc-134">It also uses the discard pattern to handle non-null objects of any other type.</span></span>

[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]

## <a name="calls-to-methods-with-out-parameters"></a><span data-ttu-id="199dc-135">使用 out 参数调用方法</span><span class="sxs-lookup"><span data-stu-id="199dc-135">Calls to methods with out parameters</span></span>

<span data-ttu-id="199dc-136">当调用 `Deconstruct` 方法来析构用户定义类型（类、结构或接口的实例）时，可抛弃单个 `out` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="199dc-136">When calling the `Deconstruct` method to deconstruct a user-defined type (an instance of a class, structure, or interface), you can discard the values of individual `out` arguments.</span></span> <span data-ttu-id="199dc-137">但当使用 out 参数调用任何方法时，也可抛弃 `out` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="199dc-137">But you can also discard the value of `out` arguments when calling any method with an out parameter.</span></span> 

<span data-ttu-id="199dc-138">以下示例调用 [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) 方法来确定日期的字符串表示形式在当前区域性中是否有效。</span><span class="sxs-lookup"><span data-stu-id="199dc-138">The following example calls the [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) method to determine whether the string representation of a date is valid in the current culture.</span></span> <span data-ttu-id="199dc-139">因为该示例侧重验证日期字符串，而不是解析它来提取日期，所以方法的 `out` 参数为抛弃。</span><span class="sxs-lookup"><span data-stu-id="199dc-139">Because the example is concerned only with validating the date string and not with parsing it to extract the date, the `out` argument to the method is a discard.</span></span>

[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]

## <a name="a-standalone-discard"></a><span data-ttu-id="199dc-140">独立抛弃</span><span class="sxs-lookup"><span data-stu-id="199dc-140">A standalone discard</span></span>

<span data-ttu-id="199dc-141">可使用独立抛弃来指示要忽略的任何变量。</span><span class="sxs-lookup"><span data-stu-id="199dc-141">You can use a standalone discard to indicate any variable that you choose to ignore.</span></span> <span data-ttu-id="199dc-142">以下示例使用独立抛弃来忽略异步操作返回的 <xref:System.Threading.Tasks.Task> 对象。</span><span class="sxs-lookup"><span data-stu-id="199dc-142">The following example uses a standalone discard to ignore the <xref:System.Threading.Tasks.Task> object returned by an asynchronous operation.</span></span> <span data-ttu-id="199dc-143">这一操作的效果等同于抑制操作即将完成时所引发的异常。</span><span class="sxs-lookup"><span data-stu-id="199dc-143">This has the effect of suppressing the exception that the operation throws as it is about to complete.</span></span>

[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]

<span data-ttu-id="199dc-144">请注意，`_` 也是有效标识符。</span><span class="sxs-lookup"><span data-stu-id="199dc-144">Note that `_` is also a valid identifier.</span></span> <span data-ttu-id="199dc-145">当在支持的上下文之外使用时，`_` 不视为抛弃，而视为有效变量。</span><span class="sxs-lookup"><span data-stu-id="199dc-145">When used outside of a supported context, `_` is treated not as a discard but as a valid variable.</span></span> <span data-ttu-id="199dc-146">如果名为 `_` 的标识符已在范围内，则使用 `_` 作为独立抛弃可能导致：</span><span class="sxs-lookup"><span data-stu-id="199dc-146">If an identifier named `_` is already in scope, the use of `_` as a standalone discard can result in:</span></span>

- <span data-ttu-id="199dc-147">将预期的抛弃的值赋给范围内 `_` 变量，会导致该变量的值被意外修改。</span><span class="sxs-lookup"><span data-stu-id="199dc-147">Accidental modification of the value of the in-scope `_` variable by assigning it the value of the intended discard.</span></span> <span data-ttu-id="199dc-148">例如: </span><span class="sxs-lookup"><span data-stu-id="199dc-148">For example:</span></span>

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]
 
- <span data-ttu-id="199dc-149">因违反类型安全而发生的编译器错误。</span><span class="sxs-lookup"><span data-stu-id="199dc-149">A compiler error for violating type safety.</span></span> <span data-ttu-id="199dc-150">例如: </span><span class="sxs-lookup"><span data-stu-id="199dc-150">For example:</span></span>

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]
 
- <span data-ttu-id="199dc-151">编译器错误 CS0136：“无法在此范围中声明名为“_”的局部变量或参数，因为该名称用于在封闭的局部范围中定义局部变量或参数”。</span><span class="sxs-lookup"><span data-stu-id="199dc-151">Compiler error CS0136, "A local or parameter named '_' cannot be declared in this scope because that name is used in an enclosing local scope to define a local or parameter."</span></span> <span data-ttu-id="199dc-152">例如: </span><span class="sxs-lookup"><span data-stu-id="199dc-152">For example:</span></span>

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]

## <a name="see-also"></a><span data-ttu-id="199dc-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="199dc-153">See also</span></span>
<span data-ttu-id="199dc-154">[解构元组和其他类型](deconstruct.md) </span><span class="sxs-lookup"><span data-stu-id="199dc-154">[Deconstructing tuples and other types](deconstruct.md) </span></span>  
<span data-ttu-id="199dc-155">[`is` 关键字](language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="199dc-155">[`is` keyword](language-reference/keywords/is.md) </span></span>  
[<span data-ttu-id="199dc-156">`switch` 关键字</span><span class="sxs-lookup"><span data-stu-id="199dc-156">`switch` keyword</span></span>](language-reference/keywords/switch.md)   
