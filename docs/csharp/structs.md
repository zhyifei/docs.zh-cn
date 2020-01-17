---
title: 结构 - C# 指南
description: 了解结构类型及其创建方式
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: cdfe2a763058b8f568ede2ff93c918c2dae874f7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346906"
---
# <a name="structs"></a><span data-ttu-id="dc91d-103">结构</span><span class="sxs-lookup"><span data-stu-id="dc91d-103">Structs</span></span>

<span data-ttu-id="dc91d-104">结构  是一个值类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-104">A *struct* is a value type.</span></span> <span data-ttu-id="dc91d-105">创建结构时，分配给结构的变量保留结构的实际数据。</span><span class="sxs-lookup"><span data-stu-id="dc91d-105">When a struct is created, the variable to which the struct is assigned holds the struct's actual data.</span></span> <span data-ttu-id="dc91d-106">将结构分配给新变量时，会复制结构。</span><span class="sxs-lookup"><span data-stu-id="dc91d-106">When the struct is assigned to a new variable, it is copied.</span></span> <span data-ttu-id="dc91d-107">因此，新变量和原始变量包含相同数据的副本（共两个）。</span><span class="sxs-lookup"><span data-stu-id="dc91d-107">The new variable and the original variable therefore contain two separate copies of the same data.</span></span> <span data-ttu-id="dc91d-108">对一个副本所做的更改不会影响另一个副本。</span><span class="sxs-lookup"><span data-stu-id="dc91d-108">Changes made to one copy do not affect the other copy.</span></span>

<span data-ttu-id="dc91d-109">值类型变量直接包含它们的值，这意味着在声明变量的任何上下文中内联分配内存。</span><span class="sxs-lookup"><span data-stu-id="dc91d-109">Value type variables directly contain their values, which means that the memory is allocated inline in whatever context the variable is declared.</span></span> <span data-ttu-id="dc91d-110">对于值类型变量，没有单独的堆分配或垃圾回收开销。</span><span class="sxs-lookup"><span data-stu-id="dc91d-110">There is no separate heap allocation or garbage collection overhead for value-type variables.</span></span>

