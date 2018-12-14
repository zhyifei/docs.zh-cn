---
title: C# 7.2 中的新增功能
description: C# 7.2 中的新增功能概述。
ms.date: 08/16/2017
ms.openlocfilehash: 7ee6d06750f82c9529beaed3cc665f876af08888
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148170"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="25cf3-103">C# 7.2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="25cf3-103">What's new in C# 7.2</span></span>

<span data-ttu-id="25cf3-104">C# 7.2 又是一个单点版本，它增添了大量有用的功能。</span><span class="sxs-lookup"><span data-stu-id="25cf3-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="25cf3-105">此版本的一项主要功能是避免不必要的复制或分配，进而更有效地处理值类型。</span><span class="sxs-lookup"><span data-stu-id="25cf3-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="25cf3-106">其余功能很微小，但值得拥有。</span><span class="sxs-lookup"><span data-stu-id="25cf3-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="25cf3-107">C# 7.2 使用[语言版本选择](../language-reference/configure-language-version.md)配置元素来选择编译器语言版本。</span><span class="sxs-lookup"><span data-stu-id="25cf3-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="25cf3-108">此版本中新增的语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="25cf3-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="25cf3-109">编写安全高效代码的技巧</span><span class="sxs-lookup"><span data-stu-id="25cf3-109">Techniques for writing safe efficient code</span></span>](#safe-efficient-code-enhancements)
  - <span data-ttu-id="25cf3-110">结合了多项语法改进，可使用引用语义处理值类型。</span><span class="sxs-lookup"><span data-stu-id="25cf3-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="25cf3-111">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="25cf3-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="25cf3-112">命名的参数可后接位置参数。</span><span class="sxs-lookup"><span data-stu-id="25cf3-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="25cf3-113">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="25cf3-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="25cf3-114">数值文字现可在任何打印数字前放置前导下划线。</span><span class="sxs-lookup"><span data-stu-id="25cf3-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="25cf3-115">`private protected` 访问修饰符</span><span class="sxs-lookup"><span data-stu-id="25cf3-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="25cf3-116">`private protected` 访问修饰符允许访问同一程序集中的派生类。</span><span class="sxs-lookup"><span data-stu-id="25cf3-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
