---
title: 指针转换 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 8fa1c1442d146c9d2fbdb2fa969b2e29d7ef765d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498302"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="86845-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="86845-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="86845-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="86845-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="86845-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="86845-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="86845-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="86845-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="86845-106">From</span><span class="sxs-lookup"><span data-stu-id="86845-106">From</span></span>|<span data-ttu-id="86845-107">到</span><span class="sxs-lookup"><span data-stu-id="86845-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="86845-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-108">Any pointer type</span></span>|<span data-ttu-id="86845-109">void\*</span><span class="sxs-lookup"><span data-stu-id="86845-109">void\*</span></span>|  
|<span data-ttu-id="86845-110">null</span><span class="sxs-lookup"><span data-stu-id="86845-110">null</span></span>|<span data-ttu-id="86845-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="86845-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="86845-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="86845-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="86845-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="86845-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="86845-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="86845-115">From</span><span class="sxs-lookup"><span data-stu-id="86845-115">From</span></span>|<span data-ttu-id="86845-116">到</span><span class="sxs-lookup"><span data-stu-id="86845-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="86845-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-117">Any pointer type</span></span>|<span data-ttu-id="86845-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-118">Any other pointer type</span></span>|  
|<span data-ttu-id="86845-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="86845-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="86845-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-120">Any pointer type</span></span>|  
|<span data-ttu-id="86845-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-121">Any pointer type</span></span>|<span data-ttu-id="86845-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="86845-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86845-123">示例</span><span class="sxs-lookup"><span data-stu-id="86845-123">Example</span></span>  
 <span data-ttu-id="86845-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="86845-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="86845-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="86845-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="86845-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="86845-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="86845-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="86845-127">See also</span></span>

- [<span data-ttu-id="86845-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="86845-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="86845-129">指针表达式</span><span class="sxs-lookup"><span data-stu-id="86845-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="86845-130">指针类型</span><span class="sxs-lookup"><span data-stu-id="86845-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="86845-131">类型</span><span class="sxs-lookup"><span data-stu-id="86845-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="86845-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="86845-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="86845-133">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="86845-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="86845-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="86845-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
