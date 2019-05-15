---
title: ':: 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 324f6711cdec478e5647b05d84c281f79e95f036
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452359"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="efd1d-102">:: 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="efd1d-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="efd1d-103">命名空间别名限定符（`::`）用于查找标识符。</span><span class="sxs-lookup"><span data-stu-id="efd1d-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="efd1d-104">它始终位于两个标识符之间，如本示例所示：</span><span class="sxs-lookup"><span data-stu-id="efd1d-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="efd1d-105">`::` 运算符也可以用于 using alias 指令：</span><span class="sxs-lookup"><span data-stu-id="efd1d-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="efd1d-106">备注</span><span class="sxs-lookup"><span data-stu-id="efd1d-106">Remarks</span></span>

<span data-ttu-id="efd1d-107">命名空间别名限定符可以为 `global`。</span><span class="sxs-lookup"><span data-stu-id="efd1d-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="efd1d-108">这将调用全局命名空间（而不是别名命名空间）中的查找。</span><span class="sxs-lookup"><span data-stu-id="efd1d-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="efd1d-109">更多相关信息</span><span class="sxs-lookup"><span data-stu-id="efd1d-109">For more information</span></span>

<span data-ttu-id="efd1d-110">有关如何使用 `::` 运算符的示例，请参阅以下部分：</span><span class="sxs-lookup"><span data-stu-id="efd1d-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="efd1d-111">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="efd1d-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="efd1d-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="efd1d-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="efd1d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd1d-113">See also</span></span>

- [<span data-ttu-id="efd1d-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="efd1d-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="efd1d-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="efd1d-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="efd1d-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="efd1d-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="efd1d-117">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="efd1d-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="efd1d-118">. 运算符</span><span class="sxs-lookup"><span data-stu-id="efd1d-118">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="efd1d-119">外部别名</span><span class="sxs-lookup"><span data-stu-id="efd1d-119">extern alias</span></span>](../keywords/extern-alias.md)