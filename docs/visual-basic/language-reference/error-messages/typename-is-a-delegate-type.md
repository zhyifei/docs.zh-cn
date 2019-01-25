---
title: '&#39;&lt;typename&gt; &#39;是委托类型'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 6676328d0c1ea459f5934b5f9e2cb66580adad40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737197"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="dfc2c-102">&#39;&lt;typename&gt; &#39;是委托类型</span><span class="sxs-lookup"><span data-stu-id="dfc2c-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="dfc2c-103">\<类型名称 > 是委托类型。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="dfc2c-104">委托构造允许仅一个 AddressOf 表达式作为自变量列表。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="dfc2c-105">通常可以而不是委托构造使用一个 AddressOf 表达式。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="dfc2c-106">一个`New`子句创建委托类的实例为提供了无效的参数列表的委托构造函数。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="dfc2c-107">你可以提供只有一个`AddressOf`表达式创建新的委托实例时。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="dfc2c-108">如果不传递任何参数到委托构造函数中，如果传递多个自变量，或如果传递单个参数不是有效，可能发生此错误`AddressOf`表达式。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="dfc2c-109">**错误 ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="dfc2c-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dfc2c-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dfc2c-110">To correct this error</span></span>  
  
-   <span data-ttu-id="dfc2c-111">使用单个`AddressOf`中的委托类的参数列表中表达式`New`子句。</span><span class="sxs-lookup"><span data-stu-id="dfc2c-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc2c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfc2c-112">See also</span></span>
- [<span data-ttu-id="dfc2c-113">New 运算符</span><span class="sxs-lookup"><span data-stu-id="dfc2c-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="dfc2c-114">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="dfc2c-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="dfc2c-115">委托</span><span class="sxs-lookup"><span data-stu-id="dfc2c-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="dfc2c-116">如何：调用委托方法</span><span class="sxs-lookup"><span data-stu-id="dfc2c-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
