---
title: volatile - C# 参考
ms.custom: seodec18
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 7200432780cb5a65bc5420b41c5dbd2e27a2c01f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633109"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="55580-102">volatile（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="55580-102">volatile (C# Reference)</span></span>

<span data-ttu-id="55580-103">`volatile` 关键字指示一个字段可以由多个同时执行的线程修改。</span><span class="sxs-lookup"><span data-stu-id="55580-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="55580-104">出于性能原因，编译器，运行时系统甚至硬件都可能重新排列对存储器位置的读取和写入。</span><span class="sxs-lookup"><span data-stu-id="55580-104">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="55580-105">声明了 `volatile` 的字段不进行这些优化。</span><span class="sxs-lookup"><span data-stu-id="55580-105">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="55580-106">添加 `volatile` 修饰符可确保所有线程观察易失性写入操作（由任何其他线程执行）时的观察顺序与写入操作的执行顺序一致。</span><span class="sxs-lookup"><span data-stu-id="55580-106">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="55580-107">不确保从所有执行线程整体来看时所有易失性写入操作均按执行顺序排序。</span><span class="sxs-lookup"><span data-stu-id="55580-107">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="55580-108">`volatile` 关键字可应用于以下类型的字段：</span><span class="sxs-lookup"><span data-stu-id="55580-108">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="55580-109">引用类型。</span><span class="sxs-lookup"><span data-stu-id="55580-109">Reference types.</span></span>
- <span data-ttu-id="55580-110">指针类型（在不安全的上下文中）。</span><span class="sxs-lookup"><span data-stu-id="55580-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="55580-111">请注意，虽然指针本身可以是可变的，但是它指向的对象不能是可变的。</span><span class="sxs-lookup"><span data-stu-id="55580-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="55580-112">换句话说，不能声明“指向可变对象的指针”。</span><span class="sxs-lookup"><span data-stu-id="55580-112">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="55580-113">简单类型，如 `sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`char`、`float` 和 `bool`。</span><span class="sxs-lookup"><span data-stu-id="55580-113">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="55580-114">具有以下基本类型之一的 `enum` 类型：`byte`、`sbyte`、`short`、`ushort`、`int` 或 `uint`。</span><span class="sxs-lookup"><span data-stu-id="55580-114">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="55580-115">已知为引用类型的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="55580-115">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="55580-116"><xref:System.IntPtr> 和 <xref:System.UIntPtr>。</span><span class="sxs-lookup"><span data-stu-id="55580-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="55580-117">其他类型（包括 `double` 和 `long`）无法标记为 `volatile`，因为对这些类型的字段的读取和写入不能保证是原子的。</span><span class="sxs-lookup"><span data-stu-id="55580-117">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="55580-118">若要保护对这些类型字段的多线程访问，请使用 <xref:System.Threading.Interlocked> 类成员或使用 [`lock`](lock-statement.md) 语句保护访问权限。</span><span class="sxs-lookup"><span data-stu-id="55580-118">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="55580-119">`volatile` 关键字只能应用于 `class` 或 `struct` 的字段。</span><span class="sxs-lookup"><span data-stu-id="55580-119">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="55580-120">不能将局部变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="55580-120">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="55580-121">示例</span><span class="sxs-lookup"><span data-stu-id="55580-121">Example</span></span>

<span data-ttu-id="55580-122">下面的示例说明如何将公共字段变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="55580-122">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="55580-123">下面的示例演示如何创建辅助线程，并用它与主线程并行执行处理。</span><span class="sxs-lookup"><span data-stu-id="55580-123">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="55580-124">有关多线程处理的详细信息，请参阅[托管线程处理](../../../standard/threading/index.md)。</span><span class="sxs-lookup"><span data-stu-id="55580-124">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="55580-125">将 `volatile` 修饰符添加到 `_shouldStop` 的声明后，将始终获得相同的结果（类似于前面代码中显示的片段）。</span><span class="sxs-lookup"><span data-stu-id="55580-125">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="55580-126">但是，如果 `_shouldStop` 成员上没有该修饰符，则行为是不可预测的。</span><span class="sxs-lookup"><span data-stu-id="55580-126">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="55580-127">`DoWork` 方法可能会优化成员访问，从而导致读取陈旧数据。</span><span class="sxs-lookup"><span data-stu-id="55580-127">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="55580-128">鉴于多线程编程的性质，读取陈旧数据的次数是不可预测的。</span><span class="sxs-lookup"><span data-stu-id="55580-128">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="55580-129">不同的程序运行会产生一些不同的结果。</span><span class="sxs-lookup"><span data-stu-id="55580-129">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="55580-130">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="55580-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="55580-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="55580-131">See also</span></span>

- [<span data-ttu-id="55580-132">C# 语言规范：可变关键字</span><span class="sxs-lookup"><span data-stu-id="55580-132">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="55580-133">C# 参考</span><span class="sxs-lookup"><span data-stu-id="55580-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="55580-134">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="55580-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="55580-135">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="55580-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="55580-136">修饰符</span><span class="sxs-lookup"><span data-stu-id="55580-136">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="55580-137">lock 语句</span><span class="sxs-lookup"><span data-stu-id="55580-137">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
