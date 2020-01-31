---
title: void - C# 参考
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742764"
---
# <a name="void-c-reference"></a><span data-ttu-id="3000c-102">void（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3000c-102">void (C# Reference)</span></span>

<span data-ttu-id="3000c-103">当用作一种方法的返回类型时，`void` 将指定该方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="3000c-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="3000c-104">方法的参数列表中不允许有 `void`。</span><span class="sxs-lookup"><span data-stu-id="3000c-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="3000c-105">无参数且不返回值的方法的声明方式如下：</span><span class="sxs-lookup"><span data-stu-id="3000c-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="3000c-106">`void` 还可用于在不安全的上下文中将指针声明为未知类型。</span><span class="sxs-lookup"><span data-stu-id="3000c-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="3000c-107">有关详细信息，请参阅[指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3000c-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="3000c-108">`void` 是 .NET Framework <xref:System.Void?displayProperty=nameWithType> 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="3000c-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3000c-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3000c-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3000c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3000c-110">See also</span></span>

- [<span data-ttu-id="3000c-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3000c-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3000c-112">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3000c-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3000c-113">引用类型</span><span class="sxs-lookup"><span data-stu-id="3000c-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="3000c-114">值类型</span><span class="sxs-lookup"><span data-stu-id="3000c-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="3000c-115">方法</span><span class="sxs-lookup"><span data-stu-id="3000c-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="3000c-116">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="3000c-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
