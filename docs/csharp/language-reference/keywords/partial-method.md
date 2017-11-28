---
title: "分部（方法）（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: partialmethod_CSharpKeyword
helpviewer_keywords: partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03962a59d5dbe0146cad9835f81d41c06914795b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="11176-102">分部（方法）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="11176-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="11176-103">分部方法在分部类型的一部分中定义了签名，并在该类型的另一部分中定义了实现。</span><span class="sxs-lookup"><span data-stu-id="11176-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="11176-104">通过分部方法，类设计器可提供与事件处理程序类似的方法挂钩，以便开发者决定是否实现。</span><span class="sxs-lookup"><span data-stu-id="11176-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="11176-105">如果开发者不提供实现，则编译器在编译时删除签名。</span><span class="sxs-lookup"><span data-stu-id="11176-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="11176-106">以下条件适用于分部方法：</span><span class="sxs-lookup"><span data-stu-id="11176-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="11176-107">分部类型各部分中的签名必须匹配。</span><span class="sxs-lookup"><span data-stu-id="11176-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="11176-108">方法必须返回 void。</span><span class="sxs-lookup"><span data-stu-id="11176-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="11176-109">不允许使用访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="11176-109">No access modifiers are allowed.</span></span> <span data-ttu-id="11176-110">分部方法是隐式专用的。</span><span class="sxs-lookup"><span data-stu-id="11176-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="11176-111">下列示例显示在分部类的两个部分中定义的分部方法：</span><span class="sxs-lookup"><span data-stu-id="11176-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="11176-112">有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="11176-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11176-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11176-113">See Also</span></span>  
 [<span data-ttu-id="11176-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="11176-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="11176-115">分部（类型）</span><span class="sxs-lookup"><span data-stu-id="11176-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
