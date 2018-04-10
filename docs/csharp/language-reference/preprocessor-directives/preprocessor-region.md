---
title: '#region（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce4a8ac79c4687280e28618d8863d16cd193a3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="region-c-reference"></a><span data-ttu-id="591d6-102">#region（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="591d6-102">#region (C# Reference)</span></span>
<span data-ttu-id="591d6-103">利用 `#region`，可以指定在使用 Visual Studio Code 编辑器的[大纲功能](/visualstudio/ide/outlining)时可展开或折叠的代码块。</span><span class="sxs-lookup"><span data-stu-id="591d6-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="591d6-104">在较长的代码文件中，能够折叠或隐藏一个或多个区域会十分便利，这样，可将精力集中于当前处理的文件部分。</span><span class="sxs-lookup"><span data-stu-id="591d6-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="591d6-105">下面的示例演示如何定义区域：</span><span class="sxs-lookup"><span data-stu-id="591d6-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="591d6-106">备注</span><span class="sxs-lookup"><span data-stu-id="591d6-106">Remarks</span></span>  
 <span data-ttu-id="591d6-107">`#region` 块必须通过 [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) 指令终止。</span><span class="sxs-lookup"><span data-stu-id="591d6-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="591d6-108">`#region` 块不能与 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 块重叠。</span><span class="sxs-lookup"><span data-stu-id="591d6-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="591d6-109">但是，可以将 `#region` 块嵌套在 `#if` 块内，或将 `#if` 块嵌套在 `#region` 块内。</span><span class="sxs-lookup"><span data-stu-id="591d6-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591d6-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="591d6-110">See Also</span></span>  
 [<span data-ttu-id="591d6-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="591d6-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="591d6-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="591d6-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="591d6-113">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="591d6-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
