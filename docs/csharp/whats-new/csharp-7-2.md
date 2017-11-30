---
title: "什么是 C# 7.2 中的新增功能"
description: "C# 7.2 中的新增功能概述。"
keywords: "C# 语言设计中，7.2，Visual Studio 2017，"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="28967-104">什么是 C# 7.2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="28967-104">What's new in C# 7.2</span></span>

<span data-ttu-id="28967-105">C# 7.2 是添加了大量有用的功能的另一个点版本。</span><span class="sxs-lookup"><span data-stu-id="28967-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="28967-106">对于此版本的一个主题通过避免不必要的副本或分配更有效地工作与值类型。</span><span class="sxs-lookup"><span data-stu-id="28967-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="28967-107">其余的功能是小型、 nice 具有的功能。</span><span class="sxs-lookup"><span data-stu-id="28967-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="28967-108">使用 C# 7.2[语言版本选择](csharp-7-1.md#language-version-selection)要选择的编译器语言版本的配置元素。</span><span class="sxs-lookup"><span data-stu-id="28967-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="28967-109">在此版本中的新语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="28967-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="28967-110">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="28967-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="28967-111">启用使用引用语义的值类型的工作的语法改进的组合。</span><span class="sxs-lookup"><span data-stu-id="28967-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="28967-112">非尾随的命名自变量</span><span class="sxs-lookup"><span data-stu-id="28967-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="28967-113">命名自变量可以跟位置自变量。</span><span class="sxs-lookup"><span data-stu-id="28967-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="28967-114">中数值的前导下划线</span><span class="sxs-lookup"><span data-stu-id="28967-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="28967-115">数值现在可以在任何打印数字之前的前导下划线。</span><span class="sxs-lookup"><span data-stu-id="28967-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="28967-116">`private protected`访问修饰符</span><span class="sxs-lookup"><span data-stu-id="28967-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="28967-117">`private protected`访问修饰符将启用为同一程序集中的派生类的访问。</span><span class="sxs-lookup"><span data-stu-id="28967-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="28967-118">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="28967-118">Reference semantics with value types</span></span>

<span data-ttu-id="28967-119">7.2 中引入的语言功能允许你在使用引用语义时处理值类型。</span><span class="sxs-lookup"><span data-stu-id="28967-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="28967-120">它们旨在通过将复制的值类型而不会产生与使用引用类型相关联的内存分配降至最低来提高性能。</span><span class="sxs-lookup"><span data-stu-id="28967-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="28967-121">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="28967-121">The features include:</span></span>

 - <span data-ttu-id="28967-122">`in`参数，指定自变量是通过引用传递，但不是会修改调用的方法的修饰符。</span><span class="sxs-lookup"><span data-stu-id="28967-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="28967-123">`ref readonly`方法返回时，以指示一种方法通过引用返回其值，但不允许写入该对象上的修饰符。</span><span class="sxs-lookup"><span data-stu-id="28967-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="28967-124">`readonly struct`声明，以指示结构是不可变，并且应作为传递`in`到其成员方法的参数。</span><span class="sxs-lookup"><span data-stu-id="28967-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="28967-125">`ref struct`声明，以指示结构类型直接访问托管的内存，并且必须始终堆栈分配。</span><span class="sxs-lookup"><span data-stu-id="28967-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="28967-126">你可以阅读有关所有这些详细信息中的更改[值类型与引用语义一起使用](../reference-semantics-with-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="28967-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="28967-127">非尾随的命名自变量</span><span class="sxs-lookup"><span data-stu-id="28967-127">Non-trailing named arguments</span></span>

<span data-ttu-id="28967-128">方法调用现在可以使用命名参数之前位置自变量，当这些命名自变量位于正确位置的参数。</span><span class="sxs-lookup"><span data-stu-id="28967-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="28967-129">有关详细信息请参阅[命名实参和可选实参](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="28967-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="28967-130">中数值的前导下划线</span><span class="sxs-lookup"><span data-stu-id="28967-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="28967-131">在 C# 7.0 中的数字分隔符对的支持的实现不允许`_`为文字值的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="28967-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="28967-132">十六进制值和二进制数字文本可能会立即开始与`_`。</span><span class="sxs-lookup"><span data-stu-id="28967-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="28967-133">例如: </span><span class="sxs-lookup"><span data-stu-id="28967-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="28967-134">最后，新的复合的访问修饰符：`private protected`指示可能由在同一程序集中声明的派生类访问成员。</span><span class="sxs-lookup"><span data-stu-id="28967-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="28967-135">虽然`protected internal`允许的派生的类或位于同一程序集中的类访问`private protected`限制对同一程序集中所声明的派生类型的访问。</span><span class="sxs-lookup"><span data-stu-id="28967-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="28967-136">有关详细信息请参阅[访问修饰符](../language-reference/keywords/access-modifiers.md)语言参考中。</span><span class="sxs-lookup"><span data-stu-id="28967-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
