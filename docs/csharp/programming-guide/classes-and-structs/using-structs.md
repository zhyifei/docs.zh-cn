---
title: 使用 struct - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 4cfb3b184491e42194204899e26d7f1966a68427
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596000"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="385b9-102">使用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="385b9-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="385b9-103">`struct` 类型适用于表示轻量级对象，如 `Point`、 `Rectangle`和 `Color`。</span><span class="sxs-lookup"><span data-stu-id="385b9-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="385b9-104">尽管用它来表示一个点就如同具有 [Auto-Implemented Properties（自动实现的属性）](../../language-reference/keywords/class.md) 的 [类](./auto-implemented-properties.md)那样方便，但在某些情况下，使用 [结构](../../language-reference/keywords/struct.md) 可能更高效。</span><span class="sxs-lookup"><span data-stu-id="385b9-104">Although it is just as convenient to represent a point as a [class](../../language-reference/keywords/class.md) with [Auto-Implemented Properties](./auto-implemented-properties.md), a [struct](../../language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="385b9-105">例如，如果你声明具有 1000 个 `Point` 对象的数组，那么你将分配额外的内存用于引用每个对象；在这种情况下，使用结构将更为便宜。</span><span class="sxs-lookup"><span data-stu-id="385b9-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="385b9-106">因为 .NET Framework 包含一个名为 <xref:System.Drawing.Point> 的对象，所以本示例中的结构名称为“Coords”。</span><span class="sxs-lookup"><span data-stu-id="385b9-106">Because the .NET Framework contains an object called <xref:System.Drawing.Point>, the struct in this example is named "Coords" instead.</span></span>  
  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 <span data-ttu-id="385b9-107">定义结构的默认（无参数）构造函数是错误的。</span><span class="sxs-lookup"><span data-stu-id="385b9-107">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="385b9-108">在结构体中初始化实例字段也是错误的。</span><span class="sxs-lookup"><span data-stu-id="385b9-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="385b9-109">只能通过使用参数化构造函数、隐式、无参数构造函数、[对象初始值设定项](./object-and-collection-initializers.md)或在声明结构后单独访问成员来初始化外部可访问的结构成员。</span><span class="sxs-lookup"><span data-stu-id="385b9-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, parameterless constructor, an [object initializer](./object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="385b9-110">任何私有或其他不可访问的成员需要以独占方式使用构造函数。</span><span class="sxs-lookup"><span data-stu-id="385b9-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>
  
 <span data-ttu-id="385b9-111">使用 [new](../../language-reference/operators/new-operator.md) 运算符创建结构对象时，会创建结构对象且会遵循[构造函数签名](./constructors.md#constructor-syntax)来调用相应的构造函数。</span><span class="sxs-lookup"><span data-stu-id="385b9-111">When you create a struct object using the [new](../../language-reference/operators/new-operator.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](./constructors.md#constructor-syntax).</span></span> <span data-ttu-id="385b9-112">与类不同，可以对结构进行实例化，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="385b9-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="385b9-113">在这种情况下，没有调用任何构造函数，从而提高了分配效率。</span><span class="sxs-lookup"><span data-stu-id="385b9-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="385b9-114">但是，字段将保持为未分配状态且必须在在初始化所有字段之后才可使用对象。</span><span class="sxs-lookup"><span data-stu-id="385b9-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="385b9-115">这包括无法通过属性获取或设置值。</span><span class="sxs-lookup"><span data-stu-id="385b9-115">This includes the inability to get or set values through properties.</span></span>

 <span data-ttu-id="385b9-116">如果使用默认的无参数构造函数实例化结构对象，则根据成员的[默认值](../../language-reference/keywords/default-values-table.md)分配所有成员。</span><span class="sxs-lookup"><span data-stu-id="385b9-116">If you instantiate a struct object using the default, parameterless constructor, all members are assigned according to their [default values](../../language-reference/keywords/default-values-table.md).</span></span>
  
 <span data-ttu-id="385b9-117">当为某个结构编写带有参数的构造函数时，必须显式初始化所有成员，否则一个或更多的成员将不被分配，并且不能使用结构，这会生成编译器错误 CS0171。</span><span class="sxs-lookup"><span data-stu-id="385b9-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error CS0171.</span></span>  
  
 <span data-ttu-id="385b9-118">由于全都是用于类的继承，因此没有用于结构的继承。</span><span class="sxs-lookup"><span data-stu-id="385b9-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="385b9-119">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="385b9-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="385b9-120">但是，它可以从基类 <xref:System.Object>继承。</span><span class="sxs-lookup"><span data-stu-id="385b9-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="385b9-121">结构也可以实现接口，且实现方法与类相同。</span><span class="sxs-lookup"><span data-stu-id="385b9-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="385b9-122">不能使用关键字 `struct`声明一个类。</span><span class="sxs-lookup"><span data-stu-id="385b9-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="385b9-123">在 C# 中，类和结构在语义上是不同的。</span><span class="sxs-lookup"><span data-stu-id="385b9-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="385b9-124">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="385b9-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="385b9-125">有关更多信息，请参阅 [值类型](../../language-reference/keywords/value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="385b9-125">For more information, see [Value Types](../../language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="385b9-126">除非需要引用类型语义，将较小的类声明为结构，可以提高系统的处理效率。</span><span class="sxs-lookup"><span data-stu-id="385b9-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="385b9-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="385b9-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="385b9-128">说明</span><span class="sxs-lookup"><span data-stu-id="385b9-128">Description</span></span>  
 <span data-ttu-id="385b9-129">此示例同时使用了默认构造函数和参数化构造函数来演示 `struct` 初始化。</span><span class="sxs-lookup"><span data-stu-id="385b9-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="385b9-130">代码</span><span class="sxs-lookup"><span data-stu-id="385b9-130">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="385b9-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="385b9-131">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="385b9-132">说明</span><span class="sxs-lookup"><span data-stu-id="385b9-132">Description</span></span>  
 <span data-ttu-id="385b9-133">此示例演示了一个特定于结构的功能。</span><span class="sxs-lookup"><span data-stu-id="385b9-133">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="385b9-134">此功能可以创建 Coords 对象，而无需使用 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="385b9-134">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="385b9-135">如果将 `struct` 替换为 `class`，程序将不会进行编译。</span><span class="sxs-lookup"><span data-stu-id="385b9-135">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="385b9-136">代码</span><span class="sxs-lookup"><span data-stu-id="385b9-136">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="385b9-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="385b9-137">See also</span></span>

- [<span data-ttu-id="385b9-138">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="385b9-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="385b9-139">类和结构</span><span class="sxs-lookup"><span data-stu-id="385b9-139">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="385b9-140">结构</span><span class="sxs-lookup"><span data-stu-id="385b9-140">Structs</span></span>](./structs.md)
