---
title: 指针转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: db809fa9e086351184adcac43d67f53e9456894c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43777375"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="96eb4-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="96eb4-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="96eb4-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="96eb4-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="96eb4-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="96eb4-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="96eb4-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="96eb4-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="96eb4-106">From</span><span class="sxs-lookup"><span data-stu-id="96eb4-106">From</span></span>|<span data-ttu-id="96eb4-107">到</span><span class="sxs-lookup"><span data-stu-id="96eb4-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="96eb4-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-108">Any pointer type</span></span>|<span data-ttu-id="96eb4-109">void\*</span><span class="sxs-lookup"><span data-stu-id="96eb4-109">void\*</span></span>|  
|<span data-ttu-id="96eb4-110">null</span><span class="sxs-lookup"><span data-stu-id="96eb4-110">null</span></span>|<span data-ttu-id="96eb4-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="96eb4-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="96eb4-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="96eb4-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="96eb4-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="96eb4-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="96eb4-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="96eb4-115">From</span><span class="sxs-lookup"><span data-stu-id="96eb4-115">From</span></span>|<span data-ttu-id="96eb4-116">到</span><span class="sxs-lookup"><span data-stu-id="96eb4-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="96eb4-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-117">Any pointer type</span></span>|<span data-ttu-id="96eb4-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-118">Any other pointer type</span></span>|  
|<span data-ttu-id="96eb4-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="96eb4-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="96eb4-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-120">Any pointer type</span></span>|  
|<span data-ttu-id="96eb4-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-121">Any pointer type</span></span>|<span data-ttu-id="96eb4-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="96eb4-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96eb4-123">示例</span><span class="sxs-lookup"><span data-stu-id="96eb4-123">Example</span></span>  
 <span data-ttu-id="96eb4-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="96eb4-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="96eb4-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="96eb4-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="96eb4-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="96eb4-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="96eb4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="96eb4-127">See Also</span></span>

- [<span data-ttu-id="96eb4-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="96eb4-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="96eb4-129">指针表达式</span><span class="sxs-lookup"><span data-stu-id="96eb4-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="96eb4-130">指针类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="96eb4-131">类型</span><span class="sxs-lookup"><span data-stu-id="96eb4-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="96eb4-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="96eb4-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="96eb4-133">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="96eb4-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="96eb4-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="96eb4-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
