---
title: "指针转换（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
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
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="b002d-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b002d-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="b002d-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="b002d-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="b002d-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="b002d-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="b002d-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="b002d-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="b002d-106">From</span><span class="sxs-lookup"><span data-stu-id="b002d-106">From</span></span>|<span data-ttu-id="b002d-107">到</span><span class="sxs-lookup"><span data-stu-id="b002d-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="b002d-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-108">Any pointer type</span></span>|<span data-ttu-id="b002d-109">void*</span><span class="sxs-lookup"><span data-stu-id="b002d-109">void*</span></span>|  
|<span data-ttu-id="b002d-110">null</span><span class="sxs-lookup"><span data-stu-id="b002d-110">null</span></span>|<span data-ttu-id="b002d-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="b002d-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="b002d-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="b002d-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="b002d-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="b002d-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="b002d-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="b002d-115">From</span><span class="sxs-lookup"><span data-stu-id="b002d-115">From</span></span>|<span data-ttu-id="b002d-116">到</span><span class="sxs-lookup"><span data-stu-id="b002d-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="b002d-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-117">Any pointer type</span></span>|<span data-ttu-id="b002d-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-118">Any other pointer type</span></span>|  
|<span data-ttu-id="b002d-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="b002d-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="b002d-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-120">Any pointer type</span></span>|  
|<span data-ttu-id="b002d-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="b002d-121">Any pointer type</span></span>|<span data-ttu-id="b002d-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="b002d-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b002d-123">示例</span><span class="sxs-lookup"><span data-stu-id="b002d-123">Example</span></span>  
 <span data-ttu-id="b002d-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="b002d-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="b002d-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="b002d-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="b002d-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="b002d-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="b002d-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b002d-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="b002d-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b002d-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b002d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b002d-129">See Also</span></span>  
 <span data-ttu-id="b002d-130">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b002d-131">[指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="b002d-132">[指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="b002d-133">[类型](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="b002d-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="b002d-135">[fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b002d-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="b002d-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b002d-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

