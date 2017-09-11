---
title: "放弃 - C# 指南 | Microsoft Docs"
description: "介绍 C# 对放弃的支持（放弃是未赋值的可丢弃变量），以及放弃的使用方式。"
keywords: .NET,.NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 07/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.translationtype: HT
ms.sourcegitcommit: 6170e096e36f8d054fdfe9cbd8311e6492e32a04
ms.openlocfilehash: 3f8804f9b7522e385b145a9643dec942cc1aab9f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/28/2017

---
# <a name="discards---c-guide"></a><span data-ttu-id="39f50-104">放弃 - C# 指南</span><span class="sxs-lookup"><span data-stu-id="39f50-104">Discards - C# Guide</span></span>

<span data-ttu-id="39f50-105">从 C# 7 开始，C# 支持放弃，这是一种在应用程序代码中人为取消使用的临时虚拟变量。</span><span class="sxs-lookup"><span data-stu-id="39f50-105">Starting with C# 7, C# supports discards, which are temporary, dummy variables that are intentionally unused in application code.</span></span> <span data-ttu-id="39f50-106">放弃相当于未赋值的变量；它们没有值。</span><span class="sxs-lookup"><span data-stu-id="39f50-106">Discards are equivalent to unassigned variables; they do not have a value.</span></span> <span data-ttu-id="39f50-107">因为只有一个放弃变量，并且甚至不为该变量分配存储空间，所以放弃可减少内存分配。</span><span class="sxs-lookup"><span data-stu-id="39f50-107">Because there is only a single discard variable, and that variable may not even be allocated storage, discards can reduce memory allocations.</span></span> <span data-ttu-id="39f50-108">因为它们使代码的意图清楚，增强了其可读性和可维护性。</span><span class="sxs-lookup"><span data-stu-id="39f50-108">Because they make the intent of your code clear, they enhance its readability and maintainability.</span></span>

<span data-ttu-id="39f50-109">通过将下划线 (`_`) 赋给一个变量作为其变量名，指示该变量为一个放弃。</span><span class="sxs-lookup"><span data-stu-id="39f50-109">You indicate that a variable is a discard by assigning it the underscore (`_`) as its name.</span></span> <span data-ttu-id="39f50-110">例如，以下方法调用返回一个 3 元组，其中第一个和第二个值为放弃：</span><span class="sxs-lookup"><span data-stu-id="39f50-110">For example, the following method call returns a 3-tuple in which the first and second values are discards:</span></span>

```csharp
(var _, _, area) = city.GetCityInformation(cityName);
```

<span data-ttu-id="39f50-111">在 C# 7 中，支持在以下上下文中的分配中使用放弃：</span><span class="sxs-lookup"><span data-stu-id="39f50-111">In C# 7, discards are supported in assignments in the following contexts:</span></span>

- <span data-ttu-id="39f50-112">元组和对象[析构](deconstruct.md)。</span><span class="sxs-lookup"><span data-stu-id="39f50-112">Tuple and object [deconstruction](deconstruct.md).</span></span>
- <span data-ttu-id="39f50-113">使用 [is](language-reference/keywords/is.md) 和 [switch](language-reference/keywords/switch.md) 的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="39f50-113">Pattern matching with [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md).</span></span>
- <span data-ttu-id="39f50-114">对具有 `out` 参数的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="39f50-114">Calls to methods with `out` parameters.</span></span>
- <span data-ttu-id="39f50-115">当范围内没有 `_` 时，独立的 `_`。</span><span class="sxs-lookup"><span data-stu-id="39f50-115">A standalone `_` when no `_` is in scope.</span></span>

