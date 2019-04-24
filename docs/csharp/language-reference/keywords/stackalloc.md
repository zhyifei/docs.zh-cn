---
title: stackalloc 关键字 - C# 参考
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 61a27e777a1919a2a6fc5140a311835a8f3daba9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480802"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="2d9ed-102">stackalloc（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2d9ed-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="2d9ed-103">使用 `stackalloc` 关键字在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="2d9ed-104">将分配的块分配给 <xref:System.Span%601?displayName=nameWithType>（而不是 `int*`），可以在安全块中实现堆栈分配。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="2d9ed-105">不需要 `unsafe` 上下文。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d9ed-106">备注</span><span class="sxs-lookup"><span data-stu-id="2d9ed-106">Remarks</span></span>

<span data-ttu-id="2d9ed-107">此关键字仅在局部变量初始值设定项中有效。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="2d9ed-108">以下代码导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="2d9ed-109">自 C# 7.3 起，可以对 `stackalloc` 数组使用数组初始值设定项语法。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="2d9ed-110">以下所有声明都声明了一个包含三个元素的数组，这三个元素的值为整数 `1`、`2` 和 `3`。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="2d9ed-111">第二个初始化将内存分配到 <xref:System.ReadOnlySpan%601>，指明无法修改内存。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="2d9ed-112">当涉及指针类型时，`stackalloc` 需要 [unsafe](unsafe.md) 上下文。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="2d9ed-113">有关详细信息，请参阅[不安全代码和指针](../../programming-guide/unsafe-code-pointers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="2d9ed-114">`stackalloc` 就像 C 运行时库中的 [_alloca](/cpp/c-runtime-library/reference/alloca)。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="2d9ed-115">示例</span><span class="sxs-lookup"><span data-stu-id="2d9ed-115">Examples</span></span>

<span data-ttu-id="2d9ed-116">下面的示例计算并显示 Fibonacci 序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="2d9ed-117">每个数字是前两个数字的总和。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="2d9ed-118">在此代码中，在堆栈上分配足够大的可包含 20 个 `int` 类型元素的内存块，而不是在堆上分配。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="2d9ed-119">块的地址存储在 `Span` `fib` 中。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="2d9ed-120">此内存不受垃圾回收的限制，因此不必对其进行单边锁定（使用 [fixed](fixed-statement.md)）。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="2d9ed-121">内存块的生存期受到定义此内存块的方法的生存期的限制。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="2d9ed-122">在方法返回之前，无法释放内存。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="2d9ed-123">下面的示例将 `stackalloc` 整数数组初始化为位掩码，其中每个元素内都有一个位集。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="2d9ed-124">下面展示了自 C# 7.3 起新增的初始值设定项语法：</span><span class="sxs-lookup"><span data-stu-id="2d9ed-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="2d9ed-125">安全性</span><span class="sxs-lookup"><span data-stu-id="2d9ed-125">Security</span></span>

<span data-ttu-id="2d9ed-126">应尽可能使用 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601>，因为不安全代码的安全性低于安全替代项。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="2d9ed-127">即使与指针一起使用，使用 `stackalloc` 也会在公共语言运行时 (CLR) 中自动启用缓冲区溢出检测功能。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="2d9ed-128">如果检测到缓冲区溢出，则将尽快终止进程，以便将执行恶意代码的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="2d9ed-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2d9ed-129">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2d9ed-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2d9ed-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d9ed-130">See also</span></span>

- [<span data-ttu-id="2d9ed-131">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2d9ed-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2d9ed-132">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2d9ed-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2d9ed-133">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="2d9ed-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2d9ed-134">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="2d9ed-134">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="2d9ed-135">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="2d9ed-135">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
