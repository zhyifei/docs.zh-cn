---
title: "#<a name=\"else-c-reference\"></a>else（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#else'
helpviewer_keywords: '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c3468d35a6e45c06f46fe8671708ce01a3cc7b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="else-c-reference"></a><span data-ttu-id="d548b-102">#else（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d548b-102">#else (C# Reference)</span></span>
<span data-ttu-id="d548b-103">`#else` 允许创建复合条件指令，因此，如果先前 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或（可选）[#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 指令中的表达式没有一个为 `true`，则编译器将对介于 `#else` 和后续 `#endif` 之间的所有代码进行评估。</span><span class="sxs-lookup"><span data-stu-id="d548b-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d548b-104">备注</span><span class="sxs-lookup"><span data-stu-id="d548b-104">Remarks</span></span>  
 <span data-ttu-id="d548b-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 必须是 `#else` 之后的下一个预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="d548b-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="d548b-106">有关如何使用 `#else` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="d548b-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d548b-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d548b-107">See Also</span></span>  
 [<span data-ttu-id="d548b-108">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d548b-108">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d548b-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d548b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d548b-110">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="d548b-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
