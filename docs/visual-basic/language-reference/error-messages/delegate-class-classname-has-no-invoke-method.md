---
title: "委托类&lt;classname&gt;有没有 Invoke 方法，因此这种类型的表达式不能是方法调用的目标 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 54cd62bc2b4cafa89873728ba4e5b31c46f1aab1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="901b7-102">委托类&lt;classname&gt;有没有 Invoke 方法，因此这种类型的表达式不能是方法调用的目标</span><span class="sxs-lookup"><span data-stu-id="901b7-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="901b7-103">调用`Invoke`通过委托已失败，因为`Invoke`上委托类未实现。</span><span class="sxs-lookup"><span data-stu-id="901b7-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="901b7-104">**错误 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="901b7-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="901b7-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="901b7-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="901b7-106">确保委托类的实例已经用`Dim`到具有的委托实例分配了一个过程和语句`AddressOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="901b7-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="901b7-107">找到实现委托类的代码中，确保它实现了`Invoke`过程。</span><span class="sxs-lookup"><span data-stu-id="901b7-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901b7-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="901b7-108">See Also</span></span>  
 <span data-ttu-id="901b7-109">[委托](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="901b7-109">[Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="901b7-110"> [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="901b7-110"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="901b7-111"> [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="901b7-111"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="901b7-112"> [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="901b7-112"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>
