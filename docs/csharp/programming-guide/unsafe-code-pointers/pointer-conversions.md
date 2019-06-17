---
title: 指针转换 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 3cef2f2d2af2d285504daea14aa57c55b9e9a21b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833461"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="faccc-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="faccc-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="faccc-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="faccc-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="faccc-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="faccc-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="faccc-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="faccc-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="faccc-106">From</span><span class="sxs-lookup"><span data-stu-id="faccc-106">From</span></span>|<span data-ttu-id="faccc-107">功能</span><span class="sxs-lookup"><span data-stu-id="faccc-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="faccc-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-108">Any pointer type</span></span>|<span data-ttu-id="faccc-109">void\*</span><span class="sxs-lookup"><span data-stu-id="faccc-109">void\*</span></span>|  
|<span data-ttu-id="faccc-110">null</span><span class="sxs-lookup"><span data-stu-id="faccc-110">null</span></span>|<span data-ttu-id="faccc-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="faccc-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="faccc-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="faccc-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="faccc-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="faccc-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="faccc-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="faccc-115">From</span><span class="sxs-lookup"><span data-stu-id="faccc-115">From</span></span>|<span data-ttu-id="faccc-116">功能</span><span class="sxs-lookup"><span data-stu-id="faccc-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="faccc-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-117">Any pointer type</span></span>|<span data-ttu-id="faccc-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-118">Any other pointer type</span></span>|  
|<span data-ttu-id="faccc-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="faccc-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="faccc-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-120">Any pointer type</span></span>|  
|<span data-ttu-id="faccc-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-121">Any pointer type</span></span>|<span data-ttu-id="faccc-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="faccc-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="faccc-123">示例</span><span class="sxs-lookup"><span data-stu-id="faccc-123">Example</span></span>  
 <span data-ttu-id="faccc-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="faccc-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="faccc-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="faccc-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="faccc-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="faccc-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="faccc-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="faccc-127">See also</span></span>

- [<span data-ttu-id="faccc-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="faccc-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="faccc-129">指针类型</span><span class="sxs-lookup"><span data-stu-id="faccc-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="faccc-130">类型</span><span class="sxs-lookup"><span data-stu-id="faccc-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="faccc-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="faccc-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="faccc-132">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="faccc-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="faccc-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="faccc-133">stackalloc</span></span>](../../../csharp/language-reference/operators/stackalloc.md)
