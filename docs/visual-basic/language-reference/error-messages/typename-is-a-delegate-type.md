---
title: "&lt;typename&gt;是委托类型 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
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
ms.openlocfilehash: 55532e269a7d6756157d324a2db14320df5d3f55
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="a2def-102">&lt;typename&gt;是委托类型</span><span class="sxs-lookup"><span data-stu-id="a2def-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="a2def-103">\<typename&1;> 是委托类型。</span><span class="sxs-lookup"><span data-stu-id="a2def-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="a2def-104">委托构造允许只能将单个 AddressOf 表达式作为参数列表。</span><span class="sxs-lookup"><span data-stu-id="a2def-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="a2def-105">通常 AddressOf 表达式可用来代替委托构造。</span><span class="sxs-lookup"><span data-stu-id="a2def-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="a2def-106">一个`New`子句创建委托类的实例为提供了无效的参数列表的委托构造函数。</span><span class="sxs-lookup"><span data-stu-id="a2def-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="a2def-107">您可以提供只有一个`AddressOf`表达式时创建新的委托实例。</span><span class="sxs-lookup"><span data-stu-id="a2def-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="a2def-108">如果您不传递任何参数给委托构造函数，如果传递的多个参数，或者如果传递单个参数，不是有效，则可能发生此错误`AddressOf`表达式。</span><span class="sxs-lookup"><span data-stu-id="a2def-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="a2def-109">**错误 ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="a2def-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2def-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a2def-110">To correct this error</span></span>  
  
-   <span data-ttu-id="a2def-111">使用单个`AddressOf`参数列表中的代理类中的表达式`New`子句。</span><span class="sxs-lookup"><span data-stu-id="a2def-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2def-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2def-112">See Also</span></span>  
 <span data-ttu-id="a2def-113">[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a2def-113">[New Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="a2def-114"> [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a2def-114"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="a2def-115"> [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="a2def-115"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="a2def-116"> [如何：调用委托方法](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="a2def-116"> [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
