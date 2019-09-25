---
title: stackalloc 运算符 - C# 参考
ms.custom: seodec18
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9ef5f98f2b4973c5873417ecc9a71c187e7299b9
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182416"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="e51bc-102">stackalloc 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e51bc-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="e51bc-103">`stackalloc` 运算符在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="e51bc-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="e51bc-104">该方法返回时，将自动丢弃在方法执行期间创建的堆栈中分配的内存块。</span><span class="sxs-lookup"><span data-stu-id="e51bc-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="e51bc-105">不能显式释放使用 `stackalloc` 运算符分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e51bc-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="e51bc-106">堆栈中分配的内存块不受[垃圾回收](../../../standard/garbage-collection/index.md)的影响，也不必通过 [`fixed` 语句](../keywords/fixed-statement.md)固定。</span><span class="sxs-lookup"><span data-stu-id="e51bc-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="e51bc-107">在表达式 `stackalloc T[E]` 中，`T` 须为[非托管类型](../builtin-types/unmanaged-types.md)，`E` 须为 `int` 类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="e51bc-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="e51bc-108">可以将 `stackalloc` 运算符的结果分配给以下任一类型的变量：</span><span class="sxs-lookup"><span data-stu-id="e51bc-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="e51bc-109">从 C# 7.2 开始的 <xref:System.Span%601?displayProperty=nameWithType> 或 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e51bc-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="e51bc-110">将堆栈中分配的内存块分配给 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 变量时，不必使用 [unsafe](../keywords/unsafe.md) 上下文。</span><span class="sxs-lookup"><span data-stu-id="e51bc-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="e51bc-111">使用这些类型时，可以在[条件表达式](conditional-operator.md)或赋值表达式中使用 `stackalloc` 表达式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e51bc-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="e51bc-112">从 C#8.0 开始，只要允许使用 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 变量，就可以在其他表达式中使用 `stackalloc` 表达式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e51bc-112">Starting with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="e51bc-113">建议尽可能使用 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 类型来处理堆栈中分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e51bc-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="e51bc-114">[指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e51bc-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="e51bc-115">如前面的示例所示，在使用指针类型时必须使用 `unsafe` 上下文。</span><span class="sxs-lookup"><span data-stu-id="e51bc-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="e51bc-116">对于指针类型，只能在局部变量声明中使用 `stackalloc` 表达式来初始化变量。</span><span class="sxs-lookup"><span data-stu-id="e51bc-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="e51bc-117">新分配的内存的内容未定义。</span><span class="sxs-lookup"><span data-stu-id="e51bc-117">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="e51bc-118">从 C# 7.3 开始，可以使用数组初始值设定项语法来定义新分配的内存的内容。</span><span class="sxs-lookup"><span data-stu-id="e51bc-118">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="e51bc-119">下面的示例演示执行此操作的各种方法：</span><span class="sxs-lookup"><span data-stu-id="e51bc-119">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="e51bc-120">安全性</span><span class="sxs-lookup"><span data-stu-id="e51bc-120">Security</span></span>

<span data-ttu-id="e51bc-121">使用 `stackalloc` 会自动启用公共语言运行时 (CLR) 中的缓冲区溢出检测功能。</span><span class="sxs-lookup"><span data-stu-id="e51bc-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="e51bc-122">如果检测到缓冲区溢出，则将尽快终止进程，以便将执行恶意代码的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="e51bc-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e51bc-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e51bc-123">C# language specification</span></span>

<span data-ttu-id="e51bc-124">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[堆栈分配](~/_csharplang/spec/unsafe-code.md#stack-allocation)部分。</span><span class="sxs-lookup"><span data-stu-id="e51bc-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e51bc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e51bc-125">See also</span></span>

- [<span data-ttu-id="e51bc-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e51bc-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e51bc-127">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="e51bc-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="e51bc-128">指针相关的运算符</span><span class="sxs-lookup"><span data-stu-id="e51bc-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="e51bc-129">指针类型</span><span class="sxs-lookup"><span data-stu-id="e51bc-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e51bc-130">内存和跨度相关类型</span><span class="sxs-lookup"><span data-stu-id="e51bc-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
