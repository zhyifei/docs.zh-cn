---
title: 使用索引器 - C# 编程指南
ms.custom: seodec18
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: ad5c6f68f5eb2f62d7c6f389e374e1b2db5417c6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241913"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="c5780-102">使用索引器（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c5780-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="c5780-103">索引器使你可从语法上方便地创建[类](../../../csharp/language-reference/keywords/class.md)、[结构](../../../csharp/language-reference/keywords/struct.md)或[接口](../../../csharp/language-reference/keywords/interface.md)，以便客户端应用程序能像访问数组一样访问它们。</span><span class="sxs-lookup"><span data-stu-id="c5780-103">Indexers are a syntactic convenience that enable you to create a [class](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md), or [interface](../../../csharp/language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="c5780-104">在主要目标是封装内部集合或数组的类型中，常常要实现索引器。</span><span class="sxs-lookup"><span data-stu-id="c5780-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="c5780-105">例如，假设有一个类 `TempRecord`，它表示 24 小时的周期内在 10 个不同时间点所记录的温度（单位为华氏度）。</span><span class="sxs-lookup"><span data-stu-id="c5780-105">For example, suppose you have a class `TempRecord` that represents the temperature in Farenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="c5780-106">此类包含类型 `float[]` 的一个数组 `temps`，用于存储温度值。</span><span class="sxs-lookup"><span data-stu-id="c5780-106">The class contains an array `temps` of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="c5780-107">通过在此类中实现索引器，客户端可采用 `float temp = tr[4]` 的形式（而非 `float temp = tr.temps[4]`）访问 `TempRecord` 实例中的温度。</span><span class="sxs-lookup"><span data-stu-id="c5780-107">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="c5780-108">索引器表示法不但简化了客户端应用程序的语法；它还使类及其目标更容易直观地为其它开发者所理解。</span><span class="sxs-lookup"><span data-stu-id="c5780-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
<span data-ttu-id="c5780-109">若要在类或结构上声明索引器，请使用 [this](../../../csharp/language-reference/keywords/this.md) 关键字，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c5780-109">To declare an indexer on a class or struct, use the [this](../../../csharp/language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a><span data-ttu-id="c5780-110">备注</span><span class="sxs-lookup"><span data-stu-id="c5780-110">Remarks</span></span>

<span data-ttu-id="c5780-111">索引器及其参数的类型必须至少具有和索引器相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="c5780-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="c5780-112">有关可访问性级别的详细信息，请参阅[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="c5780-112">For more information about accessibility levels, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="c5780-113">有关如何在接口上使用索引器的详细信息，请参阅[接口索引器](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="c5780-113">For more information about how to use indexers with an interface, see [Interface Indexers](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="c5780-114">索引器的签名由其形参的数目和类型所组成。</span><span class="sxs-lookup"><span data-stu-id="c5780-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="c5780-115">它不包含索引器类型或形参的名称。</span><span class="sxs-lookup"><span data-stu-id="c5780-115">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="c5780-116">如果要在相同类中声明多个索引器，则它们的签名必须不同。</span><span class="sxs-lookup"><span data-stu-id="c5780-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="c5780-117">索引器值不分类为变量；因此，无法将索引器值作为 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数来传递。</span><span class="sxs-lookup"><span data-stu-id="c5780-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>  
  
 <span data-ttu-id="c5780-118">若要使索引器的名称可为其他语言所用，请使用 <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c5780-118">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

<span data-ttu-id="c5780-119">此索引器将具有名称 `TheItem`。</span><span class="sxs-lookup"><span data-stu-id="c5780-119">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="c5780-120">如果不提供名称属性，则 `Item` 将成为默认名称。</span><span class="sxs-lookup"><span data-stu-id="c5780-120">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="c5780-121">示例 1</span><span class="sxs-lookup"><span data-stu-id="c5780-121">Example 1</span></span>  
  
