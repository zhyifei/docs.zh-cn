---
title: 委托类“<classname>”没有 Invoke 方法，所以此类型的表达式不能作为方法调用的目标
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 3fe164d868ee7bde0e687e1d592f4d5a17565aea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321297"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="ad855-102">委托类的\<类名 > 有没有 Invoke 方法，所以此类型的表达式不能作为方法调用的目标</span><span class="sxs-lookup"><span data-stu-id="ad855-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="ad855-103">调用`Invoke`通过委托失败，因为`Invoke`上委托类未实现。</span><span class="sxs-lookup"><span data-stu-id="ad855-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="ad855-104">**错误 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="ad855-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ad855-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ad855-105">To correct this error</span></span>  
  
1. <span data-ttu-id="ad855-106">确保委托类的实例已经用`Dim`语句和到委托实例获得了一个过程`AddressOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="ad855-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="ad855-107">找到实现委托类的代码并确保它实现了`Invoke`过程。</span><span class="sxs-lookup"><span data-stu-id="ad855-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad855-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad855-108">See also</span></span>

- [<span data-ttu-id="ad855-109">委托</span><span class="sxs-lookup"><span data-stu-id="ad855-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ad855-110">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="ad855-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ad855-111">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="ad855-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ad855-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="ad855-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
