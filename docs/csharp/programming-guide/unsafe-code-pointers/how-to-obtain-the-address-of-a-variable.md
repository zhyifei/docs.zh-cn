---
title: 如何：获取变量的地址 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bc5776bc57096b88a71ff786915553ae9aa04b7b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635062"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="56d0f-102">如何：获取变量的地址（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="56d0f-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="56d0f-103">若要获取计算结果为固定变量的一元表达式的地址，请使用 address-of 运算符 `&`：</span><span class="sxs-lookup"><span data-stu-id="56d0f-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="56d0f-104">address-of 运算符只适用于变量。</span><span class="sxs-lookup"><span data-stu-id="56d0f-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="56d0f-105">如果变量是可移动变量，则可以使用[固定语句](../../../csharp/language-reference/keywords/fixed-statement.md)临时固定变量，再获取其地址。</span><span class="sxs-lookup"><span data-stu-id="56d0f-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span> <span data-ttu-id="56d0f-106">有关可移动变量的详细信息，请参阅[固定变量和可移动变量](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables)。</span><span class="sxs-lookup"><span data-stu-id="56d0f-106">For more information about moveable variables, see [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span></span> 
  
 <span data-ttu-id="56d0f-107">由你负责确保变量已初始化。</span><span class="sxs-lookup"><span data-stu-id="56d0f-107">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="56d0f-108">如果未初始化变量，编译器不会发出错误消息。</span><span class="sxs-lookup"><span data-stu-id="56d0f-108">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="56d0f-109">你也无法获取常量或值的地址。</span><span class="sxs-lookup"><span data-stu-id="56d0f-109">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56d0f-110">示例</span><span class="sxs-lookup"><span data-stu-id="56d0f-110">Example</span></span>  
 <span data-ttu-id="56d0f-111">在此示例中，已声明一个指向 `int` 和 `p` 的指针，并向其赋予了整型变量 `number` 的地址。</span><span class="sxs-lookup"><span data-stu-id="56d0f-111">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="56d0f-112">向 `*p` 赋值后导致初始化变量 `number`。</span><span class="sxs-lookup"><span data-stu-id="56d0f-112">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="56d0f-113">如果向此赋值语句添加注释，将删除变量 `number` 的初始化，但不会产生任何编译时错误。</span><span class="sxs-lookup"><span data-stu-id="56d0f-113">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="56d0f-114">使用 [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项编译此示例。</span><span class="sxs-lookup"><span data-stu-id="56d0f-114">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="56d0f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="56d0f-115">See also</span></span>

- [<span data-ttu-id="56d0f-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="56d0f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="56d0f-117">指针类型</span><span class="sxs-lookup"><span data-stu-id="56d0f-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="56d0f-118">类型</span><span class="sxs-lookup"><span data-stu-id="56d0f-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="56d0f-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="56d0f-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="56d0f-120">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="56d0f-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="56d0f-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="56d0f-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
