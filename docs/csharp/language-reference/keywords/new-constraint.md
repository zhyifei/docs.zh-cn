---
title: new 约束 - C# 参考
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: cd67aeb82d736b8941b0637494089723e7815505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713352"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="98eb8-102">new 约束（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="98eb8-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="98eb8-103">`new` 约束指定泛型类声明中的类型实参必须有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="98eb8-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="98eb8-104">若要使用 `new` 约束，则该类型不能为抽象类型。</span><span class="sxs-lookup"><span data-stu-id="98eb8-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="98eb8-105">当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="98eb8-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="98eb8-106">当与其他约束一起使用时，`new()` 约束必须最后指定：</span><span class="sxs-lookup"><span data-stu-id="98eb8-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="98eb8-107">有关详细信息，请参阅[类型参数的约束](../../programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="98eb8-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="98eb8-108">`new` 关键字还可用于[创建类型的实例](../operators/new-operator.md)或用作[成员声明修饰符](new-modifier.md)。</span><span class="sxs-lookup"><span data-stu-id="98eb8-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="98eb8-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="98eb8-109">C# language specification</span></span>

<span data-ttu-id="98eb8-110">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[类型参数约束](~/_csharplang/spec/classes.md#type-parameter-constraints)部分。</span><span class="sxs-lookup"><span data-stu-id="98eb8-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="98eb8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="98eb8-111">See also</span></span>

- [<span data-ttu-id="98eb8-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="98eb8-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="98eb8-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="98eb8-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="98eb8-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="98eb8-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="98eb8-115">泛型</span><span class="sxs-lookup"><span data-stu-id="98eb8-115">Generics</span></span>](../../programming-guide/generics/index.md)