<span data-ttu-id="39f50-116">当 `_` 是有效放弃时，尝试检索其值或在赋值操作中使用它时会生成编译器错误 CS0301：当前上下文中不存在名称 "\_"。</span><span class="sxs-lookup"><span data-stu-id="39f50-116">When `_` is a valid discard, attempting to retrieve its value or use it in an assignment operation generates compiler error CS0301, "The name '\_' does not exist in the current context".</span></span> <span data-ttu-id="39f50-117">这是因为 `_` 未赋值，甚至可能未分配存储位置。</span><span class="sxs-lookup"><span data-stu-id="39f50-117">This is because `_` is not assigned a value, and may not even be assigned a storage location.</span></span> <span data-ttu-id="39f50-118">如果它是一个实际变量，则不能像之前的示例那样放弃多个值。</span><span class="sxs-lookup"><span data-stu-id="39f50-118">If it were an actual variable, you could not discard more than one value, as the previous example did.</span></span>

## <a name="tuple-and-object-deconstruction"></a><span data-ttu-id="39f50-119">元组和对象析构</span><span class="sxs-lookup"><span data-stu-id="39f50-119">Tuple and object deconstruction</span></span>

<span data-ttu-id="39f50-120">如果应用程序代码使用某些元组元素但忽略其他元素，这时使用放弃来处理元组就会特别有用。</span><span class="sxs-lookup"><span data-stu-id="39f50-120">Discards are particularly useful in working with tuples when your application code uses some tuple elements but ignores others.</span></span> <span data-ttu-id="39f50-121">例如，以下的 `QueryCityDataForYears` 方法返回一个 6 元组，包含城市名称、城市面积、一个年份、该年份的城市人口、另一个年份及该年份的城市人口。</span><span class="sxs-lookup"><span data-stu-id="39f50-121">For example, the following `QueryCityDataForYears` method returns a 6-tuple with the name of a city, its area, a year, the city's population for that year, a second year, and the city's population for that second year.</span></span> <span data-ttu-id="39f50-122">该示例显示了两个年份之间人口的变化。</span><span class="sxs-lookup"><span data-stu-id="39f50-122">The example shows the change in population between those two years.</span></span> <span data-ttu-id="39f50-123">对于元组提供的数据，我们不关注城市面积，并在一开始就知道城市名称和两个日期。</span><span class="sxs-lookup"><span data-stu-id="39f50-123">Of the data available from the tuple, we're unconcerned with the city area, and we know the city name and the two dates at design-time.</span></span> <span data-ttu-id="39f50-124">因此，我们只关注存储在元组中的两个人口数量值，可将其余值作为放弃处理。</span><span class="sxs-lookup"><span data-stu-id="39f50-124">As a result, we're only interested in the two population values stored in the tuple, and can handle its remaining values as discards.</span></span>  

