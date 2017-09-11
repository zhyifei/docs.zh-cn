---
title: "stackalloc（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="50c44-102">stackalloc（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="50c44-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="50c44-103">在不安全代码上下文中使用 `stackalloc` 关键字在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="50c44-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="50c44-104">备注</span><span class="sxs-lookup"><span data-stu-id="50c44-104">Remarks</span></span>  
 <span data-ttu-id="50c44-105">此关键字仅在局部变量初始值设定项中有效。</span><span class="sxs-lookup"><span data-stu-id="50c44-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="50c44-106">以下代码导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="50c44-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="50c44-107">由于涉及指针类型，因此 `stackalloc` 需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 上下文。</span><span class="sxs-lookup"><span data-stu-id="50c44-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="50c44-108">有关详细信息，请参阅[不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50c44-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="50c44-109">`stackalloc` 就像 C 运行时库中的 [_alloca](/cpp/c-runtime-library/reference/alloca)。</span><span class="sxs-lookup"><span data-stu-id="50c44-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="50c44-110">下面的示例计算并显示 Fibonacci 序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="50c44-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="50c44-111">每个数字是前两个数字的总和。</span><span class="sxs-lookup"><span data-stu-id="50c44-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="50c44-112">在此代码中，在堆栈上分配足够大的可包含 20 个 `int` 类型元素的内存块，而不是在堆上分配。</span><span class="sxs-lookup"><span data-stu-id="50c44-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="50c44-113">块的地址存储在指针 `fib` 中。</span><span class="sxs-lookup"><span data-stu-id="50c44-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="50c44-114">此内存不受垃圾回收的限制，因此不必对其进行单边锁定（使用 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)）。</span><span class="sxs-lookup"><span data-stu-id="50c44-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="50c44-115">内存块的生存期受到定义此内存块的方法的生存期的限制。</span><span class="sxs-lookup"><span data-stu-id="50c44-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="50c44-116">在方法返回之前，无法释放内存。</span><span class="sxs-lookup"><span data-stu-id="50c44-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50c44-117">示例</span><span class="sxs-lookup"><span data-stu-id="50c44-117">Example</span></span>  
 <span data-ttu-id="50c44-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="50c44-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="50c44-119">安全性</span><span class="sxs-lookup"><span data-stu-id="50c44-119">Security</span></span>  
 <span data-ttu-id="50c44-120">不安全代码的安全性低于安全替代项。</span><span class="sxs-lookup"><span data-stu-id="50c44-120">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="50c44-121">但是，使用 `stackalloc` 会自动启用公共语言运行时 (CLR) 中的缓冲区溢出检测功能。</span><span class="sxs-lookup"><span data-stu-id="50c44-121">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="50c44-122">如果检测到缓冲区溢出，则将尽快终止进程，以便将执行恶意代码的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="50c44-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="50c44-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="50c44-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50c44-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="50c44-124">See Also</span></span>  
 <span data-ttu-id="50c44-125">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="50c44-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="50c44-126">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="50c44-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="50c44-127">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="50c44-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="50c44-128">[运算符关键字](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="50c44-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="50c44-129">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="50c44-129">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

