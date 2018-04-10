---
title: ':: 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9945e-102">:: 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9945e-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="9945e-103">命名空间别名限定符（`::`）用于查找标识符。</span><span class="sxs-lookup"><span data-stu-id="9945e-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="9945e-104">它始终位于两个标识符之间，如本示例所示：</span><span class="sxs-lookup"><span data-stu-id="9945e-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="9945e-105">备注</span><span class="sxs-lookup"><span data-stu-id="9945e-105">Remarks</span></span>  
 <span data-ttu-id="9945e-106">命名空间别名限定符可以为 `global`。</span><span class="sxs-lookup"><span data-stu-id="9945e-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="9945e-107">这将调用全局命名空间（而不是别名命名空间）中的查找。</span><span class="sxs-lookup"><span data-stu-id="9945e-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9945e-108">更多信息</span><span class="sxs-lookup"><span data-stu-id="9945e-108">For More Information</span></span>  
 <span data-ttu-id="9945e-109">有关如何使用 `::` 运算符的示例，请参阅以下部分：</span><span class="sxs-lookup"><span data-stu-id="9945e-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="9945e-110">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="9945e-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9945e-111">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9945e-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9945e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9945e-112">See Also</span></span>  
 [<span data-ttu-id="9945e-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9945e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9945e-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9945e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9945e-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="9945e-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="9945e-116">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="9945e-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="9945e-117">。运算符</span><span class="sxs-lookup"><span data-stu-id="9945e-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="9945e-118">外部别名</span><span class="sxs-lookup"><span data-stu-id="9945e-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
