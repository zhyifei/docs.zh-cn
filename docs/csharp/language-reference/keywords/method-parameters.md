---
title: "方法参数（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b20d2d233350cfb9de55cbd07e722082ec311597
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="6b136-102">方法参数（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6b136-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="6b136-103">为不具有 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 的方法声明的参数会按值传递给调用的方法。</span><span class="sxs-lookup"><span data-stu-id="6b136-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="6b136-104">可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。</span><span class="sxs-lookup"><span data-stu-id="6b136-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="6b136-105">可以通过使用方法参数关键字更改此行为。</span><span class="sxs-lookup"><span data-stu-id="6b136-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="6b136-106">本部分介绍声明方法参数时可以使用的关键字：</span><span class="sxs-lookup"><span data-stu-id="6b136-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="6b136-107">params</span><span class="sxs-lookup"><span data-stu-id="6b136-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="6b136-108">in</span><span class="sxs-lookup"><span data-stu-id="6b136-108">in</span></span>](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
  
-   [<span data-ttu-id="6b136-109">ref</span><span class="sxs-lookup"><span data-stu-id="6b136-109">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="6b136-110">out</span><span class="sxs-lookup"><span data-stu-id="6b136-110">out</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b136-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b136-111">See Also</span></span>  
 [<span data-ttu-id="6b136-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6b136-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6b136-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6b136-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6b136-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="6b136-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
