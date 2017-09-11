---
title: "方法参数（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
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
ms.openlocfilehash: 4ba57e1a9e904befe11ff41796c987bd8f93b081
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="7e617-102">方法参数（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7e617-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="7e617-103">如果为不带 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 的方法声明参数，则该参数可以具有与之关联的值。</span><span class="sxs-lookup"><span data-stu-id="7e617-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="7e617-104">可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。</span><span class="sxs-lookup"><span data-stu-id="7e617-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="7e617-105">可以通过使用方法参数关键字更改此行为。</span><span class="sxs-lookup"><span data-stu-id="7e617-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="7e617-106">本部分介绍声明方法参数时可以使用的关键字：</span><span class="sxs-lookup"><span data-stu-id="7e617-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="7e617-107">params</span><span class="sxs-lookup"><span data-stu-id="7e617-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="7e617-108">ref</span><span class="sxs-lookup"><span data-stu-id="7e617-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="7e617-109">out</span><span class="sxs-lookup"><span data-stu-id="7e617-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e617-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e617-110">See Also</span></span>  
 <span data-ttu-id="7e617-111">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7e617-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7e617-112">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7e617-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7e617-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7e617-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

