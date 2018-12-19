---
title: ::运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243473"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="907ac-102">::运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="907ac-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="907ac-103">命名空间别名限定符（`::`）用于查找标识符。</span><span class="sxs-lookup"><span data-stu-id="907ac-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="907ac-104">它始终位于两个标识符之间，如本示例所示：</span><span class="sxs-lookup"><span data-stu-id="907ac-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="907ac-105">`::` 运算符也可以用于 using alias 指令：</span><span class="sxs-lookup"><span data-stu-id="907ac-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="907ac-106">备注</span><span class="sxs-lookup"><span data-stu-id="907ac-106">Remarks</span></span>  
 <span data-ttu-id="907ac-107">命名空间别名限定符可以为 `global`。</span><span class="sxs-lookup"><span data-stu-id="907ac-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="907ac-108">这将调用全局命名空间（而不是别名命名空间）中的查找。</span><span class="sxs-lookup"><span data-stu-id="907ac-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="907ac-109">更多信息</span><span class="sxs-lookup"><span data-stu-id="907ac-109">For More Information</span></span>  
 <span data-ttu-id="907ac-110">有关如何使用 `::` 运算符的示例，请参阅以下部分：</span><span class="sxs-lookup"><span data-stu-id="907ac-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="907ac-111">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="907ac-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="907ac-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="907ac-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="907ac-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="907ac-113">See Also</span></span>

- [<span data-ttu-id="907ac-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="907ac-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="907ac-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="907ac-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="907ac-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="907ac-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="907ac-117">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="907ac-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="907ac-118">。运算符</span><span class="sxs-lookup"><span data-stu-id="907ac-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="907ac-119">外部别名</span><span class="sxs-lookup"><span data-stu-id="907ac-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
