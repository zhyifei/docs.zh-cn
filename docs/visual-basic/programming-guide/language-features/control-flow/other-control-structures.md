---
title: 其他控件结构 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c42070ce2ea866e59e1b2e190f7c05e1ee7cc922
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819315"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="91063-102">其他控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91063-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="91063-103">Visual Basic 提供的控制结构，可帮助您释放资源，或减少必须重复的对象引用的次数。</span><span class="sxs-lookup"><span data-stu-id="91063-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="91063-104">使用...使用构造结束</span><span class="sxs-lookup"><span data-stu-id="91063-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="91063-105">`Using...End Using`构造建立可在其中一个语句块使用的 SQL 连接等资源。</span><span class="sxs-lookup"><span data-stu-id="91063-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="91063-106">您可以根据需要获取与资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="91063-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="91063-107">当您退出`Using`块中，Visual Basic 会自动释放的资源，这样就可用于其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="91063-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="91063-108">资源必须是本地的和可释放。</span><span class="sxs-lookup"><span data-stu-id="91063-108">The resource must be local and disposable.</span></span> <span data-ttu-id="91063-109">有关详细信息，请参阅 [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="91063-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="91063-110">使用...最终构造</span><span class="sxs-lookup"><span data-stu-id="91063-110">With...End With Construction</span></span>  
 <span data-ttu-id="91063-111">`With...End With`构造可以一次指定的对象引用，然后运行一系列访问其成员的语句。</span><span class="sxs-lookup"><span data-stu-id="91063-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="91063-112">这可以简化代码，并提高性能，因为 Visual Basic 不需要重新建立访问每个语句的引用。</span><span class="sxs-lookup"><span data-stu-id="91063-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="91063-113">有关详细信息，请参阅[使用...使用语句结束](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="91063-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91063-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="91063-114">See also</span></span>

- [<span data-ttu-id="91063-115">控制流</span><span class="sxs-lookup"><span data-stu-id="91063-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="91063-116">决策结构</span><span class="sxs-lookup"><span data-stu-id="91063-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="91063-117">循环结构</span><span class="sxs-lookup"><span data-stu-id="91063-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="91063-118">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="91063-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="91063-119">Using 语句</span><span class="sxs-lookup"><span data-stu-id="91063-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="91063-120">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="91063-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