<span data-ttu-id="39f50-125">[!code-csharp[元组-放弃](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39f50-125">[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span></span>

<span data-ttu-id="39f50-126">有关使用放弃析构元组的详细信息，请参阅[析构元组和其他类型](deconstruct.md#deconstructing-tuple-elements-with-discards)。</span><span class="sxs-lookup"><span data-stu-id="39f50-126">For more information on deconstructing tuples with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-tuple-elements-with-discards).</span></span>

<span data-ttu-id="39f50-127">类、结构或接口的 `Deconstruct` 方法还允许从对象中检索和析构一组特定的数据。</span><span class="sxs-lookup"><span data-stu-id="39f50-127">The `Deconstruct` method of a class, structure, or interface also allows you to retrieve and deconstruct a specific set of data from an object.</span></span> <span data-ttu-id="39f50-128">如果想只使用析构值的一个子集时，可使用放弃。</span><span class="sxs-lookup"><span data-stu-id="39f50-128">You can use discards when you are interested in working with only a subset of the deconstructed values.</span></span> <span data-ttu-id="39f50-129">以下示例将 `Person` 对象析构为四个字符串（名字、姓氏、城市和省/市/自治区），但舍弃姓氏和省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="39f50-129">Ihe following example deconstructs a `Person` object into four strings (the first and last names, the city, and the state), but discards the last name and the state.</span></span>

<span data-ttu-id="39f50-130">[!code-csharp[类-放弃](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39f50-130">[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]</span></span>

<span data-ttu-id="39f50-131">有关使用放弃析构用户定义的类型的详细信息，请参阅[析构元组和其他类型](deconstruct.md#deconstructing-a-user-defined-type-with-discards)。</span><span class="sxs-lookup"><span data-stu-id="39f50-131">For more information on deconstructing user-defined types with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-a-user-defined-type-with-discards).</span></span>

## <a name="pattern-matching-with-switch-and-is"></a><span data-ttu-id="39f50-132">使用 `switch` 和 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="39f50-132">Pattern matching with `switch` and `is`</span></span>

<span data-ttu-id="39f50-133">放弃模式可通过 [is](language-reference/keywords/is.md) 和 [switch](language-reference/keywords/switch.md) 关键字用于模式匹配。</span><span class="sxs-lookup"><span data-stu-id="39f50-133">The *discard pattern* can be used in pattern matching with the [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md) keywords.</span></span> <span data-ttu-id="39f50-134">每个表达式始终匹配放弃模式。</span><span class="sxs-lookup"><span data-stu-id="39f50-134">Every expression always matches the discard pattern.</span></span>

<span data-ttu-id="39f50-135">以下示例定义了一个 `ProvidesFormatInfo` 方法，该方法使用 [is](language-reference/keywords/is.md) 语句来确定对象是否提供 <xref:System.IFormatProvider> 实现并测试对象是否为 `null`。</span><span class="sxs-lookup"><span data-stu-id="39f50-135">The following example defines a `ProvidesFormatInfo` method that uses [is](language-reference/keywords/is.md) statements to determine whether an object provides an <xref:System.IFormatProvider> implementation and tests whether the object is `null`.</span></span> <span data-ttu-id="39f50-136">它还使用放弃模式来处理任何其他类型的非 null 对象。</span><span class="sxs-lookup"><span data-stu-id="39f50-136">It also uses the discard pattern to handle non-null objects of any other type.</span></span>

<span data-ttu-id="39f50-137">[!code-csharp[放弃-模式](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]</span><span class="sxs-lookup"><span data-stu-id="39f50-137">[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]</span></span>

## <a name="calls-to-methods-with-out-parameters"></a><span data-ttu-id="39f50-138">使用 out 参数调用方法</span><span class="sxs-lookup"><span data-stu-id="39f50-138">Calls to methods with out parameters</span></span>

<span data-ttu-id="39f50-139">当调用 `Deconstruct` 方法来析构用户定义类型（类、结构或接口的实例）时，可放弃单个 `out` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="39f50-139">When calling the `Deconstruct` method to deconstruct a user-defined type (an instance of a class, structure, or interface), you can discard the values of individual `out` arguments.</span></span> <span data-ttu-id="39f50-140">但当使用 out 参数调用任何方法时，也可放弃 `out` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="39f50-140">But you can also discard the value of `out` arguments when calling any method with an out parameter.</span></span> 

<span data-ttu-id="39f50-141">以下示例调用 [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) 方法来确定日期的字符串表示形式在当前区域性中是否有效。</span><span class="sxs-lookup"><span data-stu-id="39f50-141">The following example calls the [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) method to determine whether the string representation of a date is valid in the current culture.</span></span> <span data-ttu-id="39f50-142">因为该示例侧重验证日期字符串，而不是解析它来提取日期，所以方法的 `out` 参数为放弃。</span><span class="sxs-lookup"><span data-stu-id="39f50-142">Because the example is concerned only with validating the date string and not with parsing it to extract the date, the `out` argument to the method is a discard.</span></span>

<span data-ttu-id="39f50-143">[!code-csharp[放弃-使用 out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39f50-143">[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]</span></span>

## <a name="a-standalone-discard"></a><span data-ttu-id="39f50-144">独立放弃</span><span class="sxs-lookup"><span data-stu-id="39f50-144">A standalone discard</span></span>

<span data-ttu-id="39f50-145">可使用独立放弃来指示要忽略的任何变量。</span><span class="sxs-lookup"><span data-stu-id="39f50-145">You can use a standalone discard to indicate any variable that you choose to ignore.</span></span> <span data-ttu-id="39f50-146">以下示例使用独立放弃来忽略异步操作返回的 <xref:System.Threading.Tasks.Task> 对象。</span><span class="sxs-lookup"><span data-stu-id="39f50-146">The following example uses a standalone discard to ignore the <xref:System.Threading.Tasks.Task> object returned by an asynchronous operation.</span></span> <span data-ttu-id="39f50-147">这一操作的效果等同于抑制操作即将完成时所引发的异常。</span><span class="sxs-lookup"><span data-stu-id="39f50-147">This has the effect of suppressing the exception that the operation throws as it is about to complete.</span></span>

<span data-ttu-id="39f50-148">[!code-csharp[独立-放弃](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39f50-148">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]</span></span>

<span data-ttu-id="39f50-149">请注意，`_` 也是有效标识符。</span><span class="sxs-lookup"><span data-stu-id="39f50-149">Note that `_` is also a valid identifier.</span></span> <span data-ttu-id="39f50-150">当在支持的上下文之外使用时，`_` 不视为放弃，而视为有效变量。</span><span class="sxs-lookup"><span data-stu-id="39f50-150">When used outside of a supported context, `_` is treated not as a discard but as a valid variable.</span></span> <span data-ttu-id="39f50-151">如果名为 `_` 的标识符已在范围内，则使用 `_` 作为独立放弃可能导致：</span><span class="sxs-lookup"><span data-stu-id="39f50-151">If an identifier named `_` is already in scope, the use of `_` as a standalone discard can result in:</span></span>

- <span data-ttu-id="39f50-152">将预期的放弃的值赋给范围内 `_` 变量，会导致该变量的值被意外修改。</span><span class="sxs-lookup"><span data-stu-id="39f50-152">Accidental modification of the value of the in-scope `_` variable by assigning it the value of the intended discard.</span></span> <span data-ttu-id="39f50-153">例如: </span><span class="sxs-lookup"><span data-stu-id="39f50-153">For example:</span></span>

   <span data-ttu-id="39f50-154">[!code-csharp[独立-放弃](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="39f50-154">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]</span></span>
 
- <span data-ttu-id="39f50-155">因违反类型安全而发生的编译器错误。</span><span class="sxs-lookup"><span data-stu-id="39f50-155">A compiler error for violating type safety.</span></span> <span data-ttu-id="39f50-156">例如: </span><span class="sxs-lookup"><span data-stu-id="39f50-156">For example:</span></span>

   <span data-ttu-id="39f50-157">[!code-csharp[独立-放弃](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="39f50-157">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]</span></span>
 
- <span data-ttu-id="39f50-158">编译器错误 CS0136：“无法在此范围中声明名为“_”的局部变量或参数，因为该名称用于在封闭的局部范围中定义局部变量或参数”。</span><span class="sxs-lookup"><span data-stu-id="39f50-158">Compiler error CS0136, "A local or parameter named '_' cannot be declared in this scope because that name is used in an enclosing local scope to define a local or parameter."</span></span> <span data-ttu-id="39f50-159">例如: </span><span class="sxs-lookup"><span data-stu-id="39f50-159">For example:</span></span>

   <span data-ttu-id="39f50-160">[!code-csharp[独立-放弃](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="39f50-160">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]</span></span>

## <a name="see-also"></a><span data-ttu-id="39f50-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="39f50-161">See also</span></span>
<span data-ttu-id="39f50-162">[解构元组和其他类型](deconstruct.md) </span><span class="sxs-lookup"><span data-stu-id="39f50-162">[Deconstructing tuples and other types](deconstruct.md) </span></span>  
<span data-ttu-id="39f50-163">[`is` 关键字](language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="39f50-163">[`is` keyword](language-reference/keywords/is.md) </span></span>  
[<span data-ttu-id="39f50-164">`switch` 关键字</span><span class="sxs-lookup"><span data-stu-id="39f50-164">`switch` keyword</span></span>](language-reference/keywords/switch.md)   

