---
title: volatile（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526214"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="eff05-102">volatile（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="eff05-102">volatile (C# Reference)</span></span>
<span data-ttu-id="eff05-103">`volatile` 关键字指示一个字段可以由多个同时执行的线程修改。</span><span class="sxs-lookup"><span data-stu-id="eff05-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="eff05-104">声明为 `volatile` 的字段不受编译器优化（假定由单个线程访问）的限制。</span><span class="sxs-lookup"><span data-stu-id="eff05-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="eff05-105">这些限制确保所有线程观察易失性写入操作（由任何其他线程执行）时的观察顺序与写入操作的执行顺序一致。</span><span class="sxs-lookup"><span data-stu-id="eff05-105">These restrictions ensure that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="eff05-106">不确保从所有执行线程整体来看时所有易失性写入操作均按执行顺序排序。</span><span class="sxs-lookup"><span data-stu-id="eff05-106">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>  
  
 <span data-ttu-id="eff05-107">`volatile` 修饰符通常用于由多个线程访问、但不使用 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 语句对访问进行序列化的字段。</span><span class="sxs-lookup"><span data-stu-id="eff05-107">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="eff05-108">`volatile` 关键字可应用于以下类型的字段：</span><span class="sxs-lookup"><span data-stu-id="eff05-108">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="eff05-109">引用类型。</span><span class="sxs-lookup"><span data-stu-id="eff05-109">Reference types.</span></span>  
  
-   <span data-ttu-id="eff05-110">指针类型（在不安全的上下文中）。</span><span class="sxs-lookup"><span data-stu-id="eff05-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="eff05-111">请注意，虽然指针本身可以是可变的，但是它指向的对象不能是可变的。</span><span class="sxs-lookup"><span data-stu-id="eff05-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="eff05-112">换句话说，不能声明“指向可变对象的指针”。</span><span class="sxs-lookup"><span data-stu-id="eff05-112">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="eff05-113">类型，如 sbyte、byte、short、ushort、int、uint、char、float 和 bool。</span><span class="sxs-lookup"><span data-stu-id="eff05-113">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="eff05-114">具有以下基类型之一的枚举类型：byte、sbyte、short、ushort、int 或 uint。</span><span class="sxs-lookup"><span data-stu-id="eff05-114">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="eff05-115">已知为引用类型的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="eff05-115">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="eff05-116"><xref:System.IntPtr> 和 <xref:System.UIntPtr>。</span><span class="sxs-lookup"><span data-stu-id="eff05-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="eff05-117">可变关键字仅可应用于类或结构的字段。</span><span class="sxs-lookup"><span data-stu-id="eff05-117">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="eff05-118">不能将局部变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="eff05-118">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eff05-119">示例</span><span class="sxs-lookup"><span data-stu-id="eff05-119">Example</span></span>  
 <span data-ttu-id="eff05-120">下面的示例说明如何将公共字段变量声明为 `volatile`。</span><span class="sxs-lookup"><span data-stu-id="eff05-120">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="eff05-121">示例</span><span class="sxs-lookup"><span data-stu-id="eff05-121">Example</span></span>  
 <span data-ttu-id="eff05-122">下面的示例演示如何创建辅助线程，并用它与主线程并行执行处理。</span><span class="sxs-lookup"><span data-stu-id="eff05-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="eff05-123">有关多线程处理的背景信息，请参阅[托管线程](../../../standard/threading/index.md)和[线程 (C#)](../../programming-guide/concepts/threading/index.md)。</span><span class="sxs-lookup"><span data-stu-id="eff05-123">For background information about multithreading, see [Managed Threading](../../../standard/threading/index.md) and [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="eff05-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="eff05-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eff05-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="eff05-125">See Also</span></span>

- [<span data-ttu-id="eff05-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="eff05-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="eff05-127">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="eff05-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="eff05-128">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="eff05-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="eff05-129">修饰符</span><span class="sxs-lookup"><span data-stu-id="eff05-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
