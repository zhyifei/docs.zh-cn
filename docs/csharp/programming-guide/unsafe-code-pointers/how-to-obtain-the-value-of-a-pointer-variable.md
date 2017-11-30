---
title: "如何：获取指针变量的值（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8065c10bec737789f13dcbafe147b50eedb9da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="9df58-102">如何：获取指针变量的值（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9df58-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="9df58-103">使用指针间接寻址运算符在指针指向的位置获取变量。</span><span class="sxs-lookup"><span data-stu-id="9df58-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="9df58-104">表达式采用以下形式，其中 `p` 为指针类型：</span><span class="sxs-lookup"><span data-stu-id="9df58-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="9df58-105">不能对指针类型外的任何类型的表达式使用一元间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="9df58-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="9df58-106">此外，不能将其应用于 [void](../../../csharp/language-reference/keywords/void.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="9df58-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="9df58-107">将间接寻址运算符应用于 [null](../../../csharp/language-reference/keywords/null.md) 指针时，结果具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="9df58-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9df58-108">示例</span><span class="sxs-lookup"><span data-stu-id="9df58-108">Example</span></span>  
 <span data-ttu-id="9df58-109">在下面的示例中，`char` 类型的变量可通过使用另一类型的指针进行访问。</span><span class="sxs-lookup"><span data-stu-id="9df58-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="9df58-110">请注意，`theChar` 地址将随着每次运行有所不同，因为分配给变量的物理地址可变。</span><span class="sxs-lookup"><span data-stu-id="9df58-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 <span data-ttu-id="9df58-111">**值的 theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="9df58-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="9df58-112">theChar 的地址 = 12F718</span><span class="sxs-lookup"><span data-stu-id="9df58-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="9df58-113">pChar 的值 = Z </span><span class="sxs-lookup"><span data-stu-id="9df58-113">**Value of pChar = Z** </span></span>  
<span data-ttu-id="9df58-114">pInt 的值 = 90</span><span class="sxs-lookup"><span data-stu-id="9df58-114">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="9df58-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9df58-115">See Also</span></span>  
 [<span data-ttu-id="9df58-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9df58-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9df58-117">指针表达式</span><span class="sxs-lookup"><span data-stu-id="9df58-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="9df58-118">指针类型</span><span class="sxs-lookup"><span data-stu-id="9df58-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="9df58-119">类型</span><span class="sxs-lookup"><span data-stu-id="9df58-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="9df58-120">不安全</span><span class="sxs-lookup"><span data-stu-id="9df58-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="9df58-121">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="9df58-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="9df58-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="9df58-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
