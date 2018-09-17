---
title: void（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 223db893dd42181c234d9a07c1a1c00af26f0c30
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593057"
---
# <a name="void-c-reference"></a><span data-ttu-id="1e599-102">void（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1e599-102">void (C# Reference)</span></span>
<span data-ttu-id="1e599-103">当用作一种方法的返回类型时，`void` 将指定该方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="1e599-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="1e599-104">方法的参数列表中不允许有 `void`。</span><span class="sxs-lookup"><span data-stu-id="1e599-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="1e599-105">无参数且不返回值的方法的声明方式如下：</span><span class="sxs-lookup"><span data-stu-id="1e599-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="1e599-106">`void` 还可用于在不安全的上下文中将指针声明为未知类型。</span><span class="sxs-lookup"><span data-stu-id="1e599-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="1e599-107">有关详细信息，请参阅[指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1e599-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="1e599-108">`void` 是 .NET Framework <xref:System.Void?displayProperty=nameWithType> 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="1e599-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1e599-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1e599-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1e599-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e599-110">See also</span></span>

- [<span data-ttu-id="1e599-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1e599-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1e599-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1e599-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1e599-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="1e599-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="1e599-114">引用类型</span><span class="sxs-lookup"><span data-stu-id="1e599-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="1e599-115">值类型</span><span class="sxs-lookup"><span data-stu-id="1e599-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="1e599-116">方法</span><span class="sxs-lookup"><span data-stu-id="1e599-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [<span data-ttu-id="1e599-117">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="1e599-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
