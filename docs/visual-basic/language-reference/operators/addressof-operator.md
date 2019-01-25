---
title: AddressOf 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 4f4f88551b6708ac3d0ee0f0f5bdcbdec1dfaaa9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721055"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="41092-102">AddressOf 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41092-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="41092-103">创建引用特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="41092-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41092-104">语法</span><span class="sxs-lookup"><span data-stu-id="41092-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="41092-105">部件</span><span class="sxs-lookup"><span data-stu-id="41092-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="41092-106">必需。</span><span class="sxs-lookup"><span data-stu-id="41092-106">Required.</span></span> <span data-ttu-id="41092-107">指定引用的新创建的过程委托的过程。</span><span class="sxs-lookup"><span data-stu-id="41092-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41092-108">备注</span><span class="sxs-lookup"><span data-stu-id="41092-108">Remarks</span></span>  
 <span data-ttu-id="41092-109">`AddressOf`运算符创建一个函数委托，指向由指定的函数`procedurename`。</span><span class="sxs-lookup"><span data-stu-id="41092-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="41092-110">当指定的过程是实例方法然后的函数委托引用在实例和方法。</span><span class="sxs-lookup"><span data-stu-id="41092-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="41092-111">然后，调用的函数委托时指定实例的指定的方法调用。</span><span class="sxs-lookup"><span data-stu-id="41092-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="41092-112">`AddressOf`运算符可以用作委托构造函数的操作数，或可在其中可以由编译器确定委托类型的上下文中。</span><span class="sxs-lookup"><span data-stu-id="41092-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41092-113">示例</span><span class="sxs-lookup"><span data-stu-id="41092-113">Example</span></span>  
 <span data-ttu-id="41092-114">此示例使用`AddressOf`运算符来指定一个委托来处理`Click`按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="41092-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="41092-115">示例</span><span class="sxs-lookup"><span data-stu-id="41092-115">Example</span></span>  
 <span data-ttu-id="41092-116">下面的示例使用`AddressOf`运算符来指定线程的启动函数。</span><span class="sxs-lookup"><span data-stu-id="41092-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="41092-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="41092-117">See also</span></span>
- [<span data-ttu-id="41092-118">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="41092-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="41092-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="41092-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="41092-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="41092-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="41092-121">委托</span><span class="sxs-lookup"><span data-stu-id="41092-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
