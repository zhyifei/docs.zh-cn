---
title: 指针转换 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 308d5e0646eeb94012dbe18d46d6d33f67dfeaf5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698360"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="d79e5-102">指针转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d79e5-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="d79e5-103">下表显示预定义隐式指针转换。</span><span class="sxs-lookup"><span data-stu-id="d79e5-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="d79e5-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="d79e5-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="d79e5-105">隐式指针转换</span><span class="sxs-lookup"><span data-stu-id="d79e5-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="d79e5-106">From</span><span class="sxs-lookup"><span data-stu-id="d79e5-106">From</span></span>|<span data-ttu-id="d79e5-107">功能</span><span class="sxs-lookup"><span data-stu-id="d79e5-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d79e5-108">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-108">Any pointer type</span></span>|<span data-ttu-id="d79e5-109">void\*</span><span class="sxs-lookup"><span data-stu-id="d79e5-109">void\*</span></span>|  
|<span data-ttu-id="d79e5-110">null</span><span class="sxs-lookup"><span data-stu-id="d79e5-110">null</span></span>|<span data-ttu-id="d79e5-111">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="d79e5-112">显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。</span><span class="sxs-lookup"><span data-stu-id="d79e5-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="d79e5-113">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="d79e5-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="d79e5-114">显式指针转换</span><span class="sxs-lookup"><span data-stu-id="d79e5-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="d79e5-115">From</span><span class="sxs-lookup"><span data-stu-id="d79e5-115">From</span></span>|<span data-ttu-id="d79e5-116">功能</span><span class="sxs-lookup"><span data-stu-id="d79e5-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d79e5-117">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-117">Any pointer type</span></span>|<span data-ttu-id="d79e5-118">其他任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-118">Any other pointer type</span></span>|  
|<span data-ttu-id="d79e5-119">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="d79e5-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="d79e5-120">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-120">Any pointer type</span></span>|  
|<span data-ttu-id="d79e5-121">任何指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-121">Any pointer type</span></span>|<span data-ttu-id="d79e5-122">sbyte、byte、short、ushort、int、uint、long 或 ulong</span><span class="sxs-lookup"><span data-stu-id="d79e5-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d79e5-123">示例</span><span class="sxs-lookup"><span data-stu-id="d79e5-123">Example</span></span>  
 <span data-ttu-id="d79e5-124">在下面的示例中，`int` 的指针将转换为 `byte` 的指针。</span><span class="sxs-lookup"><span data-stu-id="d79e5-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="d79e5-125">请注意，指针指向变量的最低寻址字节。</span><span class="sxs-lookup"><span data-stu-id="d79e5-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="d79e5-126">如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。</span><span class="sxs-lookup"><span data-stu-id="d79e5-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d79e5-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d79e5-127">See also</span></span>

- [<span data-ttu-id="d79e5-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d79e5-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d79e5-129">指针类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="d79e5-130">引用类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="d79e5-131">值类型</span><span class="sxs-lookup"><span data-stu-id="d79e5-131">Value types</span></span>](../../language-reference/keywords/value-types.md)
- [<span data-ttu-id="d79e5-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="d79e5-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="d79e5-133">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="d79e5-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="d79e5-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d79e5-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
