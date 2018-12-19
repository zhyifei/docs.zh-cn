---
title: new 约束 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: de0798319d91032143cb806d6d39338c4f51ac8f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237839"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="c2aae-102">new 约束（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c2aae-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="c2aae-103">`new` 约束指定泛型类声明中的任何类型实参都必须有公共的无形参构造函数。</span><span class="sxs-lookup"><span data-stu-id="c2aae-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="c2aae-104">若要使用 new 约束，则该类型不能为抽象类型。</span><span class="sxs-lookup"><span data-stu-id="c2aae-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="c2aae-105">示例</span><span class="sxs-lookup"><span data-stu-id="c2aae-105">Example</span></span>

<span data-ttu-id="c2aae-106">当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="c2aae-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="c2aae-107">示例</span><span class="sxs-lookup"><span data-stu-id="c2aae-107">Example</span></span>

<span data-ttu-id="c2aae-108">当与其他约束一起使用时，`new()` 约束必须最后指定：</span><span class="sxs-lookup"><span data-stu-id="c2aae-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="c2aae-109">有关详细信息，请参阅[类型参数的约束](../../programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="c2aae-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2aae-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c2aae-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2aae-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2aae-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="c2aae-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c2aae-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="c2aae-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c2aae-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2aae-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c2aae-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2aae-115">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="c2aae-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="c2aae-116">泛型</span><span class="sxs-lookup"><span data-stu-id="c2aae-116">Generics</span></span>](../../programming-guide/generics/index.md)