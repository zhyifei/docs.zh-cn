---
title: "结构 - C# 指南"
description: "了解结构类型及其创建方式"
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e2a4bfdb46a69113d5eb8949df4ccf902acf9dee
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="structs"></a><span data-ttu-id="2b9ba-104">结构</span><span class="sxs-lookup"><span data-stu-id="2b9ba-104">Structs</span></span>
<span data-ttu-id="2b9ba-105">结构是一个值类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-105">A *struct* is a value type.</span></span> <span data-ttu-id="2b9ba-106">创建结构时，分配给结构的变量保留结构的实际数据。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-106">When a struct is created, the variable to which the struct is assigned holds the struct's actual data.</span></span> <span data-ttu-id="2b9ba-107">将结构分配给新变量时，会复制结构。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-107">When the struct is assigned to a new variable, it is copied.</span></span> <span data-ttu-id="2b9ba-108">因此，新变量和原始变量包含相同数据的副本（共两个）。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-108">The new variable and the original variable therefore contain two separate copies of the same data.</span></span> <span data-ttu-id="2b9ba-109">对一个副本所做的更改不会影响另一个副本。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-109">Changes made to one copy do not affect the other copy.</span></span>

<span data-ttu-id="2b9ba-110">值类型变量直接包含它们的值，这意味着在声明变量的任何上下文中内联分配内存。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-110">Value type variables directly contain their values, which means that the memory is allocated inline in whatever context the variable is declared.</span></span> <span data-ttu-id="2b9ba-111">对于值类型变量，没有单独的堆分配或垃圾回收开销。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-111">There is no separate heap allocation or garbage collection overhead for value-type variables.</span></span>  
  
