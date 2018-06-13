---
title: 委托类&#39; &lt;classname&gt; &#39;有没有 Invoke 方法，因此此类型的表达式不能为方法调用的目标
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588825"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="1bbdb-102">委托类&#39; &lt;classname&gt; &#39;有没有 Invoke 方法，因此此类型的表达式不能为方法调用的目标</span><span class="sxs-lookup"><span data-stu-id="1bbdb-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="1bbdb-103">调用`Invoke`通过委托已失败，因为`Invoke`上委托类未实现。</span><span class="sxs-lookup"><span data-stu-id="1bbdb-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="1bbdb-104">**错误 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="1bbdb-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1bbdb-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1bbdb-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="1bbdb-106">确保委托类的实例，已创建具有`Dim`语句和是否委托实例分配了一个过程`AddressOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="1bbdb-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="1bbdb-107">找到实现委托类的代码，并确保它实现`Invoke`过程。</span><span class="sxs-lookup"><span data-stu-id="1bbdb-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbdb-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bbdb-108">See Also</span></span>  
 [<span data-ttu-id="1bbdb-109">委托</span><span class="sxs-lookup"><span data-stu-id="1bbdb-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="1bbdb-110">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="1bbdb-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="1bbdb-111">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="1bbdb-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="1bbdb-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="1bbdb-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
