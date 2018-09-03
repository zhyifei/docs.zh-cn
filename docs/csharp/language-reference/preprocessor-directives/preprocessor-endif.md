---
title: '#endif（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: a652c1226f8f0c624ec8ebf0e665a4aa77ddf6f0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43420809"
---
# <a name="endif-c-reference"></a><span data-ttu-id="06123-102">#endif（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="06123-102">#endif (C# Reference)</span></span>
<span data-ttu-id="06123-103">`#endif` 指定条件指令的末尾，以 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令开头。</span><span class="sxs-lookup"><span data-stu-id="06123-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="06123-104">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="06123-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="06123-105">备注</span><span class="sxs-lookup"><span data-stu-id="06123-105">Remarks</span></span>  
 <span data-ttu-id="06123-106">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="06123-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="06123-107">有关如何使用 `#endif` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="06123-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06123-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="06123-108">See Also</span></span>

- [<span data-ttu-id="06123-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="06123-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="06123-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="06123-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="06123-111">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="06123-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
