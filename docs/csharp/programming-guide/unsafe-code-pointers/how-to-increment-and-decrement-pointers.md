---
title: 如何：递增和递减指针 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: f28fc4f86e4ff01f90bfd49714f38eee7040f9d1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242279"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="dc0b5-102">如何：递增和递减指针（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="dc0b5-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="dc0b5-103">使用增量运算符 (`++`) 和减量运算符 (`--`)，通过 `pointer-type*` 类型指针的 `sizeof(pointer-type)` 更改指针位置。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="dc0b5-104">增量和减量表达式的形式如下：</span><span class="sxs-lookup"><span data-stu-id="dc0b5-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="dc0b5-105">增量和减量运算符可应用于除 `void*` 类型以外的任何类型的指针。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="dc0b5-106">对 `pointer-type*` 类型的指针应用增量运算符的效果是向指针变量中包含的地址增加 `sizeof(pointer-type)`。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="dc0b5-107">对 `pointer-type*` 类型的指针应用减量运算符的效果是从指针变量中包含的地址减去 `sizeof(pointer-type)`。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="dc0b5-108">运算溢出指针范围时，不会产生异常，并且结果取决于实现。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc0b5-109">示例</span><span class="sxs-lookup"><span data-stu-id="dc0b5-109">Example</span></span>  
 <span data-ttu-id="dc0b5-110">在此示例中，通过按 `int` 大小递增指针单步调试数组。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="dc0b5-111">每一步都将显示数组元素的地址和内容。</span><span class="sxs-lookup"><span data-stu-id="dc0b5-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="dc0b5-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="dc0b5-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="dc0b5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc0b5-113">See also</span></span>

- [<span data-ttu-id="dc0b5-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dc0b5-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dc0b5-115">指针表达式</span><span class="sxs-lookup"><span data-stu-id="dc0b5-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="dc0b5-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="dc0b5-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="dc0b5-117">操作指针</span><span class="sxs-lookup"><span data-stu-id="dc0b5-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="dc0b5-118">指针类型</span><span class="sxs-lookup"><span data-stu-id="dc0b5-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="dc0b5-119">类型</span><span class="sxs-lookup"><span data-stu-id="dc0b5-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="dc0b5-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="dc0b5-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="dc0b5-121">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="dc0b5-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="dc0b5-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="dc0b5-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="dc0b5-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="dc0b5-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
