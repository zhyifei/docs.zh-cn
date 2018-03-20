---
title: "C# 结构 - C# 语言介绍"
description: "了解 C# 值类型（称为“结构”）的基础知识"
keywords: ".NET, C#, 结构, 值类型"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: fa840d80bba98889f75863db2612f196d78bd3c5
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="structs"></a><span data-ttu-id="69dbe-104">结构</span><span class="sxs-lookup"><span data-stu-id="69dbe-104">Structs</span></span>

<span data-ttu-id="69dbe-105">***结构***是可以包含数据成员和函数成员的数据结构，这一点与类一样；与类不同的是，结构是值类型，无需进行堆分配。</span><span class="sxs-lookup"><span data-stu-id="69dbe-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="69dbe-106">结构类型的变量直接存储结构数据，而类类型的变量存储对动态分配的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="69dbe-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="69dbe-107">结构类型不支持用户指定的继承，并且所有结构类型均隐式继承自类型 <xref:System.ValueType>，后者又隐式继承自 `object`。</span><span class="sxs-lookup"><span data-stu-id="69dbe-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="69dbe-108">结构对包含值语义的小型数据结构特别有用。</span><span class="sxs-lookup"><span data-stu-id="69dbe-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="69dbe-109">复数、坐标系中的点或字典中的键值对都是结构的典型示例。</span><span class="sxs-lookup"><span data-stu-id="69dbe-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="69dbe-110">对小型数据结构使用结构（而不是类）在应用程序执行的内存分配次数上存在巨大差异。</span><span class="sxs-lookup"><span data-stu-id="69dbe-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="69dbe-111">例如，以下程序创建并初始化包含 100 个点的数组。</span><span class="sxs-lookup"><span data-stu-id="69dbe-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="69dbe-112">通过将 `Point` 实现为类，可单独实例化 101 个对象，一个对象用于数组，其他所有对象分别用于 100 个元素。</span><span class="sxs-lookup"><span data-stu-id="69dbe-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

<span data-ttu-id="69dbe-113">也可以选择将 Point 实现为结构。</span><span class="sxs-lookup"><span data-stu-id="69dbe-113">An alternative is to make Point a struct.</span></span>

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

<span data-ttu-id="69dbe-114">现在，仅实例化一个对象（即用于数组的对象），`Point` 实例存储内嵌在数组中。</span><span class="sxs-lookup"><span data-stu-id="69dbe-114">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="69dbe-115">结构构造函数使用 new 运算符进行调用，但这不并表示要分配内存。</span><span class="sxs-lookup"><span data-stu-id="69dbe-115">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="69dbe-116">结构构造函数只返回结构值本身（通常在堆栈的临时位置中），并在必要时复制此值，而非动态分配对象并返回对此对象的引用。</span><span class="sxs-lookup"><span data-stu-id="69dbe-116">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="69dbe-117">借助类，两个变量可以引用同一对象；因此，对一个变量执行的运算可能会影响另一个变量引用的对象。</span><span class="sxs-lookup"><span data-stu-id="69dbe-117">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="69dbe-118">借助结构，每个变量都有自己的数据副本；因此，对一个变量执行的运算不会影响另一个变量。</span><span class="sxs-lookup"><span data-stu-id="69dbe-118">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="69dbe-119">例如，以下代码片段生成的输出取决于 Point 是类还是结构。</span><span class="sxs-lookup"><span data-stu-id="69dbe-119">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

<span data-ttu-id="69dbe-120">如果 `Point` 是类，则输出 20，因为 a 和 b 引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="69dbe-120">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="69dbe-121">如果 Point 是结构，则输出 10，因为将 `a` 赋值给 `b` 创建了值副本，而此副本不受后面对 `a.x` 的赋值的影响。</span><span class="sxs-lookup"><span data-stu-id="69dbe-121">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="69dbe-122">以上示例突出显示了结构的两个限制。</span><span class="sxs-lookup"><span data-stu-id="69dbe-122">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="69dbe-123">首先，复制整个结构通常比复制对象引用效率更低，因此通过结构进行的赋值和值参数传递可能比通过引用类型成本更高。</span><span class="sxs-lookup"><span data-stu-id="69dbe-123">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="69dbe-124">其次，除 `in`、`ref` 和 `out` 参数以外，无法创建对结构的引用，这就表示在很多应用场景中都不能使用结构。</span><span class="sxs-lookup"><span data-stu-id="69dbe-124">Second, except for `in`, `ref`, and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="69dbe-125">[上一页](classes-and-objects.md)
[下一页](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="69dbe-125">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>
