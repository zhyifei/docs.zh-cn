---
title: "属性（C# 编程指南）"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="cd44d-102">属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="cd44d-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="cd44d-103">属性是一种成员，它提供灵活的机制来读取、写入或计算私有字段的值。</span><span class="sxs-lookup"><span data-stu-id="cd44d-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="cd44d-104">属性可用作公共数据成员，但它们实际上是称为*访问器*的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="cd44d-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="cd44d-105">这使得可以轻松访问数据，还有助于提高方法的安全性和灵活性。</span><span class="sxs-lookup"><span data-stu-id="cd44d-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="cd44d-106">属性概述</span><span class="sxs-lookup"><span data-stu-id="cd44d-106">Properties overview</span></span>  
  
- <span data-ttu-id="cd44d-107">属性允许类公开获取和设置值的公共方法，而隐藏实现或验证代码。</span><span class="sxs-lookup"><span data-stu-id="cd44d-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="cd44d-108">[get](../../../csharp/language-reference/keywords/get.md) 属性访问器用于返回属性值，而 [set](../../../csharp/language-reference/keywords/set.md) 属性访问器用于分配新值。</span><span class="sxs-lookup"><span data-stu-id="cd44d-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="cd44d-109">这些访问器可以具有不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="cd44d-109">These accessors can have different access levels.</span></span> <span data-ttu-id="cd44d-110">有关详细信息，请参阅[限制访问器可访问性](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)。</span><span class="sxs-lookup"><span data-stu-id="cd44d-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="cd44d-111">[value](../../../csharp/language-reference/keywords/value.md) 关键字用于定义由 `set` 访问器分配的值。</span><span class="sxs-lookup"><span data-stu-id="cd44d-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="cd44d-112">属性可以是*读-写*属性（既有 `get` 访问器又有 `set` 访问器）、*只读*属性（有 `get` 访问器，但没有 `set` 访问器）或*只写*访问器（有 `set` 访问器，但没有 `get` 访问器）。</span><span class="sxs-lookup"><span data-stu-id="cd44d-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="cd44d-113">只写属性很少出现，常用于限制对敏感数据的访问。</span><span class="sxs-lookup"><span data-stu-id="cd44d-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="cd44d-114">不需要自定义访问器代码的简单属性可以作为表达式主体定义或[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)来实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="cd44d-115">具有支持字段的属性</span><span class="sxs-lookup"><span data-stu-id="cd44d-115">Properties with backing fields</span></span>

<span data-ttu-id="cd44d-116">有一个实现属性的基本模式，该模式使用私有支持字段来设置和检索属性值。</span><span class="sxs-lookup"><span data-stu-id="cd44d-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="cd44d-117">`get` 访问器返回私有字段的值，`set` 访问器在向私有字段赋值之前可能会执行一些数据验证。</span><span class="sxs-lookup"><span data-stu-id="cd44d-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="cd44d-118">这两个访问器还可以在存储或返回数据之前对其执行某些转换或计算。</span><span class="sxs-lookup"><span data-stu-id="cd44d-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="cd44d-119">下面的示例阐释了此模式。</span><span class="sxs-lookup"><span data-stu-id="cd44d-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="cd44d-120">在此示例中，`TimePeriod` 类表示时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cd44d-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="cd44d-121">在内部，该类将时间间隔以秒为单位存储在名为 `seconds` 的私有字段中。</span><span class="sxs-lookup"><span data-stu-id="cd44d-121">Internally, the class stores the time interval in seconds in a private field named `seconds`.</span></span> <span data-ttu-id="cd44d-122">名为 `Hours` 的读-写属性允许客户以小时为单位指定时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cd44d-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="cd44d-123">`get` 和 `set` 访问器都会执行小时与秒之间的必要转换。</span><span class="sxs-lookup"><span data-stu-id="cd44d-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="cd44d-124">此外，`set` 访问器还会验证数据，如果小时数无效，则引发 @System.ArgumentOutOfRangeException。</span><span class="sxs-lookup"><span data-stu-id="cd44d-124">In addition, the `set` accessor validates the data and throws an @System.ArgumentOutOfRangeException if the number of hours is invalid.</span></span> 
   
 <span data-ttu-id="cd44d-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd44d-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="cd44d-126">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="cd44d-126">Expression body definitions</span></span>  

 <span data-ttu-id="cd44d-127">属性访问器通常由单行语句组成，这些语句只分配或只返回表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="cd44d-127">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="cd44d-128">可以将这些属性作为 expression-bodied 成员来实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-128">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="cd44d-129">`=>` 符号后跟用于为属性赋值或从属性中检索值的表达式，即组成了表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="cd44d-129">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="cd44d-130">从 C# 6 开始，只读属性可以将 `get` 访问器作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-130">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="cd44d-131">在这种情况下，既不使用 `get` 访问器关键字，也不使用 `return` 关键字。</span><span class="sxs-lookup"><span data-stu-id="cd44d-131">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="cd44d-132">下面的示例将只读 `Name` 属性作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-132">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 <span data-ttu-id="cd44d-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd44d-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span></span>  

 <span data-ttu-id="cd44d-134">从 C# 7 开始，`get` 和 `set` 访问器都可以作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-134">Starting with C# 7, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="cd44d-135">在这种情况下，必须使用 `get` 和 `set` 关键字。</span><span class="sxs-lookup"><span data-stu-id="cd44d-135">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="cd44d-136">下面的示例阐释如何为这两个访问器使用表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="cd44d-136">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="cd44d-137">请注意，`return` 关键字不与 `get` 访问器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cd44d-137">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  <span data-ttu-id="cd44d-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd44d-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span></span>  

