---
title: "C# 7.2 中的新增功能"
description: "C# 7.2 中的新增功能概述。"
keywords: "C# 语言设计, 7.2, Visual Studio 2017,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: cc861f186bea681bb32a2f8041a7155026679987
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="3e148-104">C# 7.2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="3e148-104">What's new in C# 7.2</span></span>

<span data-ttu-id="3e148-105">C# 7.2 又是一个单点版本，它增添了大量有用的功能。</span><span class="sxs-lookup"><span data-stu-id="3e148-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="3e148-106">此版本的一项主要功能是避免不必要的复制或分配，进而更有效地处理值类型。</span><span class="sxs-lookup"><span data-stu-id="3e148-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="3e148-107">其余功能很微小，但值得拥有。</span><span class="sxs-lookup"><span data-stu-id="3e148-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="3e148-108">C# 7.2 使用[语言版本选择](csharp-7-1.md#language-version-selection)配置元素来选择编译器语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e148-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="3e148-109">此版本中新增的语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="3e148-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="3e148-110">引用语义结合值类型</span><span class="sxs-lookup"><span data-stu-id="3e148-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="3e148-111">结合了多项语法改进，可使用引用语义处理值类型。</span><span class="sxs-lookup"><span data-stu-id="3e148-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="3e148-112">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="3e148-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="3e148-113">命名的参数可后接位置参数。</span><span class="sxs-lookup"><span data-stu-id="3e148-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="3e148-114">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="3e148-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="3e148-115">数值文字现可在任何打印数字前放置前导下划线。</span><span class="sxs-lookup"><span data-stu-id="3e148-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="3e148-116">`private protected` 访问修饰符</span><span class="sxs-lookup"><span data-stu-id="3e148-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="3e148-117">`private protected` 访问修饰符允许访问同一程序集中的派生类。</span><span class="sxs-lookup"><span data-stu-id="3e148-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="3e148-118">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="3e148-118">Reference semantics with value types</span></span>

<span data-ttu-id="3e148-119">利用 7.2 中引入的语言功能，可在使用引用语义时处理值类型。</span><span class="sxs-lookup"><span data-stu-id="3e148-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="3e148-120">它们旨在尽量减少值类型的复制，而不造成与引用类型使用相关的内存分配，进而提升性能。</span><span class="sxs-lookup"><span data-stu-id="3e148-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="3e148-121">功能包括：</span><span class="sxs-lookup"><span data-stu-id="3e148-121">The features include:</span></span>

 - <span data-ttu-id="3e148-122">针对实参的 `in` 修饰符，指定形参通过引用传递，但不通过调用方法修改。</span><span class="sxs-lookup"><span data-stu-id="3e148-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="3e148-123">针对方法返回的 `ref readonly` 修饰符，指示方法通过引用返回其值，但不允许写入该对象。</span><span class="sxs-lookup"><span data-stu-id="3e148-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="3e148-124">`readonly struct` 声明，指示结构不可变，且应作为 `in` 参数传递到其成员方法。</span><span class="sxs-lookup"><span data-stu-id="3e148-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="3e148-125">`ref struct` 声明，指示结构类型直接访问托管的内存，且必须始终分配有堆栈。</span><span class="sxs-lookup"><span data-stu-id="3e148-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="3e148-126">若要详细了解所有这些更改，请参阅[结合使用值类型和引用语义](../reference-semantics-with-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3e148-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="3e148-127">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="3e148-127">Non-trailing named arguments</span></span>

<span data-ttu-id="3e148-128">方法调用现可使用位于位置参数前面的命名参数（若这些命名参数的位置正确）。</span><span class="sxs-lookup"><span data-stu-id="3e148-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="3e148-129">有关详细信息，请参阅[命名参数和可选参数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="3e148-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="3e148-130">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="3e148-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="3e148-131">C# 7.0 中实现了对数字分隔符的支持，但这不允许文字值的第一个字符是 `_`。</span><span class="sxs-lookup"><span data-stu-id="3e148-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="3e148-132">十六进制文本和二进制文件现可以 `_` 开头。</span><span class="sxs-lookup"><span data-stu-id="3e148-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="3e148-133">例如：</span><span class="sxs-lookup"><span data-stu-id="3e148-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="3e148-134">最后，新的复合访问修饰符 `private protected` 指示可通过包含同一程序集中声明的类或派生类来访问成员。</span><span class="sxs-lookup"><span data-stu-id="3e148-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="3e148-135">虽然 `protected internal` 允许通过同一程序集中的类或派生类进行访问，但 `private protected` 限制对同一程序集中声明的派生类的访问。</span><span class="sxs-lookup"><span data-stu-id="3e148-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="3e148-136">有关详细信息，请参阅语言参考中的[访问修饰符](../language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="3e148-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
