---
title: 属性 - C# 编程指南
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- cs.properties
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
ms.openlocfilehash: c7374b77526a31c2c508516d5a3cb7cc3e29339a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583069"
---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="efe93-102">属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="efe93-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="efe93-103">属性是一种成员，它提供灵活的机制来读取、写入或计算私有字段的值。</span><span class="sxs-lookup"><span data-stu-id="efe93-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="efe93-104">属性可用作公共数据成员，但它们实际上是称为*访问器*的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="efe93-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="efe93-105">这使得可以轻松访问数据，还有助于提高方法的安全性和灵活性。</span><span class="sxs-lookup"><span data-stu-id="efe93-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="efe93-106">属性概述</span><span class="sxs-lookup"><span data-stu-id="efe93-106">Properties overview</span></span>  
  
- <span data-ttu-id="efe93-107">属性允许类公开获取和设置值的公共方法，而隐藏实现或验证代码。</span><span class="sxs-lookup"><span data-stu-id="efe93-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="efe93-108">[get](../../../csharp/language-reference/keywords/get.md) 属性访问器用于返回属性值，而 [set](../../../csharp/language-reference/keywords/set.md) 属性访问器用于分配新值。</span><span class="sxs-lookup"><span data-stu-id="efe93-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="efe93-109">这些访问器可以具有不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="efe93-109">These accessors can have different access levels.</span></span> <span data-ttu-id="efe93-110">有关详细信息，请参阅[限制访问器可访问性](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)。</span><span class="sxs-lookup"><span data-stu-id="efe93-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="efe93-111">[value](../../../csharp/language-reference/keywords/value.md) 关键字用于定义由 `set` 访问器分配的值。</span><span class="sxs-lookup"><span data-stu-id="efe93-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="efe93-112">属性可以是*读-写*属性（既有 `get` 访问器又有 `set` 访问器）、*只读*属性（有 `get` 访问器，但没有 `set` 访问器）或*只写*访问器（有 `set` 访问器，但没有 `get` 访问器）。</span><span class="sxs-lookup"><span data-stu-id="efe93-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="efe93-113">只写属性很少出现，常用于限制对敏感数据的访问。</span><span class="sxs-lookup"><span data-stu-id="efe93-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="efe93-114">不需要自定义访问器代码的简单属性可以作为表达式主体定义或[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)来实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="efe93-115">具有支持字段的属性</span><span class="sxs-lookup"><span data-stu-id="efe93-115">Properties with backing fields</span></span>

