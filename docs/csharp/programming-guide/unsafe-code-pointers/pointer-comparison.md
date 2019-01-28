---
title: 指针比较 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: a2cbbabdad1d79c82bb5b3ec02a391727e552c98
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718632"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="f74b3-102">指针比较（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f74b3-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="f74b3-103">可以应用以下运算符比较任何类型的指针：</span><span class="sxs-lookup"><span data-stu-id="f74b3-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="f74b3-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="f74b3-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="f74b3-105">比较运算符比较两个操作数的地址，如同它们是无符号整数。</span><span class="sxs-lookup"><span data-stu-id="f74b3-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f74b3-106">示例</span><span class="sxs-lookup"><span data-stu-id="f74b3-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="f74b3-107">示例输出</span><span class="sxs-lookup"><span data-stu-id="f74b3-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="f74b3-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f74b3-108">See also</span></span>

- [<span data-ttu-id="f74b3-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f74b3-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f74b3-110">指针表达式</span><span class="sxs-lookup"><span data-stu-id="f74b3-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="f74b3-111">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f74b3-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="f74b3-112">操作指针</span><span class="sxs-lookup"><span data-stu-id="f74b3-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="f74b3-113">指针类型</span><span class="sxs-lookup"><span data-stu-id="f74b3-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="f74b3-114">类型</span><span class="sxs-lookup"><span data-stu-id="f74b3-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="f74b3-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="f74b3-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="f74b3-116">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="f74b3-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="f74b3-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="f74b3-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
