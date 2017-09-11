---
title: "如何：递增和递减指针（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="592e9-102">如何：递增和递减指针（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="592e9-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="592e9-103">使用增量运算符 (`++`) 和减量运算符 (`--`)，通过 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) 更改 pointer-type* 类型的指针的指针位置。</span><span class="sxs-lookup"><span data-stu-id="592e9-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="592e9-104">增量和减量表达式的形式如下：</span><span class="sxs-lookup"><span data-stu-id="592e9-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="592e9-105">增量和减量运算符可应用于除 `void*` 类型以外的任何类型的指针。</span><span class="sxs-lookup"><span data-stu-id="592e9-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="592e9-106">对 `pointer-type` 类型的指针应用增量运算符的效果是向指针变量中包含的地址增加 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)。</span><span class="sxs-lookup"><span data-stu-id="592e9-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="592e9-107">对 `pointer-type` 类型的指针应用减量运算符的效果是从指针变量中包含的地址减去 `sizeof` (`pointer-type`)。</span><span class="sxs-lookup"><span data-stu-id="592e9-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="592e9-108">运算溢出指针范围时，不会产生异常，并且结果取决于实现。</span><span class="sxs-lookup"><span data-stu-id="592e9-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="592e9-109">示例</span><span class="sxs-lookup"><span data-stu-id="592e9-109">Example</span></span>  
 <span data-ttu-id="592e9-110">在此示例中，通过按 `int` 大小递增指针单步调试数组。</span><span class="sxs-lookup"><span data-stu-id="592e9-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="592e9-111">每一步都将显示数组元素的地址和内容。</span><span class="sxs-lookup"><span data-stu-id="592e9-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="592e9-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="592e9-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="592e9-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="592e9-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="592e9-114">Value:0 @ Address:12860272</span><span class="sxs-lookup"><span data-stu-id="592e9-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="592e9-115">Value:1 @ Address:12860276</span><span class="sxs-lookup"><span data-stu-id="592e9-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="592e9-116">Value:2 @ Address:12860280</span><span class="sxs-lookup"><span data-stu-id="592e9-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="592e9-117">Value:3 @ Address:12860284</span><span class="sxs-lookup"><span data-stu-id="592e9-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="592e9-118">Value:4 @ Address:12860288</span><span class="sxs-lookup"><span data-stu-id="592e9-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="592e9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="592e9-119">See Also</span></span>  
 <span data-ttu-id="592e9-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="592e9-121">[指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="592e9-122">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="592e9-123">[操作指针](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="592e9-124">[指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="592e9-125">[类型](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="592e9-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="592e9-127">[fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="592e9-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="592e9-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="592e9-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

