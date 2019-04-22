---
title: 嵌套函数没有与委托“<delegatename>”兼容的签名。
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 04eae6d2c6d64e8a0f46ae3c2801a7eb6d893dca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822253"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="c3c23-102">嵌套的函数没有与委托兼容的签名\<委托名 >'</span><span class="sxs-lookup"><span data-stu-id="c3c23-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="c3c23-103">Lambda 表达式已分配到具有兼容签名的委托。</span><span class="sxs-lookup"><span data-stu-id="c3c23-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="c3c23-104">例如，在下面的代码中，委托`Del`具有两个整数参数。</span><span class="sxs-lookup"><span data-stu-id="c3c23-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="c3c23-105">如果具有一个自变量的 lambda 表达式声明为类型会引发错误`Del`:</span><span class="sxs-lookup"><span data-stu-id="c3c23-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="c3c23-106">**错误 ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="c3c23-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3c23-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c3c23-107">To correct this error</span></span>  
  
-   <span data-ttu-id="c3c23-108">调整委托定义或分配的 lambda 表达式，以便签名是兼容。</span><span class="sxs-lookup"><span data-stu-id="c3c23-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c23-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3c23-109">See also</span></span>

- [<span data-ttu-id="c3c23-110">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="c3c23-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="c3c23-111">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="c3c23-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
