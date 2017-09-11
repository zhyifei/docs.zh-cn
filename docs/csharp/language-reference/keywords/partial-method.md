---
title: "分部（方法）（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a><span data-ttu-id="c057e-102">分部（方法）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c057e-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="c057e-103">分部方法在分部类型的一部分中定义了签名，并在该类型的另一部分中定义了实现。</span><span class="sxs-lookup"><span data-stu-id="c057e-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="c057e-104">通过分部方法，类设计器可提供与事件处理程序类似的方法挂钩，以便开发者决定是否实现。</span><span class="sxs-lookup"><span data-stu-id="c057e-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="c057e-105">如果开发者不提供实现，则编译器在编译时删除签名。</span><span class="sxs-lookup"><span data-stu-id="c057e-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="c057e-106">以下条件适用于分部方法：</span><span class="sxs-lookup"><span data-stu-id="c057e-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="c057e-107">分部类型各部分中的签名必须匹配。</span><span class="sxs-lookup"><span data-stu-id="c057e-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="c057e-108">方法必须返回 void。</span><span class="sxs-lookup"><span data-stu-id="c057e-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="c057e-109">不允许使用访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="c057e-109">No access modifiers are allowed.</span></span> <span data-ttu-id="c057e-110">分部方法是隐式专用的。</span><span class="sxs-lookup"><span data-stu-id="c057e-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="c057e-111">下列示例显示在分部类的两个部分中定义的分部方法：</span><span class="sxs-lookup"><span data-stu-id="c057e-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 <span data-ttu-id="c057e-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c057e-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span></span>  
  
 <span data-ttu-id="c057e-113">有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="c057e-113">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c057e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c057e-114">See Also</span></span>  
 <span data-ttu-id="c057e-115">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c057e-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="c057e-116">分部（类型）</span><span class="sxs-lookup"><span data-stu-id="c057e-116">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

