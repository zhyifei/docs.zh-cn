---
title: "如何：递增和递减指针（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c8efc6d0844d867ad6eebccf3bb22c03e6d5020
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="8c03e-102">如何：递增和递减指针（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8c03e-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="8c03e-103">使用增量运算符 (`++`) 和减量运算符 (`--`)，通过 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) 更改 pointer-type* 类型的指针的指针位置。</span><span class="sxs-lookup"><span data-stu-id="8c03e-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="8c03e-104">增量和减量表达式的形式如下：</span><span class="sxs-lookup"><span data-stu-id="8c03e-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="8c03e-105">增量和减量运算符可应用于除 `void*` 类型以外的任何类型的指针。</span><span class="sxs-lookup"><span data-stu-id="8c03e-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="8c03e-106">对 `pointer-type` 类型的指针应用增量运算符的效果是向指针变量中包含的地址增加 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)。</span><span class="sxs-lookup"><span data-stu-id="8c03e-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="8c03e-107">对 `pointer-type` 类型的指针应用减量运算符的效果是从指针变量中包含的地址减去 `sizeof` (`pointer-type`)。</span><span class="sxs-lookup"><span data-stu-id="8c03e-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="8c03e-108">运算溢出指针范围时，不会产生异常，并且结果取决于实现。</span><span class="sxs-lookup"><span data-stu-id="8c03e-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c03e-109">示例</span><span class="sxs-lookup"><span data-stu-id="8c03e-109">Example</span></span>  
 <span data-ttu-id="8c03e-110">在此示例中，通过按 `int` 大小递增指针单步调试数组。</span><span class="sxs-lookup"><span data-stu-id="8c03e-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="8c03e-111">每一步都将显示数组元素的地址和内容。</span><span class="sxs-lookup"><span data-stu-id="8c03e-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="8c03e-112">Value:0 @ Address:12860272</span><span class="sxs-lookup"><span data-stu-id="8c03e-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="8c03e-113">Value:1 @ Address:12860276</span><span class="sxs-lookup"><span data-stu-id="8c03e-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="8c03e-114">Value:2 @ Address:12860280</span><span class="sxs-lookup"><span data-stu-id="8c03e-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="8c03e-115">Value:3 @ Address:12860284</span><span class="sxs-lookup"><span data-stu-id="8c03e-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="8c03e-116">Value:4 @ Address:12860288</span><span class="sxs-lookup"><span data-stu-id="8c03e-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="8c03e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c03e-117">See Also</span></span>  
 [<span data-ttu-id="8c03e-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8c03e-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8c03e-119">指针表达式</span><span class="sxs-lookup"><span data-stu-id="8c03e-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="8c03e-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8c03e-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="8c03e-121">操作指针</span><span class="sxs-lookup"><span data-stu-id="8c03e-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="8c03e-122">指针类型</span><span class="sxs-lookup"><span data-stu-id="8c03e-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="8c03e-123">类型</span><span class="sxs-lookup"><span data-stu-id="8c03e-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="8c03e-124">不安全</span><span class="sxs-lookup"><span data-stu-id="8c03e-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="8c03e-125">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="8c03e-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="8c03e-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="8c03e-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
