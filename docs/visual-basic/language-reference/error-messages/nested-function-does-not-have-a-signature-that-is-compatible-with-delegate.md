---
title: 嵌套的函数没有与委托兼容的签名&#39; &lt;delegatename&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506402"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="7aa90-102">嵌套的函数没有与委托兼容的签名&#39; &lt;delegatename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7aa90-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="7aa90-103">Lambda 表达式已分配到具有兼容签名的委托。</span><span class="sxs-lookup"><span data-stu-id="7aa90-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="7aa90-104">例如，在下面的代码中，委托`Del`具有两个整数参数。</span><span class="sxs-lookup"><span data-stu-id="7aa90-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="7aa90-105">如果具有一个自变量的 lambda 表达式声明为类型会引发错误`Del`:</span><span class="sxs-lookup"><span data-stu-id="7aa90-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="7aa90-106">**错误 ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="7aa90-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7aa90-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7aa90-107">To correct this error</span></span>  
  
-   <span data-ttu-id="7aa90-108">调整委托定义或分配的 lambda 表达式，以便签名是兼容。</span><span class="sxs-lookup"><span data-stu-id="7aa90-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa90-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa90-109">See also</span></span>
- [<span data-ttu-id="7aa90-110">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="7aa90-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="7aa90-111">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="7aa90-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
