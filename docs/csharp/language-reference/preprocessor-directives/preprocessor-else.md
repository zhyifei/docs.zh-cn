---
title: '#else - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: eabbbb97c42af058c7426d4b72a53b41a96488ed
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237358"
---
# <a name="else-c-reference"></a><span data-ttu-id="8034b-102">#else（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8034b-102">#else (C# Reference)</span></span>
<span data-ttu-id="8034b-103">`#else` 允许创建复合条件指令，因此，如果先前 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或（可选）[#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 指令中的任何表达式的计算结果都不是 `true`，则编译器将对介于 `#else` 和后续 `#endif` 之间的所有代码进行求值。</span><span class="sxs-lookup"><span data-stu-id="8034b-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8034b-104">备注</span><span class="sxs-lookup"><span data-stu-id="8034b-104">Remarks</span></span>  
 <span data-ttu-id="8034b-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 必须是 `#else` 之后的下一个预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="8034b-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="8034b-106">有关如何使用 `#else` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="8034b-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8034b-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="8034b-107">See Also</span></span>

- [<span data-ttu-id="8034b-108">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8034b-108">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8034b-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8034b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8034b-110">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="8034b-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
