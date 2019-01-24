---
title: 如何使用指针访问数组元素 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 59765dbcad6c28cf2ad9f3df2052df19cafd08f1
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307274"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="3dd82-102">如何使用指针访问数组元素（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3dd82-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="3dd82-103">在不安全的上下文中，可通过指针元素访问来访问内存中的元素，如下方示例所示：</span><span class="sxs-lookup"><span data-stu-id="3dd82-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="3dd82-104">方括号中的表达式必须可隐式转换为 `int`、`uint`、`long` 或 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="3dd82-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="3dd82-105">`p[e]` 操作等效于 `*(p+e)`。</span><span class="sxs-lookup"><span data-stu-id="3dd82-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="3dd82-106">与 C 和 C++ 一样，指针元素访问不检查越界错误。</span><span class="sxs-lookup"><span data-stu-id="3dd82-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="3dd82-107">示例</span><span class="sxs-lookup"><span data-stu-id="3dd82-107">Example</span></span>

<span data-ttu-id="3dd82-108">此示例中，向字符数组 `charPointer` 分配了 123 个内存位置。</span><span class="sxs-lookup"><span data-stu-id="3dd82-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="3dd82-109">此数组用于显示两个 [for](../../../csharp/language-reference/keywords/for.md) 循环中的小写字母和大写字母。</span><span class="sxs-lookup"><span data-stu-id="3dd82-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="3dd82-110">请注意，表达式 `charPointer[i]` 等效于表达式 `*(charPointer + i)`，使用这两个表达式中任何一个获得的结果相同。</span><span class="sxs-lookup"><span data-stu-id="3dd82-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="3dd82-111">大写字母：</span><span class="sxs-lookup"><span data-stu-id="3dd82-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="3dd82-112">ABCDEFGHIJKLMNOPQRSTUVWXYZ</span><span class="sxs-lookup"><span data-stu-id="3dd82-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="3dd82-113">小写字母：</span><span class="sxs-lookup"><span data-stu-id="3dd82-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="3dd82-114">abcdefghijklmnopqrstuvwxyz</span><span class="sxs-lookup"><span data-stu-id="3dd82-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="3dd82-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd82-115">See also</span></span>

- [<span data-ttu-id="3dd82-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3dd82-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3dd82-117">指针表达式</span><span class="sxs-lookup"><span data-stu-id="3dd82-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="3dd82-118">指针类型</span><span class="sxs-lookup"><span data-stu-id="3dd82-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="3dd82-119">类型</span><span class="sxs-lookup"><span data-stu-id="3dd82-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="3dd82-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="3dd82-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="3dd82-121">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="3dd82-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="3dd82-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3dd82-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
