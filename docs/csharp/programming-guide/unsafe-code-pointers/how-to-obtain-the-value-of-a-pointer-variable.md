---
title: 如何：获取指针变量的值 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: b20642344b34b5426512ef64bde2ab33d55136b9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236630"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="08f78-102">如何：获取指针变量的值（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="08f78-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="08f78-103">使用指针间接寻址运算符在指针指向的位置获取变量。</span><span class="sxs-lookup"><span data-stu-id="08f78-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="08f78-104">表达式采用以下形式，其中 `p` 为指针类型：</span><span class="sxs-lookup"><span data-stu-id="08f78-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="08f78-105">不能对指针类型外的任何类型的表达式使用一元间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="08f78-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="08f78-106">此外，不能将其应用于 [void](../../../csharp/language-reference/keywords/void.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="08f78-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="08f78-107">将间接寻址运算符应用于 [null](../../../csharp/language-reference/keywords/null.md) 指针时，结果具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="08f78-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08f78-108">示例</span><span class="sxs-lookup"><span data-stu-id="08f78-108">Example</span></span>  
 <span data-ttu-id="08f78-109">在下面的示例中，`char` 类型的变量可通过使用另一类型的指针进行访问。</span><span class="sxs-lookup"><span data-stu-id="08f78-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="08f78-110">请注意，`theChar` 地址将随着每次运行有所不同，因为分配给变量的物理地址可变。</span><span class="sxs-lookup"><span data-stu-id="08f78-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
<span data-ttu-id="08f78-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="08f78-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span></span>

## <a name="see-also"></a><span data-ttu-id="08f78-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="08f78-112">See Also</span></span>

- [<span data-ttu-id="08f78-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="08f78-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="08f78-114">指针表达式</span><span class="sxs-lookup"><span data-stu-id="08f78-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="08f78-115">指针类型</span><span class="sxs-lookup"><span data-stu-id="08f78-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="08f78-116">类型</span><span class="sxs-lookup"><span data-stu-id="08f78-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="08f78-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="08f78-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="08f78-118">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="08f78-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="08f78-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="08f78-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
