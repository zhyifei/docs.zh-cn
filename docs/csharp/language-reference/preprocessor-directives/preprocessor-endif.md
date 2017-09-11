---
title: "#<a name=\"endif-c-reference\"></a>endif（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#endif'
dev_langs:
- CSharp
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e4c37657a1ca81b7e5403e58123cf630a224b8ec
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="endif-c-reference"></a><span data-ttu-id="41729-102">#endif（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="41729-102">#endif (C# Reference)</span></span>
<span data-ttu-id="41729-103">`#endif` 指定条件指令的末尾，以 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令开头。</span><span class="sxs-lookup"><span data-stu-id="41729-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="41729-104">例如，</span><span class="sxs-lookup"><span data-stu-id="41729-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="41729-105">备注</span><span class="sxs-lookup"><span data-stu-id="41729-105">Remarks</span></span>  
 <span data-ttu-id="41729-106">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="41729-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="41729-107">有关如何使用 `#endif` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="41729-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41729-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41729-108">See Also</span></span>  
 <span data-ttu-id="41729-109">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="41729-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="41729-110">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="41729-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="41729-111">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="41729-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