* [<span data-ttu-id="25cf3-117">条件 `ref` 表达式</span><span class="sxs-lookup"><span data-stu-id="25cf3-117">Conditional `ref` expressions</span></span>](#conditional-ref-expressions)
  - <span data-ttu-id="25cf3-118">现在可以引用条件表达式 (`?:`) 的结果。</span><span class="sxs-lookup"><span data-stu-id="25cf3-118">The result of a conditional expression (`?:`) can now be a reference.</span></span>

## <a name="safe-efficient-code-enhancements"></a><span data-ttu-id="25cf3-119">安全高效的代码的增强功能</span><span class="sxs-lookup"><span data-stu-id="25cf3-119">Safe efficient code enhancements</span></span>

<span data-ttu-id="25cf3-120">利用 7.2 中引入的语言功能，可在使用引用语义时处理值类型。</span><span class="sxs-lookup"><span data-stu-id="25cf3-120">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="25cf3-121">它们旨在尽量减少值类型的复制，而不造成与引用类型使用相关的内存分配，进而提升性能。</span><span class="sxs-lookup"><span data-stu-id="25cf3-121">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="25cf3-122">功能包括：</span><span class="sxs-lookup"><span data-stu-id="25cf3-122">The features include:</span></span>

 - <span data-ttu-id="25cf3-123">针对实参的 `in` 修饰符，指定形参通过引用传递，但不通过调用方法修改。</span><span class="sxs-lookup"><span data-stu-id="25cf3-123">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="25cf3-124">将 `in` 修饰符添加到参数是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-124">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
 - <span data-ttu-id="25cf3-125">针对方法返回的 `ref readonly` 修饰符，指示方法通过引用返回其值，但不允许写入该对象。</span><span class="sxs-lookup"><span data-stu-id="25cf3-125">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="25cf3-126">如果向某个值赋予返回值，则添加 `ref readonly` 修饰符是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-126">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="25cf3-127">将 `readonly` 修饰符添加到现有的 `ref` 返回语句是[不兼容的更改](version-update-considerations.md#incompatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-127">Adding the `readonly` modifer to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="25cf3-128">它要求调用方更新 `ref` 本地变量的声明以包含 `readonly` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="25cf3-128">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
 - <span data-ttu-id="25cf3-129">`readonly struct` 声明，指示结构不可变，且应作为 `in` 参数传递到其成员方法。</span><span class="sxs-lookup"><span data-stu-id="25cf3-129">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="25cf3-130">将 `readonly` 修饰符添加到现有的结构声明是[二进制兼容的更改](version-update-considerations.md#binary-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-130">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
 - <span data-ttu-id="25cf3-131">`ref struct` 声明，指示结构类型直接访问托管的内存，且必须始终分配有堆栈。</span><span class="sxs-lookup"><span data-stu-id="25cf3-131">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="25cf3-132">将 `ref` 修饰符添加到现有 `struct` 声明是[不兼容的更改](version-update-considerations.md#incompatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-132">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="25cf3-133">`ref struct` 不能是类的成员，也不能用于可能在堆上分配的其他位置。</span><span class="sxs-lookup"><span data-stu-id="25cf3-133">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="25cf3-134">可以在[编写安全高效的代码](../write-safe-efficient-code.md)中详细了解所有这些更改。</span><span class="sxs-lookup"><span data-stu-id="25cf3-134">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="25cf3-135">非尾随命名参数</span><span class="sxs-lookup"><span data-stu-id="25cf3-135">Non-trailing named arguments</span></span>

<span data-ttu-id="25cf3-136">方法调用现可使用位于位置参数前面的命名参数（若这些命名参数的位置正确）。</span><span class="sxs-lookup"><span data-stu-id="25cf3-136">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="25cf3-137">有关详细信息，请参阅[命名参数和可选参数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-137">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="25cf3-138">数值文字中的前导下划线</span><span class="sxs-lookup"><span data-stu-id="25cf3-138">Leading underscores in numeric literals</span></span>

<span data-ttu-id="25cf3-139">C# 7.0 中实现了对数字分隔符的支持，但这不允许文字值的第一个字符是 `_`。</span><span class="sxs-lookup"><span data-stu-id="25cf3-139">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="25cf3-140">十六进制文本和二进制文件现可以 `_` 开头。</span><span class="sxs-lookup"><span data-stu-id="25cf3-140">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="25cf3-141">例如:</span><span class="sxs-lookup"><span data-stu-id="25cf3-141">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="25cf3-142">_private protected_ 访问修饰符</span><span class="sxs-lookup"><span data-stu-id="25cf3-142">_private protected_ access modifier</span></span>

<span data-ttu-id="25cf3-143">新的复合访问修饰符：`private protected` 指示可通过包含同一程序集中声明的类或派生类来访问成员。</span><span class="sxs-lookup"><span data-stu-id="25cf3-143">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="25cf3-144">虽然 `protected internal` 允许通过同一程序集中的类或派生类进行访问，但 `private protected` 限制对同一程序集中声明的派生类的访问。</span><span class="sxs-lookup"><span data-stu-id="25cf3-144">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="25cf3-145">有关详细信息，请参阅语言参考中的[访问修饰符](../language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-145">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="conditional-ref-expressions"></a><span data-ttu-id="25cf3-146">条件 `ref` 表达式</span><span class="sxs-lookup"><span data-stu-id="25cf3-146">Conditional `ref` expressions</span></span>

<span data-ttu-id="25cf3-147">最后，条件表达式可能生成 ref 结果而不是值。</span><span class="sxs-lookup"><span data-stu-id="25cf3-147">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="25cf3-148">例如，你将编写以下内容以检索对两个数组之一中第一个元素的引用：</span><span class="sxs-lookup"><span data-stu-id="25cf3-148">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="25cf3-149">变量 `r` 是对 `arr` 或 `otherArr` 中第一个值的引用。</span><span class="sxs-lookup"><span data-stu-id="25cf3-149">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="25cf3-150">有关详细信息，请参阅语言参考中的[条件运算符 (?:)](../language-reference/operators/conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="25cf3-150">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>
