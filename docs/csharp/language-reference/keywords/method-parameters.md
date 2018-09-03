---
title: 方法参数（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 446a5239fa1de8559dea50f7e8b8869aed0297c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389995"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="5813b-102">方法参数（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5813b-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="5813b-103">为不具有 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 的方法声明的参数会按值传递给调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5813b-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="5813b-104">可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。</span><span class="sxs-lookup"><span data-stu-id="5813b-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="5813b-105">可以通过使用方法参数关键字更改此行为。</span><span class="sxs-lookup"><span data-stu-id="5813b-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="5813b-106">本部分介绍声明方法参数时可以使用的关键字：</span><span class="sxs-lookup"><span data-stu-id="5813b-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="5813b-107">[params](../../../csharp/language-reference/keywords/params.md) 指定此参数采用可变数量的参数。</span><span class="sxs-lookup"><span data-stu-id="5813b-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="5813b-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) 指定此参数由引用传递，但只由调用方法读取。</span><span class="sxs-lookup"><span data-stu-id="5813b-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="5813b-109">[ref](../../../csharp/language-reference/keywords/ref.md) 指定此参数由引用传递，可能由调用方法读取或写入。</span><span class="sxs-lookup"><span data-stu-id="5813b-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="5813b-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 指定此参数由引用传递，由调用方法写入。</span><span class="sxs-lookup"><span data-stu-id="5813b-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5813b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5813b-111">See Also</span></span>

- [<span data-ttu-id="5813b-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5813b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5813b-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5813b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5813b-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5813b-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