<span data-ttu-id="2b9ba-112">值类型分为两类：[结构](./language-reference/keywords/struct.md)和[枚举](./language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-112">There are two categories of value types: [struct](./language-reference/keywords/struct.md) and [enum](./language-reference/keywords/enum.md).</span></span>  
  
<span data-ttu-id="2b9ba-113">内置的数值类型是结构，它们具有可访问的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="2b9ba-113">The built-in numeric types are structs, and they have properties and methods that you can access:</span></span>  
  
<span data-ttu-id="2b9ba-114">[!code-csharp静态方法[](../../samples/snippets/csharp/concepts/structs/static-method.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9ba-114">[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]</span></span>
  
<span data-ttu-id="2b9ba-115">但可将这些类型视为简单的非聚合类型，为其声明并赋值：</span><span class="sxs-lookup"><span data-stu-id="2b9ba-115">But you declare and assign values to them as if they were simple non-aggregate types:</span></span>  
  
<span data-ttu-id="2b9ba-116">[!code-csharp[赋值](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9ba-116">[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]</span></span> 
  
<span data-ttu-id="2b9ba-117">例如，值类型为“密封”，这意味着不能从 @System.Int32 派生类型，并且不能将结构定义为从任何用户定义的类或结构继承，因为结构只能从 @System.ValueType 继承。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-117">Value types are *sealed*, which means, for example, that you cannot derive a type from @System.Int32, and you cannot define a struct to inherit from any user-defined class or struct because a struct can only inherit from @System.ValueType.</span></span> <span data-ttu-id="2b9ba-118">但是，一个结构可以实现一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-118">However, a struct can implement one or more interfaces.</span></span> <span data-ttu-id="2b9ba-119">可将结构类型强制转换为接口类型；这将导致“装箱”操作，以将结构包装在托管堆上的引用类型对象内。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-119">You can cast a struct type to an interface type; this causes a *boxing* operation to wrap the struct inside a reference type object on the managed heap.</span></span> <span data-ttu-id="2b9ba-120">当将值类型传递到接受 @System.Object 作为输入参数的方法时，将发生装箱操作。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-120">Boxing operations occur when you pass a value type to a method that takes an @System.Object as an input parameter.</span></span> <span data-ttu-id="2b9ba-121">有关详细信息，请参阅[装箱和取消装箱](./programming-guide/types/boxing-and-unboxing.md )。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-121">For more information, see [Boxing and Unboxing](./programming-guide/types/boxing-and-unboxing.md ).</span></span>  
  
<span data-ttu-id="2b9ba-122">使用 [struct](./language-reference/keywords/struct.md) 关键字可以创建你自己的自定义值类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-122">You use the [struct](./language-reference/keywords/struct.md) keyword to create your own custom value types.</span></span> <span data-ttu-id="2b9ba-123">结构通常用作一小组相关变量的容器，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="2b9ba-123">Typically, a struct is used as a container for a small set of related variables, as shown in the following example:</span></span>  
  
<span data-ttu-id="2b9ba-124">[!code-csharp[Struct 关键字](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9ba-124">[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]</span></span>  
  
<span data-ttu-id="2b9ba-125">有关 .NET Framework 中的值类型的详细信息，请参阅[通用类型系统](../standard/common-type-system.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-125">For more information about value types in the .NET Framework, see [Common Type System](../standard/common-type-system.md).</span></span>  
    
<span data-ttu-id="2b9ba-126">结构与类具有许多相同的语法，但结构比类受到的限制更多：</span><span class="sxs-lookup"><span data-stu-id="2b9ba-126">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="2b9ba-127">在结构声明中，除非将字段声明为 `const` 或 `static`，否则无法初始化。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-127">Within a struct declaration, fields cannot be initialized unless they are declared as `const` or `static`.</span></span>  
  
-   <span data-ttu-id="2b9ba-128">结构不能声明默认构造函数（没有参数的构造函数）或终结器。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-128">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="2b9ba-129">结构在分配时进行复制。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-129">Structs are copied on assignment.</span></span> <span data-ttu-id="2b9ba-130">将结构分配给新变量时，将复制所有数据，并且对新副本所做的任何修改不会更改原始副本的数据。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-130">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="2b9ba-131">使用值类型的集合（如 Dictionary<string, myStruct>）时，请务必记住这一点。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-131">This is important to remember when working with collections of value types such as Dictionary<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="2b9ba-132">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-132">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="2b9ba-133">与类不同，无需使用 `new` 运算符即可对结构进行实例化。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-133">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="2b9ba-134">结构可以声明具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-134">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="2b9ba-135">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-135">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="2b9ba-136">所有结构都直接继承自 @System.ValueType，后者继承自 @System.Object。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-136">All structs inherit directly from @System.ValueType, which inherits from @System.Object.</span></span>  
  
-   <span data-ttu-id="2b9ba-137">结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-137">A struct can implement interfaces.</span></span>

## <a name="literal-values"></a><span data-ttu-id="2b9ba-138">文本值</span><span class="sxs-lookup"><span data-stu-id="2b9ba-138">Literal values</span></span>  
<span data-ttu-id="2b9ba-139">在 C# 中，文本值从编译器接收类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-139">In C#, literal values receive a type from the compiler.</span></span> <span data-ttu-id="2b9ba-140">可以通过在数字末尾追加一个字母来指定数字文本应采用的类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-140">You can specify how a numeric literal should be typed by appending a letter to the end of the number.</span></span> <span data-ttu-id="2b9ba-141">例如，若要指定应按浮点数来处理值 4.56，则在该数字后追加一个“f”或“F”：`4.56f`。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-141">For example, to specify that the value 4.56 should be treated as a float, append an "f" or "F" after the number: `4.56f`.</span></span> <span data-ttu-id="2b9ba-142">如果没有追加字母，编译器将推断该文本的 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-142">If no letter is appended, the compiler will infer the `double` type for the literal.</span></span> <span data-ttu-id="2b9ba-143">若要详细了解可以使用字母后缀指定哪些类型，请参阅[值类型](./language-reference/keywords/value-types.md)中的各个类型参考页。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-143">For more information about which types can be specified with letter suffixes, see the reference pages for individual types in [Value Types](./language-reference/keywords/value-types.md).</span></span>  
  
<span data-ttu-id="2b9ba-144">由于文本已类型化，且所有类型最终都是从 @System.Object 派生，因此可以编写和编译如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="2b9ba-144">Because literals are typed, and all types derive ultimately from @System.Object, you can write and compile code such as the following:</span></span>  
  
<span data-ttu-id="2b9ba-145">[!code-csharp文本值[](../../samples/snippets/csharp/concepts/structs/literals.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9ba-145">[!code-csharp[Literal Values](../../samples/snippets/csharp/concepts/structs/literals.cs)]</span></span>

<span data-ttu-id="2b9ba-146">最后两个示例演示 C# 7.0 中引入的语言功能。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-146">The last two examples demonstrate language features introduced in C# 7.0.</span></span> <span data-ttu-id="2b9ba-147">第一个示例演示可使用下划线字符作为数值文本内的数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-147">The first allows you to use an underscore character as a *digit separator* inside numeric literals.</span></span> <span data-ttu-id="2b9ba-148">可将它们放在数字中的任意位置，从而提高可读性。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-148">You can put them wherever you want between digits to improve readability.</span></span> <span data-ttu-id="2b9ba-149">不会对值产生影响。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-149">They have no effect on the value.</span></span>

<span data-ttu-id="2b9ba-150">第二个示例演示二进制文本，使用二进制文本可直接指定位模式，无需使用十六进制表示法。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-150">The second demonstrates *binary literals*, which allow you to specify bit patterns directly instead of using hexadecimal notation.</span></span>

## <a name="nullable-types"></a><span data-ttu-id="2b9ba-151">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="2b9ba-151">Nullable types</span></span>  
<span data-ttu-id="2b9ba-152">普通值类型不能具有 [null](./language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-152">Ordinary value types cannot have a value of [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="2b9ba-153">但是，可以通过在类型后面附加 **?**</span><span class="sxs-lookup"><span data-stu-id="2b9ba-153">However, you can create nullable value types by affixing a **?**</span></span> <span data-ttu-id="2b9ba-154">来创建可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-154">after the type.</span></span> <span data-ttu-id="2b9ba-155">例如，**int?** 属于 **int** 类型，也可以具有值 [null](./language-reference/keywords/null.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-155">For example, **int?** is an **int** type that can also have the value [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="2b9ba-156">在 CTS 中，可以为 null 的类型是泛型结构类型 @System.Nullable%601 的实例。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-156">In the CTS, nullable types are instances of the generic struct type @System.Nullable%601.</span></span> <span data-ttu-id="2b9ba-157">在将数据传入和传出数据库（数值可能为 null）时，可以为 null 的类型特别有用。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-157">Nullable types are especially useful when you are passing data to and from databases in which numeric values might be null.</span></span> <span data-ttu-id="2b9ba-158">有关详细信息，请参阅[可以为 Null 的类型（C# 编程指南）](./programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9ba-158">For more information, see [Nullable Types (C# Programming Guide)](./programming-guide/nullable-types/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b9ba-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b9ba-159">See also</span></span>
[<span data-ttu-id="2b9ba-160">类</span><span class="sxs-lookup"><span data-stu-id="2b9ba-160">Classes</span></span>](classes.md)

[<span data-ttu-id="2b9ba-161">基本类型</span><span class="sxs-lookup"><span data-stu-id="2b9ba-161">Basic Types</span></span>](basic-types.md)