<span data-ttu-id="dc91d-111">值类型分为两类：[结构](language-reference/keywords/struct.md)和[枚举](language-reference/builtin-types/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="dc91d-111">There are two categories of value types: [struct](language-reference/keywords/struct.md) and [enum](language-reference/builtin-types/enum.md).</span></span>

<span data-ttu-id="dc91d-112">内置数值类型是结构，包含可以访问的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="dc91d-112">The built-in numeric types are structs, and they have properties and methods that you can access:</span></span>

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

<span data-ttu-id="dc91d-113">不过，可以声明数值类型并向其赋值，就像它们是简单的非聚合类型一样：</span><span class="sxs-lookup"><span data-stu-id="dc91d-113">But you declare and assign values to them as if they were simple non-aggregate types:</span></span>

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

<span data-ttu-id="dc91d-114">例如，值类型为“密封”  ，这意味着不能从 <xref:System.Int32> 派生类型，并且不能将结构定义为从任何用户定义的类或结构继承，因为结构只能从 <xref:System.ValueType> 继承。</span><span class="sxs-lookup"><span data-stu-id="dc91d-114">Value types are *sealed*, which means, for example, that you cannot derive a type from <xref:System.Int32>, and you cannot define a struct to inherit from any user-defined class or struct because a struct can only inherit from <xref:System.ValueType>.</span></span> <span data-ttu-id="dc91d-115">但是，一个结构可以实现一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="dc91d-115">However, a struct can implement one or more interfaces.</span></span> <span data-ttu-id="dc91d-116">可将结构类型强制转换为接口类型；这将导致“装箱”  操作，以将结构包装在托管堆上的引用类型对象内。</span><span class="sxs-lookup"><span data-stu-id="dc91d-116">You can cast a struct type to an interface type; this causes a *boxing* operation to wrap the struct inside a reference type object on the managed heap.</span></span> <span data-ttu-id="dc91d-117">当将值类型传递到接受 <xref:System.Object> 作为输入参数的方法时，将发生装箱操作。</span><span class="sxs-lookup"><span data-stu-id="dc91d-117">Boxing operations occur when you pass a value type to a method that takes an <xref:System.Object> as an input parameter.</span></span> <span data-ttu-id="dc91d-118">有关详细信息，请参阅[装箱和取消装箱](./programming-guide/types/boxing-and-unboxing.md )。</span><span class="sxs-lookup"><span data-stu-id="dc91d-118">For more information, see [Boxing and Unboxing](./programming-guide/types/boxing-and-unboxing.md ).</span></span>

<span data-ttu-id="dc91d-119">使用 [struct](./language-reference/keywords/struct.md) 关键字可以创建你自己的自定义值类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-119">You use the [struct](./language-reference/keywords/struct.md) keyword to create your own custom value types.</span></span> <span data-ttu-id="dc91d-120">结构通常用作一小组相关变量的容器，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="dc91d-120">Typically, a struct is used as a container for a small set of related variables, as shown in the following example:</span></span>

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

<span data-ttu-id="dc91d-121">有关 .NET Framework 中的值类型的详细信息，请参阅[通用类型系统](../standard/common-type-system.md)。</span><span class="sxs-lookup"><span data-stu-id="dc91d-121">For more information about value types in the .NET Framework, see [Common Type System](../standard/common-type-system.md).</span></span>

<span data-ttu-id="dc91d-122">结构与类具有许多相同的语法，但结构比类受到的限制更多：</span><span class="sxs-lookup"><span data-stu-id="dc91d-122">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>

- <span data-ttu-id="dc91d-123">在结构声明中，除非将字段声明为 `const` 或 `static`，否则无法初始化。</span><span class="sxs-lookup"><span data-stu-id="dc91d-123">Within a struct declaration, fields cannot be initialized unless they are declared as `const` or `static`.</span></span>

- <span data-ttu-id="dc91d-124">结构不能声明无参数构造函数（没有参数的构造函数）或终结器。</span><span class="sxs-lookup"><span data-stu-id="dc91d-124">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>

- <span data-ttu-id="dc91d-125">结构在分配时进行复制。</span><span class="sxs-lookup"><span data-stu-id="dc91d-125">Structs are copied on assignment.</span></span> <span data-ttu-id="dc91d-126">将结构分配给新变量时，将复制所有数据，并且对新副本所做的任何修改不会更改原始副本的数据。</span><span class="sxs-lookup"><span data-stu-id="dc91d-126">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="dc91d-127">使用值类型的集合（如 Dictionary<string, myStruct>）时，请务必记住这一点。</span><span class="sxs-lookup"><span data-stu-id="dc91d-127">This is important to remember when working with collections of value types such as Dictionary<string, myStruct>.</span></span>

- <span data-ttu-id="dc91d-128">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-128">Structs are value types and classes are reference types.</span></span>

- <span data-ttu-id="dc91d-129">与类不同，无需使用 `new` 运算符即可对结构进行实例化。</span><span class="sxs-lookup"><span data-stu-id="dc91d-129">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dc91d-130">在 .NET Core 2.1 及更高版本中，必须使用 [new 运算符](language-reference/operators/new-operator.md)或[默认文本](language-reference/operators/default.md#default-literal)，或者通过初始化每个私有字段来实例化结构类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-130">In .NET Core 2.1 and later, a struct type must be instantiated by using the [new operator](language-reference/operators/new-operator.md) or [default literal](language-reference/operators/default.md#default-literal), or by initializing each of its private fields.</span></span> <span data-ttu-id="dc91d-131">有关详细信息，请参阅[从版本 2.0 迁移到 2.1 的中断性变更](../core/compatibility/2.0-2.1.md#corefx)。</span><span class="sxs-lookup"><span data-stu-id="dc91d-131">For more information, see [Breaking changes for migration from version 2.0 to 2.1](../core/compatibility/2.0-2.1.md#corefx).</span></span>

- <span data-ttu-id="dc91d-132">结构可以声明具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="dc91d-132">Structs can declare constructors that have parameters.</span></span>

- <span data-ttu-id="dc91d-133">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="dc91d-133">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="dc91d-134">所有结构都直接继承自 <xref:System.ValueType>，后者继承自 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="dc91d-134">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>

- <span data-ttu-id="dc91d-135">和类一样，结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="dc91d-135">A struct, like a class, can implement interfaces.</span></span>

## <a name="nullable-value-types"></a><span data-ttu-id="dc91d-136">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="dc91d-136">Nullable value types</span></span>

<span data-ttu-id="dc91d-137">普通值类型不能具有 [null](language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="dc91d-137">Ordinary value types cannot have a value of [null](language-reference/keywords/null.md).</span></span> <span data-ttu-id="dc91d-138">不过，可以在类型后面附加 `?`，创建可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-138">However, you can create nullable value types by affixing a `?` after the type.</span></span> <span data-ttu-id="dc91d-139">例如，`int?` 是还可以包含值 [null](./language-reference/keywords/null.md) 的 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="dc91d-139">For example, `int?` is an `int` type that can also have the value [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="dc91d-140">可以为 null 的值类型是泛型结构类型 <xref:System.Nullable%601> 的实例。</span><span class="sxs-lookup"><span data-stu-id="dc91d-140">Nullable value types are instances of the generic struct type <xref:System.Nullable%601>.</span></span> <span data-ttu-id="dc91d-141">在将数据传入和传出数据库（数值可能为 NULL 或未定义）时，可为空的值类型特别有用。</span><span class="sxs-lookup"><span data-stu-id="dc91d-141">Nullable value types are especially useful when you are passing data to and from databases in which numeric values might be null or undefined.</span></span> <span data-ttu-id="dc91d-142">有关详细信息，请参阅[可以为 null 的值类型](language-reference/builtin-types/nullable-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="dc91d-142">For more information, see [Nullable value types](language-reference/builtin-types/nullable-value-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc91d-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc91d-143">See also</span></span>

- [<span data-ttu-id="dc91d-144">类</span><span class="sxs-lookup"><span data-stu-id="dc91d-144">Classes</span></span>](programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="dc91d-145">基本类型</span><span class="sxs-lookup"><span data-stu-id="dc91d-145">Basic Types</span></span>](basic-types.md)
