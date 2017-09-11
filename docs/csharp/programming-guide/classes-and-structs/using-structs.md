---
title: "使用结构（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="f8f53-102">使用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f8f53-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="f8f53-103">`struct` 类型适用于表示轻量级对象，如 `Point`、 `Rectangle`和 `Color`。</span><span class="sxs-lookup"><span data-stu-id="f8f53-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="f8f53-104">尽管用它来表示一个点就如同具有 [Auto-Implemented Properties（自动实现的属性）](../../../csharp/language-reference/keywords/class.md) 的 [类](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)那样方便，但在某些情况下，使用 [结构](../../../csharp/language-reference/keywords/struct.md) 可能更高效。</span><span class="sxs-lookup"><span data-stu-id="f8f53-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="f8f53-105">例如，如果你声明具有 1000 个 `Point` 对象的数组，那么你将分配额外的内存用于引用每个对象；在这种情况下，使用结构将更为便宜。</span><span class="sxs-lookup"><span data-stu-id="f8f53-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="f8f53-106">因为 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 包含一个称为 <xref:System.Drawing.Point>的对象，因此在此示例中的结构改名为“CoOrds”。</span><span class="sxs-lookup"><span data-stu-id="f8f53-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="f8f53-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8f53-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="f8f53-108">定义结构的默认（无参数）构造函数是错误的。</span><span class="sxs-lookup"><span data-stu-id="f8f53-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="f8f53-109">在结构体中初始化实例字段也是错误的。</span><span class="sxs-lookup"><span data-stu-id="f8f53-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="f8f53-110">在声明结构后，只能通过使用参数化构造函数或通过逐个访问成员才可以初始化结构成员。</span><span class="sxs-lookup"><span data-stu-id="f8f53-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="f8f53-111">任何私有或其他不可访问的成员只能在构造函数中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="f8f53-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="f8f53-112">使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符创建结构对象时，将会创建结构对象且会调用相应的构造函数。</span><span class="sxs-lookup"><span data-stu-id="f8f53-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="f8f53-113">与类不同，可以对结构进行实例化，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="f8f53-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="f8f53-114">在这种情况下，没有调用任何构造函数，从而提高了分配效率。</span><span class="sxs-lookup"><span data-stu-id="f8f53-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="f8f53-115">但是，字段将保持为未分配状态且必须在在初始化所有字段之后才可使用对象。</span><span class="sxs-lookup"><span data-stu-id="f8f53-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="f8f53-116">当结构包含引用类型作为成员时，必须显式调用该成员的默认构造函数，否则成员会保持为未分配状态，且不能使用结构。</span><span class="sxs-lookup"><span data-stu-id="f8f53-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="f8f53-117">（这会导致编译器错误 CS0171。）</span><span class="sxs-lookup"><span data-stu-id="f8f53-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="f8f53-118">由于全都是用于类的继承，因此没有用于结构的继承。</span><span class="sxs-lookup"><span data-stu-id="f8f53-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="f8f53-119">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="f8f53-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="f8f53-120">但是，它可以从基类 <xref:System.Object>继承。</span><span class="sxs-lookup"><span data-stu-id="f8f53-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="f8f53-121">结构也可以实现接口，且实现方法与类相同。</span><span class="sxs-lookup"><span data-stu-id="f8f53-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="f8f53-122">不能使用关键字 `struct`声明一个类。</span><span class="sxs-lookup"><span data-stu-id="f8f53-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="f8f53-123">在 C# 中，类和结构在语义上是不同的。</span><span class="sxs-lookup"><span data-stu-id="f8f53-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="f8f53-124">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="f8f53-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="f8f53-125">有关更多信息，请参阅 [值类型](../../../csharp/language-reference/keywords/value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f53-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="f8f53-126">除非需要引用类型语义，将较小的类声明为结构，可以提高系统的处理效率。</span><span class="sxs-lookup"><span data-stu-id="f8f53-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="f8f53-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="f8f53-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="f8f53-128">描述</span><span class="sxs-lookup"><span data-stu-id="f8f53-128">Description</span></span>  
 <span data-ttu-id="f8f53-129">此示例同时使用了默认构造函数和参数化构造函数来演示 `struct` 初始化。</span><span class="sxs-lookup"><span data-stu-id="f8f53-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f8f53-130">代码</span><span class="sxs-lookup"><span data-stu-id="f8f53-130">Code</span></span>  
 <span data-ttu-id="f8f53-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8f53-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="f8f53-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8f53-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="f8f53-133">示例 2</span><span class="sxs-lookup"><span data-stu-id="f8f53-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="f8f53-134">描述</span><span class="sxs-lookup"><span data-stu-id="f8f53-134">Description</span></span>  
 <span data-ttu-id="f8f53-135">此示例演示了一个特定于结构的功能。</span><span class="sxs-lookup"><span data-stu-id="f8f53-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="f8f53-136">此功能可以创建 CoOrds 对象，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="f8f53-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="f8f53-137">如果将 `struct` 替换为 `class`，程序将不会进行编译。</span><span class="sxs-lookup"><span data-stu-id="f8f53-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f8f53-138">代码</span><span class="sxs-lookup"><span data-stu-id="f8f53-138">Code</span></span>  
 <span data-ttu-id="f8f53-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8f53-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="f8f53-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8f53-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f53-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8f53-141">See Also</span></span>  
 <span data-ttu-id="f8f53-142">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8f53-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f8f53-143">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8f53-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="f8f53-144">结构</span><span class="sxs-lookup"><span data-stu-id="f8f53-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

