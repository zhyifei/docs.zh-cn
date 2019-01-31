---
title: 使用 struct - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 16a8c1c9534e121c24289fbbfff14485b0338f63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743941"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="2772a-102">使用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2772a-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="2772a-103">`struct` 类型适用于表示轻量级对象，如 `Point`、 `Rectangle`和 `Color`。</span><span class="sxs-lookup"><span data-stu-id="2772a-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="2772a-104">尽管用它来表示一个点就如同具有 [Auto-Implemented Properties（自动实现的属性）](../../../csharp/language-reference/keywords/class.md) 的 [类](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)那样方便，但在某些情况下，使用 [结构](../../../csharp/language-reference/keywords/struct.md) 可能更高效。</span><span class="sxs-lookup"><span data-stu-id="2772a-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="2772a-105">例如，如果你声明具有 1000 个 `Point` 对象的数组，那么你将分配额外的内存用于引用每个对象；在这种情况下，使用结构将更为便宜。</span><span class="sxs-lookup"><span data-stu-id="2772a-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="2772a-106">因为 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 包含一个称为 <xref:System.Drawing.Point> 的对象，因此在此示例中的结构改名为“Coords”。</span><span class="sxs-lookup"><span data-stu-id="2772a-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "Coords" instead.</span></span>  
  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 <span data-ttu-id="2772a-107">定义结构的默认（无参数）构造函数是错误的。</span><span class="sxs-lookup"><span data-stu-id="2772a-107">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="2772a-108">在结构体中初始化实例字段也是错误的。</span><span class="sxs-lookup"><span data-stu-id="2772a-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="2772a-109">只能通过使用参数化构造函数、隐式默认构造函数、[对象初始值设定项](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)，或在声明结构之后通过单独访问各个成员，才能初始化可从外部访问的结构成员。</span><span class="sxs-lookup"><span data-stu-id="2772a-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, default constructor, an [object initializer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="2772a-110">任何私有或其他不可访问的成员需要以独占方式使用构造函数。</span><span class="sxs-lookup"><span data-stu-id="2772a-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>
  
 <span data-ttu-id="2772a-111">使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符创建结构对象时，会创建结构对象且会遵循[构造函数签名](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax)来调用相应的构造函数。</span><span class="sxs-lookup"><span data-stu-id="2772a-111">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax).</span></span> <span data-ttu-id="2772a-112">与类不同，可以对结构进行实例化，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="2772a-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="2772a-113">在这种情况下，没有调用任何构造函数，从而提高了分配效率。</span><span class="sxs-lookup"><span data-stu-id="2772a-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="2772a-114">但是，字段将保持为未分配状态且必须在在初始化所有字段之后才可使用对象。</span><span class="sxs-lookup"><span data-stu-id="2772a-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="2772a-115">这包括无法通过自动实现的属性获取或设置值。</span><span class="sxs-lookup"><span data-stu-id="2772a-115">This includes the inability to get or set values through auto-implemented properties.</span></span>
 
 <span data-ttu-id="2772a-116">如果使用默认的无参数构造函数实例化结构对象，则根据成员的[默认值](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)分配所有成员。</span><span class="sxs-lookup"><span data-stu-id="2772a-116">If you instantiate a struct object using the default, parameterless constructor, all members are assigned according to their [default values](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>
  
 <span data-ttu-id="2772a-117">当为某个结构编写带有参数的构造函数时，必须显式初始化所有成员，否则一个或更多的成员将不被分配，并且不能使用结构，这会生成编译器错误 CS0171。</span><span class="sxs-lookup"><span data-stu-id="2772a-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error CS0171.</span></span>  
  
 <span data-ttu-id="2772a-118">由于全都是用于类的继承，因此没有用于结构的继承。</span><span class="sxs-lookup"><span data-stu-id="2772a-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="2772a-119">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="2772a-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="2772a-120">但是，它可以从基类 <xref:System.Object>继承。</span><span class="sxs-lookup"><span data-stu-id="2772a-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="2772a-121">结构也可以实现接口，且实现方法与类相同。</span><span class="sxs-lookup"><span data-stu-id="2772a-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="2772a-122">不能使用关键字 `struct`声明一个类。</span><span class="sxs-lookup"><span data-stu-id="2772a-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="2772a-123">在 C# 中，类和结构在语义上是不同的。</span><span class="sxs-lookup"><span data-stu-id="2772a-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="2772a-124">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="2772a-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="2772a-125">有关更多信息，请参阅 [值类型](../../../csharp/language-reference/keywords/value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2772a-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="2772a-126">除非需要引用类型语义，将较小的类声明为结构，可以提高系统的处理效率。</span><span class="sxs-lookup"><span data-stu-id="2772a-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="2772a-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="2772a-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="2772a-128">说明</span><span class="sxs-lookup"><span data-stu-id="2772a-128">Description</span></span>  
 <span data-ttu-id="2772a-129">此示例同时使用了默认构造函数和参数化构造函数来演示 `struct` 初始化。</span><span class="sxs-lookup"><span data-stu-id="2772a-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2772a-130">代码</span><span class="sxs-lookup"><span data-stu-id="2772a-130">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="2772a-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="2772a-131">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="2772a-132">说明</span><span class="sxs-lookup"><span data-stu-id="2772a-132">Description</span></span>  
 <span data-ttu-id="2772a-133">此示例演示了一个特定于结构的功能。</span><span class="sxs-lookup"><span data-stu-id="2772a-133">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="2772a-134">此功能可以创建 Coords 对象，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="2772a-134">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="2772a-135">如果将 `struct` 替换为 `class`，程序将不会进行编译。</span><span class="sxs-lookup"><span data-stu-id="2772a-135">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2772a-136">代码</span><span class="sxs-lookup"><span data-stu-id="2772a-136">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2772a-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="2772a-137">See also</span></span>

- [<span data-ttu-id="2772a-138">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2772a-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2772a-139">类和结构</span><span class="sxs-lookup"><span data-stu-id="2772a-139">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="2772a-140">结构</span><span class="sxs-lookup"><span data-stu-id="2772a-140">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
