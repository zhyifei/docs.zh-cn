---
title: "如何：获取指针变量的值（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="01619-102">如何：获取指针变量的值（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="01619-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="01619-103">使用指针间接寻址运算符在指针指向的位置获取变量。</span><span class="sxs-lookup"><span data-stu-id="01619-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="01619-104">表达式采用以下形式，其中 `p` 为指针类型：</span><span class="sxs-lookup"><span data-stu-id="01619-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="01619-105">不能对指针类型外的任何类型的表达式使用一元间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="01619-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="01619-106">此外，不能将其应用于 [void](../../../csharp/language-reference/keywords/void.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="01619-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="01619-107">将间接寻址运算符应用于 [null](../../../csharp/language-reference/keywords/null.md) 指针时，结果具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="01619-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01619-108">示例</span><span class="sxs-lookup"><span data-stu-id="01619-108">Example</span></span>  
 <span data-ttu-id="01619-109">在下面的示例中，`char` 类型的变量可通过使用另一类型的指针进行访问。</span><span class="sxs-lookup"><span data-stu-id="01619-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="01619-110">请注意，`theChar` 地址将随着每次运行有所不同，因为分配给变量的物理地址可变。</span><span class="sxs-lookup"><span data-stu-id="01619-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="01619-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="01619-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="01619-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="01619-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="01619-113">theChar 的值 = Z </span><span class="sxs-lookup"><span data-stu-id="01619-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="01619-114">theChar 的地址 = 12F718</span><span class="sxs-lookup"><span data-stu-id="01619-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="01619-115">pChar 的值 = Z </span><span class="sxs-lookup"><span data-stu-id="01619-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="01619-116">pInt 的值 = 90</span><span class="sxs-lookup"><span data-stu-id="01619-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="01619-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01619-117">See Also</span></span>  
 <span data-ttu-id="01619-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="01619-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="01619-119">[指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="01619-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="01619-120">[指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="01619-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="01619-121">[类型](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="01619-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="01619-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="01619-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="01619-123">[fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="01619-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="01619-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="01619-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

