---
title: 如何：获取变量的地址 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: 3e2eac468643b755c6db2d6055427baa7ce2b7a7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241770"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="5618c-102">如何：获取变量的地址（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5618c-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="5618c-103">若要获取计算结果为固定变量的一元表达式的地址，请使用 address-of 运算符 `&`：</span><span class="sxs-lookup"><span data-stu-id="5618c-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="5618c-104">address-of 运算符只适用于变量。</span><span class="sxs-lookup"><span data-stu-id="5618c-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="5618c-105">如果变量是可移动变量，则可以使用[固定语句](../../../csharp/language-reference/keywords/fixed-statement.md)临时固定变量，再获取其地址。</span><span class="sxs-lookup"><span data-stu-id="5618c-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="5618c-106">由你负责确保变量已初始化。</span><span class="sxs-lookup"><span data-stu-id="5618c-106">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="5618c-107">如果未初始化变量，编译器不会发出错误消息。</span><span class="sxs-lookup"><span data-stu-id="5618c-107">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="5618c-108">你也无法获取常量或值的地址。</span><span class="sxs-lookup"><span data-stu-id="5618c-108">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5618c-109">示例</span><span class="sxs-lookup"><span data-stu-id="5618c-109">Example</span></span>  
 <span data-ttu-id="5618c-110">在此示例中，已声明一个指向 `int` 和 `p` 的指针，并向其赋予了整型变量 `number` 的地址。</span><span class="sxs-lookup"><span data-stu-id="5618c-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="5618c-111">向 `*p` 赋值后导致初始化变量 `number`。</span><span class="sxs-lookup"><span data-stu-id="5618c-111">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="5618c-112">如果向此赋值语句添加注释，将删除变量 `number` 的初始化，但不会产生任何编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5618c-112">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="5618c-113">使用 [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项编译此示例。</span><span class="sxs-lookup"><span data-stu-id="5618c-113">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="5618c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5618c-114">See Also</span></span>

- [<span data-ttu-id="5618c-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5618c-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5618c-116">指针表达式</span><span class="sxs-lookup"><span data-stu-id="5618c-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="5618c-117">指针类型</span><span class="sxs-lookup"><span data-stu-id="5618c-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="5618c-118">类型</span><span class="sxs-lookup"><span data-stu-id="5618c-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="5618c-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="5618c-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="5618c-120">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="5618c-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="5618c-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5618c-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