## <a name="auto-implemented-properties"></a><span data-ttu-id="cd44d-139">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="cd44d-139">Auto-implemented properties</span></span>

<span data-ttu-id="cd44d-140">在某些情况下，属性 `get` 和 `set` 访问器仅向支持字段赋值或仅从其中检索值，而不包括任何附加逻辑。</span><span class="sxs-lookup"><span data-stu-id="cd44d-140">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="cd44d-141">通过使用自动实现的属性，既能简化代码，还能让 C# 编译器透明地提供支持字段。</span><span class="sxs-lookup"><span data-stu-id="cd44d-141">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="cd44d-142">如果属性具有 `get` 和 `set` 访问器，则必须自动实现这两个访问器。</span><span class="sxs-lookup"><span data-stu-id="cd44d-142">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="cd44d-143">自动实现的属性通过以下方式定义：使用 `get` 和 `set` 关键字，但不提供任何实现。</span><span class="sxs-lookup"><span data-stu-id="cd44d-143">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="cd44d-144">下面的示例与上一个示例基本相同，只不过 `Name` 和 `Price` 是自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="cd44d-144">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="cd44d-145">请注意，该示例还删除了参数化构造函数，以便通过调用默认构造函数和[对象初始值设定项](object-and-collection-initializers.md)立即初始化 `SaleItem` 对象。</span><span class="sxs-lookup"><span data-stu-id="cd44d-145">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the default constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  <span data-ttu-id="cd44d-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd44d-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span></span>  

## <a name="related-sections"></a><span data-ttu-id="cd44d-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="cd44d-147">Related sections</span></span>  
  
-   [<span data-ttu-id="cd44d-148">使用属性</span><span class="sxs-lookup"><span data-stu-id="cd44d-148">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="cd44d-149">接口属性</span><span class="sxs-lookup"><span data-stu-id="cd44d-149">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="cd44d-150">属性与索引器之间的比较</span><span class="sxs-lookup"><span data-stu-id="cd44d-150">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="cd44d-151">限制访问器可访问性</span><span class="sxs-lookup"><span data-stu-id="cd44d-151">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [<span data-ttu-id="cd44d-152">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="cd44d-152">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="cd44d-153">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cd44d-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd44d-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd44d-154">See also</span></span>
 <span data-ttu-id="cd44d-155">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd44d-155">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cd44d-156">[使用属性](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="cd44d-156">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="cd44d-157">[索引器](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd44d-157">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="cd44d-158">[get 关键字](../../../csharp/language-reference/keywords/get.md)  </span><span class="sxs-lookup"><span data-stu-id="cd44d-158">[get keyword](../../../csharp/language-reference/keywords/get.md)  </span></span>  
 [<span data-ttu-id="cd44d-159">set 关键字</span><span class="sxs-lookup"><span data-stu-id="cd44d-159">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)    

