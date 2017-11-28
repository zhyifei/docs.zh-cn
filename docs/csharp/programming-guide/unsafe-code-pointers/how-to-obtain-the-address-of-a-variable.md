---
title: "如何：获取变量的地址（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="edb48-102">如何：获取变量的地址（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="edb48-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="edb48-103">若要获取计算结果为固定变量的一元表达式的地址，请使用 address-of 运算符：</span><span class="sxs-lookup"><span data-stu-id="edb48-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="edb48-104">address-of 运算符只适用于变量。</span><span class="sxs-lookup"><span data-stu-id="edb48-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="edb48-105">如果变量是可移动变量，则可以使用[固定语句](../../../csharp/language-reference/keywords/fixed-statement.md)临时固定变量，再获取其地址。</span><span class="sxs-lookup"><span data-stu-id="edb48-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="edb48-106">由你负责确保变量已初始化。</span><span class="sxs-lookup"><span data-stu-id="edb48-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="edb48-107">如果未初始化变量，编译器不会发出错误消息。</span><span class="sxs-lookup"><span data-stu-id="edb48-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="edb48-108">你也无法获取常量或值的地址。</span><span class="sxs-lookup"><span data-stu-id="edb48-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edb48-109">示例</span><span class="sxs-lookup"><span data-stu-id="edb48-109">Example</span></span>  
 <span data-ttu-id="edb48-110">在此示例中，已声明一个指向 `int` 和 `p` 的指针，并向其赋予了整型变量 `number` 的地址。</span><span class="sxs-lookup"><span data-stu-id="edb48-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="edb48-111">向 *p 赋值后导致初始化变量 `number`。</span><span class="sxs-lookup"><span data-stu-id="edb48-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="edb48-112">如果将此赋值语句作为注释，将删除变量 `number` 的初始化，但不会产生任何编译时错误。</span><span class="sxs-lookup"><span data-stu-id="edb48-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="edb48-113">注意使用[成员访问](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md)运算符 `->` 获取并显示指针中存储的地址。</span><span class="sxs-lookup"><span data-stu-id="edb48-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="edb48-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edb48-114">See Also</span></span>  
 [<span data-ttu-id="edb48-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="edb48-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="edb48-116">指针表达式</span><span class="sxs-lookup"><span data-stu-id="edb48-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="edb48-117">指针类型</span><span class="sxs-lookup"><span data-stu-id="edb48-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="edb48-118">类型</span><span class="sxs-lookup"><span data-stu-id="edb48-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="edb48-119">不安全</span><span class="sxs-lookup"><span data-stu-id="edb48-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="edb48-120">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="edb48-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="edb48-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="edb48-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
