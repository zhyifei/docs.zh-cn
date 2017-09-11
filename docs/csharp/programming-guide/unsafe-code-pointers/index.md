---
title: "不安全代码和指针（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75e11b34f0749270650e0e5b5a2a191a1b9e9f9a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="07d9f-102">不安全代码和指针（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="07d9f-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="07d9f-103">为了保持类型安全性，默认情况下，C# 不支持指针算法。</span><span class="sxs-lookup"><span data-stu-id="07d9f-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="07d9f-104">但是，通过使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字，可以定义可在其中使用指针的不安全上下文。</span><span class="sxs-lookup"><span data-stu-id="07d9f-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="07d9f-105">有关指针的详细信息，请参阅主题[指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)。</span><span class="sxs-lookup"><span data-stu-id="07d9f-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07d9f-106">在公共语言运行时 (CLR) 中，不安全代码是指无法验证的代码。</span><span class="sxs-lookup"><span data-stu-id="07d9f-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="07d9f-107">C# 中的不安全代码不一定是危险的；只是 CLR 无法验证该代码的安全性。</span><span class="sxs-lookup"><span data-stu-id="07d9f-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="07d9f-108">因此，CLR 将仅执行完全信任的程序集中的不安全代码。</span><span class="sxs-lookup"><span data-stu-id="07d9f-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="07d9f-109">如果你使用不安全代码，你应该负责确保代码不会引发安全风险或指针错误。</span><span class="sxs-lookup"><span data-stu-id="07d9f-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="07d9f-110">不安全代码概述</span><span class="sxs-lookup"><span data-stu-id="07d9f-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="07d9f-111">不安全代码具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="07d9f-111">Unsafe code has the following properties:</span></span>  
  
-   <span data-ttu-id="07d9f-112">可将方法、类型和代码块定义为不安全。</span><span class="sxs-lookup"><span data-stu-id="07d9f-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
-   <span data-ttu-id="07d9f-113">在某些情况下，通过移除数组绑定检查，不安全代码可提高应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="07d9f-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
-   <span data-ttu-id="07d9f-114">调用需要指针的本机函数时，需使用不安全代码。</span><span class="sxs-lookup"><span data-stu-id="07d9f-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
-   <span data-ttu-id="07d9f-115">使用不安全代码将引发安全风险和稳定性风险。</span><span class="sxs-lookup"><span data-stu-id="07d9f-115">Using unsafe code introduces security and stability risks.</span></span>  
  
-   <span data-ttu-id="07d9f-116">为使 C# 能够编译不安全代码，必须用 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="07d9f-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07d9f-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="07d9f-117">Related Sections</span></span>  
 <span data-ttu-id="07d9f-118">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="07d9f-118">For more information, see:</span></span>  
  
-   [<span data-ttu-id="07d9f-119">指针类型</span><span class="sxs-lookup"><span data-stu-id="07d9f-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [<span data-ttu-id="07d9f-120">固定大小的缓冲区</span><span class="sxs-lookup"><span data-stu-id="07d9f-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [<span data-ttu-id="07d9f-121">如何：使用指针复制字节数组</span><span class="sxs-lookup"><span data-stu-id="07d9f-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [<span data-ttu-id="07d9f-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="07d9f-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="07d9f-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="07d9f-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07d9f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d9f-124">See Also</span></span>  
 [<span data-ttu-id="07d9f-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="07d9f-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

