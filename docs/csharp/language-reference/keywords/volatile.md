---
title: volatile（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a><span data-ttu-id="df114-102">volatile（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="df114-102">volatile (C# Reference)</span></span>
<span data-ttu-id="df114-103">`volatile` 关键字指示一个字段可以由多个同时执行的线程修改。</span><span class="sxs-lookup"><span data-stu-id="df114-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="df114-104">声明为 `volatile` 的字段不受编译器优化（假定由单个线程访问）的限制。</span><span class="sxs-lookup"><span data-stu-id="df114-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="df114-105">这样可以确保该字段在任何时间呈现的都是最新的值。</span><span class="sxs-lookup"><span data-stu-id="df114-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="df114-106">`volatile` 修饰符通常用于由多个线程访问、但不使用 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 语句对访问进行序列化的字段。</span><span class="sxs-lookup"><span data-stu-id="df114-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="df114-107">`volatile` 关键字可应用于以下类型的字段：</span><span class="sxs-lookup"><span data-stu-id="df114-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="df114-108">引用类型。</span><span class="sxs-lookup"><span data-stu-id="df114-108">Reference types.</span></span>  
  
-   <span data-ttu-id="df114-109">指针类型（在不安全的上下文中）。</span><span class="sxs-lookup"><span data-stu-id="df114-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="df114-110">请注意，虽然指针本身可以是可变的，但是它指向的对象不能是可变的。</span><span class="sxs-lookup"><span data-stu-id="df114-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="df114-111">换句话说，不能声明“指向可变对象的指针”。</span><span class="sxs-lookup"><span data-stu-id="df114-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="df114-112">类型，如 sbyte、byte、short、ushort、int、uint、char、float 和 bool。</span><span class="sxs-lookup"><span data-stu-id="df114-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="df114-113">具有以下基类型之一的枚举类型：byte、sbyte、short、ushort、int 或 uint。</span><span class="sxs-lookup"><span data-stu-id="df114-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="df114-114">已知为引用类型的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="df114-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="df114-115"><xref:System.IntPtr> 和 <xref:System.UIntPtr>。</span><span class="sxs-lookup"><span data-stu-id="df114-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="df114-116">可变关键字仅可应用于类或结构的字段。</span><span class="sxs-lookup"><span data-stu-id="df114-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="df114-117">不能将局部变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="df114-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df114-118">示例</span><span class="sxs-lookup"><span data-stu-id="df114-118">Example</span></span>  
 <span data-ttu-id="df114-119">下面的示例说明如何将公共字段变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="df114-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="df114-120">示例</span><span class="sxs-lookup"><span data-stu-id="df114-120">Example</span></span>  
 <span data-ttu-id="df114-121">下面的示例演示如何创建辅助线程，并用它与主线程并行执行处理。</span><span class="sxs-lookup"><span data-stu-id="df114-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="df114-122">有关多线程处理的背景信息，请参阅 [线程](../../../standard/threading/index.md)和[线程](../../programming-guide/concepts/threading/index.md)。</span><span class="sxs-lookup"><span data-stu-id="df114-122">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="df114-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="df114-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df114-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df114-124">See Also</span></span>  
 [<span data-ttu-id="df114-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="df114-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="df114-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="df114-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="df114-127">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="df114-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="df114-128">修饰符</span><span class="sxs-lookup"><span data-stu-id="df114-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
