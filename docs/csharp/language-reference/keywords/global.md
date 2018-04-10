---
title: global（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ed2acc7384fbf3825a304888c58658d082858211
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="global-c-reference"></a><span data-ttu-id="ecb1a-102">global（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ecb1a-102">global (C# Reference)</span></span>
<span data-ttu-id="ecb1a-103">`global` 上下文关键字位于 [:: 运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) 之前时引用全局命名空间（即任何 C# 程序的默认命名空间，否则其未被命名）。</span><span class="sxs-lookup"><span data-stu-id="ecb1a-103">The `global` contextual keyword, when it comes before the [:: operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="ecb1a-104">有关详细信息，请参阅[如何：使用全局命名空间别名](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)。</span><span class="sxs-lookup"><span data-stu-id="ecb1a-104">For more information, see [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecb1a-105">示例</span><span class="sxs-lookup"><span data-stu-id="ecb1a-105">Example</span></span>  
 <span data-ttu-id="ecb1a-106">如下示例演示如何使用 `global` 上下文关键字来指定在全局命名空间中定义类 `TestApp`：</span><span class="sxs-lookup"><span data-stu-id="ecb1a-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/global_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ecb1a-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecb1a-107">See Also</span></span>  
 [<span data-ttu-id="ecb1a-108">命名空间</span><span class="sxs-lookup"><span data-stu-id="ecb1a-108">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
