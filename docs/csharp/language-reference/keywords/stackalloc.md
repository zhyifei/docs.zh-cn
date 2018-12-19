---
title: stackalloc 关键字 - C# 参考
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 31fdbacb01d1f6052c86d40c0bffc903130f216c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245504"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="82de6-102">stackalloc（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="82de6-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="82de6-103">在不安全代码上下文中使用 `stackalloc` 关键字在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="82de6-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="82de6-104">备注</span><span class="sxs-lookup"><span data-stu-id="82de6-104">Remarks</span></span>

<span data-ttu-id="82de6-105">此关键字仅在局部变量初始值设定项中有效。</span><span class="sxs-lookup"><span data-stu-id="82de6-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="82de6-106">以下代码导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="82de6-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="82de6-107">自 C# 7.3 起，可以对 `stackalloc` 数组使用数组初始值设定项语法。</span><span class="sxs-lookup"><span data-stu-id="82de6-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="82de6-108">以下所有声明都声明了一个包含三个元素的数组，这三个元素的值为整数 `1`、`2` 和 `3`：</span><span class="sxs-lookup"><span data-stu-id="82de6-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="82de6-109">由于涉及指针类型，因此 `stackalloc` 需要 [unsafe](unsafe.md) 上下文。</span><span class="sxs-lookup"><span data-stu-id="82de6-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="82de6-110">有关详细信息，请参阅[不安全代码和指针](../../programming-guide/unsafe-code-pointers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="82de6-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="82de6-111">`stackalloc` 就像 C 运行时库中的 [_alloca](/cpp/c-runtime-library/reference/alloca)。</span><span class="sxs-lookup"><span data-stu-id="82de6-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="82de6-112">示例</span><span class="sxs-lookup"><span data-stu-id="82de6-112">Examples</span></span>

<span data-ttu-id="82de6-113">下面的示例计算并显示 Fibonacci 序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="82de6-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="82de6-114">每个数字是前两个数字的总和。</span><span class="sxs-lookup"><span data-stu-id="82de6-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="82de6-115">在此代码中，在堆栈上分配足够大的可包含 20 个 `int` 类型元素的内存块，而不是在堆上分配。</span><span class="sxs-lookup"><span data-stu-id="82de6-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="82de6-116">块的地址存储在指针 `fib` 中。</span><span class="sxs-lookup"><span data-stu-id="82de6-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="82de6-117">此内存不受垃圾回收的限制，因此不必对其进行单边锁定（使用 [fixed](fixed-statement.md)）。</span><span class="sxs-lookup"><span data-stu-id="82de6-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="82de6-118">内存块的生存期受到定义此内存块的方法的生存期的限制。</span><span class="sxs-lookup"><span data-stu-id="82de6-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="82de6-119">在方法返回之前，无法释放内存。</span><span class="sxs-lookup"><span data-stu-id="82de6-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="82de6-120">下面的示例将 `stackalloc` 整数数组初始化为位掩码，其中每个元素内都有一个位集。</span><span class="sxs-lookup"><span data-stu-id="82de6-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="82de6-121">下面展示了自 C# 7.3 起新增的初始值设定项语法：</span><span class="sxs-lookup"><span data-stu-id="82de6-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="82de6-122">安全性</span><span class="sxs-lookup"><span data-stu-id="82de6-122">Security</span></span>

<span data-ttu-id="82de6-123">不安全代码的安全性低于安全替代项。</span><span class="sxs-lookup"><span data-stu-id="82de6-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="82de6-124">但是，使用 `stackalloc` 会自动启用公共语言运行时 (CLR) 中的缓冲区溢出检测功能。</span><span class="sxs-lookup"><span data-stu-id="82de6-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="82de6-125">如果检测到缓冲区溢出，则将尽快终止进程，以便将执行恶意代码的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="82de6-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="82de6-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="82de6-126">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="82de6-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="82de6-127">See also</span></span>

- [<span data-ttu-id="82de6-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="82de6-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="82de6-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="82de6-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="82de6-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="82de6-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="82de6-131">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="82de6-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
- [<span data-ttu-id="82de6-132">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="82de6-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)