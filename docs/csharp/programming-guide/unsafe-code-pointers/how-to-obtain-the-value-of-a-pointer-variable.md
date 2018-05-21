---
title: 如何：获取指针变量的值（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: c53026149837681235c6d1001707a25b9c8b40b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="8a592-102">如何：获取指针变量的值（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8a592-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="8a592-103">使用指针间接寻址运算符在指针指向的位置获取变量。</span><span class="sxs-lookup"><span data-stu-id="8a592-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="8a592-104">表达式采用以下形式，其中 `p` 为指针类型：</span><span class="sxs-lookup"><span data-stu-id="8a592-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="8a592-105">不能对指针类型外的任何类型的表达式使用一元间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="8a592-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="8a592-106">此外，不能将其应用于 [void](../../../csharp/language-reference/keywords/void.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="8a592-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="8a592-107">将间接寻址运算符应用于 [null](../../../csharp/language-reference/keywords/null.md) 指针时，结果具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="8a592-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a592-108">示例</span><span class="sxs-lookup"><span data-stu-id="8a592-108">Example</span></span>  
 <span data-ttu-id="8a592-109">在下面的示例中，`char` 类型的变量可通过使用另一类型的指针进行访问。</span><span class="sxs-lookup"><span data-stu-id="8a592-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="8a592-110">请注意，`theChar` 地址将随着每次运行有所不同，因为分配给变量的物理地址可变。</span><span class="sxs-lookup"><span data-stu-id="8a592-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 <span data-ttu-id="8a592-111">theChar 的值 = Z</span><span class="sxs-lookup"><span data-stu-id="8a592-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="8a592-112">theChar 的地址 = 12F718</span><span class="sxs-lookup"><span data-stu-id="8a592-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="8a592-113">pChar 的值 = Z </span><span class="sxs-lookup"><span data-stu-id="8a592-113">**Value of pChar = Z** </span></span>  
<span data-ttu-id="8a592-114">pInt 的值 = 90</span><span class="sxs-lookup"><span data-stu-id="8a592-114">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="8a592-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a592-115">See Also</span></span>  
 [<span data-ttu-id="8a592-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8a592-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8a592-117">指针表达式</span><span class="sxs-lookup"><span data-stu-id="8a592-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="8a592-118">指针类型</span><span class="sxs-lookup"><span data-stu-id="8a592-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="8a592-119">类型</span><span class="sxs-lookup"><span data-stu-id="8a592-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="8a592-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="8a592-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="8a592-121">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="8a592-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="8a592-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="8a592-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