<span data-ttu-id="c5780-122">下列示例演示如何声明专用数组字段 `temps` 和索引器。</span><span class="sxs-lookup"><span data-stu-id="c5780-122">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="c5780-123">索引器可以实现对实例 `tempRecord[i]` 的直接访问。</span><span class="sxs-lookup"><span data-stu-id="c5780-123">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="c5780-124">若不使用索引器，则将数组声明为[公共](../../../csharp/language-reference/keywords/public.md)成员，并直接访问其成员 `tempRecord.temps[i]`。</span><span class="sxs-lookup"><span data-stu-id="c5780-124">The alternative to using the indexer is to declare the array as a [public](../../../csharp/language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="c5780-125">请注意，当评估索引器访问时（例如在 `Console.Write` 语句中），将调用 [get](../../../csharp/language-reference/keywords/get.md) 访问器。</span><span class="sxs-lookup"><span data-stu-id="c5780-125">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../../csharp/language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="c5780-126">因此，如果不存在 `get` 访问器，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="c5780-126">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
[!code-csharp[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="c5780-127">使用其他值进行索引</span><span class="sxs-lookup"><span data-stu-id="c5780-127">Indexing using other values</span></span>

<span data-ttu-id="c5780-128">C# 不将索引类型限制为整数。</span><span class="sxs-lookup"><span data-stu-id="c5780-128">C# doesn't limit the index type to integer.</span></span> <span data-ttu-id="c5780-129">例如，对索引器使用字符串可能有用。</span><span class="sxs-lookup"><span data-stu-id="c5780-129">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="c5780-130">通过搜索集合内的字符串并返回相应的值，可以实现此类索引器。</span><span class="sxs-lookup"><span data-stu-id="c5780-130">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="c5780-131">由于访问器可被重载，字符串和整数版本可以共存。</span><span class="sxs-lookup"><span data-stu-id="c5780-131">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="c5780-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="c5780-132">Example 2</span></span>  
  
<span data-ttu-id="c5780-133">下面的示例声明了存储星期几的类。</span><span class="sxs-lookup"><span data-stu-id="c5780-133">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="c5780-134">`get` 访问器采用字符串（星期几）并返回对应的整数。</span><span class="sxs-lookup"><span data-stu-id="c5780-134">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="c5780-135">例如，“Sunday”返回 0，“Monday”返回 1，依此类推。</span><span class="sxs-lookup"><span data-stu-id="c5780-135">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>  
  
[!code-csharp[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c5780-136">可靠编程</span><span class="sxs-lookup"><span data-stu-id="c5780-136">Robust programming</span></span>

 <span data-ttu-id="c5780-137">提高索引器的安全性和可靠性有两种主要方法：</span><span class="sxs-lookup"><span data-stu-id="c5780-137">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
- <span data-ttu-id="c5780-138">请确保结合某一类型的错误处理策略，以处理万一客户端代码传入无效索引值的情况。</span><span class="sxs-lookup"><span data-stu-id="c5780-138">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="c5780-139">在本主题前面的第一个示例中，TempRecord 类提供了 Length 属性，使客户端代码能在将输入传递给索引器之前对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="c5780-139">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="c5780-140">也可将错误处理代码放入索引器自身内部。</span><span class="sxs-lookup"><span data-stu-id="c5780-140">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="c5780-141">请确保为用户记录在索引器的访问器中引发的任何异常。</span><span class="sxs-lookup"><span data-stu-id="c5780-141">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
- <span data-ttu-id="c5780-142">在可接受的程度内，为 [get](../../../csharp/language-reference/keywords/get.md) 和 [set](../../../csharp/language-reference/keywords/set.md) 访问器的可访问性设置尽可能多的限制。</span><span class="sxs-lookup"><span data-stu-id="c5780-142">Set the accessibility of the [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="c5780-143">这一点对 `set` 访问器尤为重要。</span><span class="sxs-lookup"><span data-stu-id="c5780-143">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="c5780-144">有关详细信息，请参阅[限制访问器可访问性](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)。</span><span class="sxs-lookup"><span data-stu-id="c5780-144">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5780-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5780-145">See also</span></span>

- [<span data-ttu-id="c5780-146">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c5780-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c5780-147">索引器</span><span class="sxs-lookup"><span data-stu-id="c5780-147">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="c5780-148">属性</span><span class="sxs-lookup"><span data-stu-id="c5780-148">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
