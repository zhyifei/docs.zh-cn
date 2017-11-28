---
title: "方法参数（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 924e261cc876d2428e28ed0f490beb46b95f96e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="1e8e8-102">方法参数（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1e8e8-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="1e8e8-103">如果为不带 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 的方法声明参数，则该参数可以具有与之关联的值。</span><span class="sxs-lookup"><span data-stu-id="1e8e8-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="1e8e8-104">可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。</span><span class="sxs-lookup"><span data-stu-id="1e8e8-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="1e8e8-105">可以通过使用方法参数关键字更改此行为。</span><span class="sxs-lookup"><span data-stu-id="1e8e8-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="1e8e8-106">本部分介绍声明方法参数时可以使用的关键字：</span><span class="sxs-lookup"><span data-stu-id="1e8e8-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="1e8e8-107">params</span><span class="sxs-lookup"><span data-stu-id="1e8e8-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="1e8e8-108">ref</span><span class="sxs-lookup"><span data-stu-id="1e8e8-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="1e8e8-109">out</span><span class="sxs-lookup"><span data-stu-id="1e8e8-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e8e8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e8e8-110">See Also</span></span>  
 [<span data-ttu-id="1e8e8-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1e8e8-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1e8e8-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1e8e8-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1e8e8-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="1e8e8-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