<span data-ttu-id="efe93-116">有一个实现属性的基本模式，该模式使用私有支持字段来设置和检索属性值。</span><span class="sxs-lookup"><span data-stu-id="efe93-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="efe93-117">`get` 访问器返回私有字段的值，`set` 访问器在向私有字段赋值之前可能会执行一些数据验证。</span><span class="sxs-lookup"><span data-stu-id="efe93-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="efe93-118">这两个访问器还可以在存储或返回数据之前对其执行某些转换或计算。</span><span class="sxs-lookup"><span data-stu-id="efe93-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="efe93-119">下面的示例阐释了此模式。</span><span class="sxs-lookup"><span data-stu-id="efe93-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="efe93-120">在此示例中，`TimePeriod` 类表示时间间隔。</span><span class="sxs-lookup"><span data-stu-id="efe93-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="efe93-121">在内部，该类将时间间隔以秒为单位存储在名为 `_seconds` 的私有字段中。</span><span class="sxs-lookup"><span data-stu-id="efe93-121">Internally, the class stores the time interval in seconds in a private field named `_seconds`.</span></span> <span data-ttu-id="efe93-122">名为 `Hours` 的读-写属性允许客户以小时为单位指定时间间隔。</span><span class="sxs-lookup"><span data-stu-id="efe93-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="efe93-123">`get` 和 `set` 访问器都会执行小时与秒之间的必要转换。</span><span class="sxs-lookup"><span data-stu-id="efe93-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="efe93-124">此外，`set` 访问器还会验证数据，如果小时数无效，则引发 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="efe93-124">In addition, the `set` accessor validates the data and throws an <xref:System.ArgumentOutOfRangeException> if the number of hours is invalid.</span></span> 
   
 [!code-csharp[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="efe93-125">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="efe93-125">Expression body definitions</span></span>  

 <span data-ttu-id="efe93-126">属性访问器通常由单行语句组成，这些语句只分配或只返回表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="efe93-126">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="efe93-127">可以将这些属性作为 expression-bodied 成员来实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-127">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="efe93-128">`=>` 符号后跟用于为属性赋值或从属性中检索值的表达式，即组成了表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="efe93-128">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="efe93-129">从 C# 6 开始，只读属性可以将 `get` 访问器作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-129">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="efe93-130">在这种情况下，既不使用 `get` 访问器关键字，也不使用 `return` 关键字。</span><span class="sxs-lookup"><span data-stu-id="efe93-130">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="efe93-131">下面的示例将只读 `Name` 属性作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-131">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 [!code-csharp[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]  

 <span data-ttu-id="efe93-132">从 C# 7.0 开始，`get` 和 `set` 访问器都可以作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-132">Starting with C# 7.0, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="efe93-133">在这种情况下，必须使用 `get` 和 `set` 关键字。</span><span class="sxs-lookup"><span data-stu-id="efe93-133">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="efe93-134">下面的示例阐释如何为这两个访问器使用表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="efe93-134">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="efe93-135">请注意，`return` 关键字不与 `get` 访问器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="efe93-135">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  [!code-csharp[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]  

## <a name="auto-implemented-properties"></a><span data-ttu-id="efe93-136">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="efe93-136">Auto-implemented properties</span></span>

<span data-ttu-id="efe93-137">在某些情况下，属性 `get` 和 `set` 访问器仅向支持字段赋值或仅从其中检索值，而不包括任何附加逻辑。</span><span class="sxs-lookup"><span data-stu-id="efe93-137">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="efe93-138">通过使用自动实现的属性，既能简化代码，还能让 C# 编译器透明地提供支持字段。</span><span class="sxs-lookup"><span data-stu-id="efe93-138">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="efe93-139">如果属性具有 `get` 和 `set` 访问器，则必须自动实现这两个访问器。</span><span class="sxs-lookup"><span data-stu-id="efe93-139">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="efe93-140">自动实现的属性通过以下方式定义：使用 `get` 和 `set` 关键字，但不提供任何实现。</span><span class="sxs-lookup"><span data-stu-id="efe93-140">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="efe93-141">下面的示例与上一个示例基本相同，只不过 `Name` 和 `Price` 是自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="efe93-141">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="efe93-142">请注意，该示例还删除了参数化构造函数，以便通过调用无参数构造函数和[对象初始值设定项](object-and-collection-initializers.md)立即初始化 `SaleItem` 对象。</span><span class="sxs-lookup"><span data-stu-id="efe93-142">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the parameterless constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  [!code-csharp[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]  

## <a name="related-sections"></a><span data-ttu-id="efe93-143">相关章节</span><span class="sxs-lookup"><span data-stu-id="efe93-143">Related sections</span></span>  
  
- [<span data-ttu-id="efe93-144">使用属性</span><span class="sxs-lookup"><span data-stu-id="efe93-144">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
- [<span data-ttu-id="efe93-145">接口属性</span><span class="sxs-lookup"><span data-stu-id="efe93-145">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
- [<span data-ttu-id="efe93-146">属性与索引器之间的比较</span><span class="sxs-lookup"><span data-stu-id="efe93-146">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="efe93-147">限制访问器可访问性</span><span class="sxs-lookup"><span data-stu-id="efe93-147">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
- [<span data-ttu-id="efe93-148">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="efe93-148">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="efe93-149">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="efe93-149">C# Language Specification</span></span>  

<span data-ttu-id="efe93-150">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[属性](~/_csharplang/spec/classes.md#properties)。</span><span class="sxs-lookup"><span data-stu-id="efe93-150">For more information, see [Properties](~/_csharplang/spec/classes.md#properties) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="efe93-151">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="efe93-151">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="efe93-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="efe93-152">See also</span></span>

- [<span data-ttu-id="efe93-153">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="efe93-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="efe93-154">使用属性</span><span class="sxs-lookup"><span data-stu-id="efe93-154">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="efe93-155">索引器</span><span class="sxs-lookup"><span data-stu-id="efe93-155">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="efe93-156">get 关键字</span><span class="sxs-lookup"><span data-stu-id="efe93-156">get keyword</span></span>](../../../csharp/language-reference/keywords/get.md)
- [<span data-ttu-id="efe93-157">set 关键字</span><span class="sxs-lookup"><span data-stu-id="efe93-157">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)
