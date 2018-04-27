---
title: 其他控件结构 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e1ea44cf2f0405dc55f8df60fb842691e50a9a0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="3965e-102">其他控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3965e-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="3965e-103">Visual Basic 提供帮助你的控制结构释放资源，或减少你需要重复操作的对象引用的次数。</span><span class="sxs-lookup"><span data-stu-id="3965e-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="3965e-104">使用...结束使用构造</span><span class="sxs-lookup"><span data-stu-id="3965e-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="3965e-105">`Using...End Using`构造建立可在其中一个语句块使用的资源，例如 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="3965e-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="3965e-106">您可以根据需要获取的资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="3965e-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="3965e-107">当您退出`Using`块中，Visual Basic 会自动释放的资源，以便它不用于其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="3965e-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="3965e-108">资源必须是本地且可释放。</span><span class="sxs-lookup"><span data-stu-id="3965e-108">The resource must be local and disposable.</span></span> <span data-ttu-id="3965e-109">有关详细信息，请参阅 [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3965e-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="3965e-110">使用...以构造结尾</span><span class="sxs-lookup"><span data-stu-id="3965e-110">With...End With Construction</span></span>  
 <span data-ttu-id="3965e-111">`With...End With`构造，可以一次指定的对象引用，然后运行一系列访问其成员的语句。</span><span class="sxs-lookup"><span data-stu-id="3965e-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="3965e-112">这可以简化你的代码，并提高性能，因为 Visual Basic 不需要重新建立访问它的每个语句的引用。</span><span class="sxs-lookup"><span data-stu-id="3965e-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="3965e-113">有关详细信息，请参阅[与...使用语句结束](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3965e-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3965e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3965e-114">See Also</span></span>  
 [<span data-ttu-id="3965e-115">控制流</span><span class="sxs-lookup"><span data-stu-id="3965e-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="3965e-116">决策结构</span><span class="sxs-lookup"><span data-stu-id="3965e-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="3965e-117">循环结构</span><span class="sxs-lookup"><span data-stu-id="3965e-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="3965e-118">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="3965e-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="3965e-119">Using 语句</span><span class="sxs-lookup"><span data-stu-id="3965e-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="3965e-120">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="3965e-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
