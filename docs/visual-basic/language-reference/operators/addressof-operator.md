---
title: "AddressOf 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e29b7ae2a6f6040cfc8c6e0cd0c9eb055a6694e9
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="11d61-102">AddressOf 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11d61-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="11d61-103">创建引用的特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="11d61-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d61-104">语法</span><span class="sxs-lookup"><span data-stu-id="11d61-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="11d61-105">部件</span><span class="sxs-lookup"><span data-stu-id="11d61-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="11d61-106">必需。</span><span class="sxs-lookup"><span data-stu-id="11d61-106">Required.</span></span> <span data-ttu-id="11d61-107">指定由新创建的过程委托引用的过程。</span><span class="sxs-lookup"><span data-stu-id="11d61-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11d61-108">备注</span><span class="sxs-lookup"><span data-stu-id="11d61-108">Remarks</span></span>  
 <span data-ttu-id="11d61-109">`AddressOf`运算符创建一个指向由指定的函数的函数委托`procedurename`。</span><span class="sxs-lookup"><span data-stu-id="11d61-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="11d61-110">当指定的过程是实例方法则此函数委托引用实例和方法。</span><span class="sxs-lookup"><span data-stu-id="11d61-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="11d61-111">然后，调用的函数委托时调用的指定实例的指定的方法。</span><span class="sxs-lookup"><span data-stu-id="11d61-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="11d61-112">`AddressOf`运算符可以用作委托构造函数的操作数，或者可在其中可以由编译器确定的委托类型的上下文中。</span><span class="sxs-lookup"><span data-stu-id="11d61-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11d61-113">示例</span><span class="sxs-lookup"><span data-stu-id="11d61-113">Example</span></span>  
 <span data-ttu-id="11d61-114">此示例使用`AddressOf`运算符来指定一个委托来处理`Click`按钮事件。</span><span class="sxs-lookup"><span data-stu-id="11d61-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 <span data-ttu-id="11d61-115">[!code-vb[VbVbalrDelegates #&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="11d61-115">[!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="11d61-116">示例</span><span class="sxs-lookup"><span data-stu-id="11d61-116">Example</span></span>  
 <span data-ttu-id="11d61-117">下面的示例使用`AddressOf`运算符来指定线程的启动函数。</span><span class="sxs-lookup"><span data-stu-id="11d61-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 <span data-ttu-id="11d61-118">[!code-vb[VbVbalrDelegates #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="11d61-118">[!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d61-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11d61-119">See Also</span></span>  
 <span data-ttu-id="11d61-120">[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="11d61-120">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="11d61-121"> [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="11d61-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="11d61-122"> [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="11d61-122"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="11d61-123"> [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="11d61-123"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>

