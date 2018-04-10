---
title: new 约束（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="c6a26-102">new 约束（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c6a26-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="c6a26-103">`new` 约束指定泛型类声明中的任何类型实参都必须有公共的无形参构造函数。</span><span class="sxs-lookup"><span data-stu-id="c6a26-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="c6a26-104">若要使用 new 约束，则该类型不能为抽象类型。</span><span class="sxs-lookup"><span data-stu-id="c6a26-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6a26-105">示例</span><span class="sxs-lookup"><span data-stu-id="c6a26-105">Example</span></span>  
 <span data-ttu-id="c6a26-106">当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="c6a26-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="c6a26-107">示例</span><span class="sxs-lookup"><span data-stu-id="c6a26-107">Example</span></span>  
 <span data-ttu-id="c6a26-108">当与其他约束一起使用时，`new()` 约束必须最后指定：</span><span class="sxs-lookup"><span data-stu-id="c6a26-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="c6a26-109">有关详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a26-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c6a26-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c6a26-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6a26-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a26-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="c6a26-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c6a26-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c6a26-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c6a26-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c6a26-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c6a26-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c6a26-115">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="c6a26-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="c6a26-116">泛型</span><span class="sxs-lookup"><span data-stu-id="c6a26-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
