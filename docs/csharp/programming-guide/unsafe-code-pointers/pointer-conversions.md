---
title: 指针转换 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 81b2110e6a571e174693fd272d1c6b4bf44dbae3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588217"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="51281-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="51281-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="51281-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="51281-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="51281-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="51281-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="51281-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="51281-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="51281-106">From</span><span class="sxs-lookup"><span data-stu-id="51281-106">From</span></span>|<span data-ttu-id="51281-107">功能</span><span class="sxs-lookup"><span data-stu-id="51281-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="51281-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-108">Any pointer type</span></span>|<span data-ttu-id="51281-109">void\*</span><span class="sxs-lookup"><span data-stu-id="51281-109">void\*</span></span>|  
|<span data-ttu-id="51281-110">null</span><span class="sxs-lookup"><span data-stu-id="51281-110">null</span></span>|<span data-ttu-id="51281-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="51281-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="51281-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="51281-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="51281-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="51281-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="51281-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="51281-115">From</span><span class="sxs-lookup"><span data-stu-id="51281-115">From</span></span>|<span data-ttu-id="51281-116">功能</span><span class="sxs-lookup"><span data-stu-id="51281-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="51281-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-117">Any pointer type</span></span>|<span data-ttu-id="51281-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-118">Any other pointer type</span></span>|  
|<span data-ttu-id="51281-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="51281-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="51281-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-120">Any pointer type</span></span>|  
|<span data-ttu-id="51281-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-121">Any pointer type</span></span>|<span data-ttu-id="51281-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="51281-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51281-123">示例</span><span class="sxs-lookup"><span data-stu-id="51281-123">Example</span></span>  
 <span data-ttu-id="51281-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="51281-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="51281-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="51281-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="51281-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="51281-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="51281-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="51281-127">See also</span></span>

- [<span data-ttu-id="51281-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="51281-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="51281-129">指针类型</span><span class="sxs-lookup"><span data-stu-id="51281-129">Pointer types</span></span>](./pointer-types.md)
- [<span data-ttu-id="51281-130">类型</span><span class="sxs-lookup"><span data-stu-id="51281-130">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="51281-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="51281-131">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="51281-132">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="51281-132">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="51281-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="51281-133">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
