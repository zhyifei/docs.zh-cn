---
title: 操作说明：通过指针访问成员 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: d0ca4a0b2189ee652ad1d9c2b63690306a651df4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635077"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="63671-102">如何：通过指针访问成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="63671-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="63671-103">若要访问不安全上下文中声明的结构成员，可使用成员访问运算符，如以下示例所示，其中 `p` 是包含成员 `x` 的 [struct](../../../csharp/language-reference/keywords/struct.md) 的指针。</span><span class="sxs-lookup"><span data-stu-id="63671-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="63671-104">示例</span><span class="sxs-lookup"><span data-stu-id="63671-104">Example</span></span>  
 <span data-ttu-id="63671-105">此示例中，对包含 `x` 和 `y` 两个坐标的 [struct](../../../csharp/language-reference/keywords/struct.md) `CoOrds` 进行了声明和实例化。</span><span class="sxs-lookup"><span data-stu-id="63671-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="63671-106">通过使用成员访问运算符 `->` 和实例 `home` 的指针，为 `x` 和 `y` 赋值。</span><span class="sxs-lookup"><span data-stu-id="63671-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63671-107">请注意，表达式 `p->x` 等效于表达式 `(*p).x`，使用这两个表达式中任何一个获得的结果相同。</span><span class="sxs-lookup"><span data-stu-id="63671-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="63671-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="63671-108">See also</span></span>

- [<span data-ttu-id="63671-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="63671-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="63671-110">指针类型</span><span class="sxs-lookup"><span data-stu-id="63671-110">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="63671-111">类型</span><span class="sxs-lookup"><span data-stu-id="63671-111">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="63671-112">unsafe</span><span class="sxs-lookup"><span data-stu-id="63671-112">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="63671-113">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="63671-113">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="63671-114">stackalloc</span><span class="sxs-lookup"><span data-stu-id="63671-114">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
