---
title: C# 7.2 中的新增功能
description: C# 7.2 中的新增功能概述。
ms.date: 08/16/2017
ms.openlocfilehash: 79402c9b569cb6848aaf240d83ba71338d525b35
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347415"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="2387b-103">C# 7.2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="2387b-103">What's new in C# 7.2</span></span>

<span data-ttu-id="2387b-104">C# 7.2 又是一个单点版本，它增添了大量有用的功能。</span><span class="sxs-lookup"><span data-stu-id="2387b-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="2387b-105">此版本的一项主要功能是避免不必要的复制或分配，进而更有效地处理值类型。</span><span class="sxs-lookup"><span data-stu-id="2387b-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span>

<span data-ttu-id="2387b-106">其余功能很微小，但值得拥有。</span><span class="sxs-lookup"><span data-stu-id="2387b-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="2387b-107">C# 7.2 使用[语言版本选择](../language-reference/configure-language-version.md)配置元素来选择编译器语言版本。</span><span class="sxs-lookup"><span data-stu-id="2387b-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="2387b-108">此版本中新增的语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="2387b-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="2387b-109">编写安全高效代码的技巧</span><span class="sxs-lookup"><span data-stu-id="2387b-109">Techniques for writing safe efficient code</span></span>](#safe-efficient-code-enhancements)
  - <span data-ttu-id="2387b-110">结合了多项语法改进，可使用引用语义处理值类型。</span><span class="sxs-lookup"><span data-stu-id="2387b-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="2387b-111">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="2387b-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="2387b-112">命名的参数可后接位置参数。</span><span class="sxs-lookup"><span data-stu-id="2387b-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="2387b-113">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="2387b-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="2387b-114">数值文字现可在任何打印数字前放置前导下划线。</span><span class="sxs-lookup"><span data-stu-id="2387b-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="2387b-115">`private protected` 访问修饰符</span><span class="sxs-lookup"><span data-stu-id="2387b-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="2387b-116">`private protected` 访问修饰符允许访问同一程序集中的派生类。</span><span class="sxs-lookup"><span data-stu-id="2387b-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
