---
title: new 约束 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 2aa68bec13322e332bfe3841bc99403f72301183
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421796"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="8c38c-102">new 约束（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8c38c-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="8c38c-103">`new` 约束指定泛型类声明中的任何类型实参都必须有公共的无形参构造函数。</span><span class="sxs-lookup"><span data-stu-id="8c38c-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="8c38c-104">若要使用 new 约束，则该类型不能为抽象类型。</span><span class="sxs-lookup"><span data-stu-id="8c38c-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="8c38c-105">示例</span><span class="sxs-lookup"><span data-stu-id="8c38c-105">Example</span></span>

<span data-ttu-id="8c38c-106">当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="8c38c-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="8c38c-107">示例</span><span class="sxs-lookup"><span data-stu-id="8c38c-107">Example</span></span>

<span data-ttu-id="8c38c-108">当与其他约束一起使用时，`new()` 约束必须最后指定：</span><span class="sxs-lookup"><span data-stu-id="8c38c-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="8c38c-109">有关详细信息，请参阅[类型参数的约束](../../programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="8c38c-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8c38c-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8c38c-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8c38c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c38c-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="8c38c-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8c38c-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="8c38c-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8c38c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8c38c-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="8c38c-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8c38c-115">泛型</span><span class="sxs-lookup"><span data-stu-id="8c38c-115">Generics</span></span>](../../programming-guide/generics/index.md)
