---
title: "AddressOf 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="51b64-102">AddressOf 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51b64-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="51b64-103">创建引用特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="51b64-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b64-104">语法</span><span class="sxs-lookup"><span data-stu-id="51b64-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="51b64-105">部件</span><span class="sxs-lookup"><span data-stu-id="51b64-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="51b64-106">必需。</span><span class="sxs-lookup"><span data-stu-id="51b64-106">Required.</span></span> <span data-ttu-id="51b64-107">指定要由新创建的过程委托引用的过程。</span><span class="sxs-lookup"><span data-stu-id="51b64-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51b64-108">备注</span><span class="sxs-lookup"><span data-stu-id="51b64-108">Remarks</span></span>  
 <span data-ttu-id="51b64-109">`AddressOf`运算符创建一个函数委托，指向由指定的函数`procedurename`。</span><span class="sxs-lookup"><span data-stu-id="51b64-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="51b64-110">当指定的过程是实例方法然后的函数委托引用实例和方法。</span><span class="sxs-lookup"><span data-stu-id="51b64-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="51b64-111">然后，调用的函数委托时调用的指定实例的指定的方法。</span><span class="sxs-lookup"><span data-stu-id="51b64-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="51b64-112">`AddressOf`运算符可以用作委托构造函数的操作数，或它可在其中可以由编译器确定委托的类型的上下文中。</span><span class="sxs-lookup"><span data-stu-id="51b64-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51b64-113">示例</span><span class="sxs-lookup"><span data-stu-id="51b64-113">Example</span></span>  
 <span data-ttu-id="51b64-114">此示例使用`AddressOf`运算符指定一个委托来处理`Click`的按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="51b64-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="51b64-115">示例</span><span class="sxs-lookup"><span data-stu-id="51b64-115">Example</span></span>  
 <span data-ttu-id="51b64-116">下面的示例使用`AddressOf`运算符指定线程的启动函数。</span><span class="sxs-lookup"><span data-stu-id="51b64-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="51b64-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51b64-117">See Also</span></span>  
 [<span data-ttu-id="51b64-118">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="51b64-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="51b64-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="51b64-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="51b64-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="51b64-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="51b64-121">委托</span><span class="sxs-lookup"><span data-stu-id="51b64-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