* [<span data-ttu-id="2387b-117">条件 `ref` 表达式</span><span class="sxs-lookup"><span data-stu-id="2387b-117">Conditional `ref` expressions</span></span>](#conditional-ref-expressions)
  - <span data-ttu-id="2387b-118">现在可以引用条件表达式 (`?:`) 的结果。</span><span class="sxs-lookup"><span data-stu-id="2387b-118">The result of a conditional expression (`?:`) can now be a reference.</span></span>

<span data-ttu-id="2387b-119">本文的其余部分概述了每个功能。</span><span class="sxs-lookup"><span data-stu-id="2387b-119">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="2387b-120">你将了解每项功能背后的原理。</span><span class="sxs-lookup"><span data-stu-id="2387b-120">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="2387b-121">将了解语法。</span><span class="sxs-lookup"><span data-stu-id="2387b-121">You'll learn the syntax.</span></span> <span data-ttu-id="2387b-122">可以使用 `dotnet try` 全局工具在环境中浏览这些功能：</span><span class="sxs-lookup"><span data-stu-id="2387b-122">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="2387b-123">安装 [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="2387b-123">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="2387b-124">克隆 [dotnet/try-samples](https://github.com/dotnet/try-samples) 存储库。</span><span class="sxs-lookup"><span data-stu-id="2387b-124">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="2387b-125">将当前目录设置为 try-samples 存储库的 csharp7 子目录   。</span><span class="sxs-lookup"><span data-stu-id="2387b-125">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="2387b-126">运行 `dotnet try`。</span><span class="sxs-lookup"><span data-stu-id="2387b-126">Run `dotnet try`.</span></span>

## <a name="safe-efficient-code-enhancements"></a><span data-ttu-id="2387b-127">安全高效的代码的增强功能</span><span class="sxs-lookup"><span data-stu-id="2387b-127">Safe efficient code enhancements</span></span>

<span data-ttu-id="2387b-128">利用 7.2 中引入的语言功能，可在使用引用语义时处理值类型。</span><span class="sxs-lookup"><span data-stu-id="2387b-128">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="2387b-129">它们旨在尽量减少值类型的复制，而不造成与引用类型使用相关的内存分配，进而提升性能。</span><span class="sxs-lookup"><span data-stu-id="2387b-129">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="2387b-130">功能包括：</span><span class="sxs-lookup"><span data-stu-id="2387b-130">The features include:</span></span>

- <span data-ttu-id="2387b-131">针对实参的 `in` 修饰符，指定形参通过引用传递，但不通过调用方法修改。</span><span class="sxs-lookup"><span data-stu-id="2387b-131">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="2387b-132">将 `in` 修饰符添加到参数是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="2387b-132">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="2387b-133">针对方法返回的 `ref readonly` 修饰符，指示方法通过引用返回其值，但不允许写入该对象。</span><span class="sxs-lookup"><span data-stu-id="2387b-133">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="2387b-134">如果向某个值赋予返回值，则添加 `ref readonly` 修饰符是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="2387b-134">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="2387b-135">将 `readonly` 修饰符添加到现有的 `ref` 返回语句是[不兼容的更改](version-update-considerations.md#incompatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="2387b-135">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="2387b-136">它要求调用方更新 `ref` 本地变量的声明以包含 `readonly` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="2387b-136">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="2387b-137">`readonly struct` 声明，指示结构不可变，且应作为 `in` 参数传递到其成员方法。</span><span class="sxs-lookup"><span data-stu-id="2387b-137">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="2387b-138">将 `readonly` 修饰符添加到现有的结构声明是[二进制兼容的更改](version-update-considerations.md#binary-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="2387b-138">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="2387b-139">`ref struct` 声明，指示结构类型直接访问托管的内存，且必须始终分配有堆栈。</span><span class="sxs-lookup"><span data-stu-id="2387b-139">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="2387b-140">将 `ref` 修饰符添加到现有 `struct` 声明是[不兼容的更改](version-update-considerations.md#incompatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="2387b-140">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="2387b-141">`ref struct` 不能是类的成员，也不能用于可能在堆上分配的其他位置。</span><span class="sxs-lookup"><span data-stu-id="2387b-141">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="2387b-142">可以在[编写安全高效的代码](../write-safe-efficient-code.md)中详细了解所有这些更改。</span><span class="sxs-lookup"><span data-stu-id="2387b-142">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="2387b-143">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="2387b-143">Non-trailing named arguments</span></span>

<span data-ttu-id="2387b-144">方法调用现可使用位于位置参数前面的命名参数（若这些命名参数的位置正确）。</span><span class="sxs-lookup"><span data-stu-id="2387b-144">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="2387b-145">有关详细信息，请参阅[命名参数和可选参数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="2387b-145">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="2387b-146">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="2387b-146">Leading underscores in numeric literals</span></span>

<span data-ttu-id="2387b-147">C# 7.0 中实现了对数字分隔符的支持，但这不允许文字值的第一个字符是 `_`。</span><span class="sxs-lookup"><span data-stu-id="2387b-147">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="2387b-148">十六进制文本和二进制文件现可以 `_` 开头。</span><span class="sxs-lookup"><span data-stu-id="2387b-148">Hex and binary numeric literals may now begin with an `_`.</span></span>

<span data-ttu-id="2387b-149">例如:</span><span class="sxs-lookup"><span data-stu-id="2387b-149">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="2387b-150">_private protected_ 访问修饰符</span><span class="sxs-lookup"><span data-stu-id="2387b-150">_private protected_ access modifier</span></span>

<span data-ttu-id="2387b-151">新的复合访问修饰符：`private protected` 指示可通过包含同一程序集中声明的类或派生类来访问成员。</span><span class="sxs-lookup"><span data-stu-id="2387b-151">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="2387b-152">虽然 `protected internal` 允许通过同一程序集中的类或派生类进行访问，但 `private protected` 限制对同一程序集中声明的派生类的访问。</span><span class="sxs-lookup"><span data-stu-id="2387b-152">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="2387b-153">有关详细信息，请参阅语言参考中的[访问修饰符](../language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="2387b-153">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="conditional-ref-expressions"></a><span data-ttu-id="2387b-154">条件 `ref` 表达式</span><span class="sxs-lookup"><span data-stu-id="2387b-154">Conditional `ref` expressions</span></span>

<span data-ttu-id="2387b-155">最后，条件表达式可能生成 ref 结果而不是值。</span><span class="sxs-lookup"><span data-stu-id="2387b-155">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="2387b-156">例如，你将编写以下内容以检索对两个数组之一中第一个元素的引用：</span><span class="sxs-lookup"><span data-stu-id="2387b-156">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="2387b-157">变量 `r` 是对 `arr` 或 `otherArr` 中第一个值的引用。</span><span class="sxs-lookup"><span data-stu-id="2387b-157">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="2387b-158">有关详细信息，请参阅语言参考中的[条件运算符 (?:)](../language-reference/operators/conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="2387b-158">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>
