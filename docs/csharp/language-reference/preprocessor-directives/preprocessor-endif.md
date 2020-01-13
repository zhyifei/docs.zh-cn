---
title: '#endif - C# 参考'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712541"
---
# <a name="endif-c-reference"></a><span data-ttu-id="56b84-102">#endif（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="56b84-102">#endif (C# Reference)</span></span>
<span data-ttu-id="56b84-103">`#endif` 指定条件指令的末尾，以 [#if](./preprocessor-if.md) 指令开头。</span><span class="sxs-lookup"><span data-stu-id="56b84-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="56b84-104">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="56b84-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="56b84-105">备注</span><span class="sxs-lookup"><span data-stu-id="56b84-105">Remarks</span></span>  
 <span data-ttu-id="56b84-106">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="56b84-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="56b84-107">有关如何使用 `#endif` 的示例，请参阅 [#if](./preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="56b84-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b84-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="56b84-108">See also</span></span>

- [<span data-ttu-id="56b84-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="56b84-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56b84-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="56b84-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56b84-111">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="56b84-111">C# Preprocessor Directives</span></span>](./index.md)
