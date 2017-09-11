---
title: "其他控件结构 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
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
ms.openlocfilehash: 8f8bd57f193be0d7f410f7325355ffc47ab10e3f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="2cf86-102">其他控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cf86-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2cf86-103">提供帮助您的控制结构释放资源或减少您必须重复的对象引用的次数。</span><span class="sxs-lookup"><span data-stu-id="2cf86-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="2cf86-104">使用...结束使用构造</span><span class="sxs-lookup"><span data-stu-id="2cf86-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="2cf86-105">`Using...End Using`构造建立要在其中一个语句块使用的资源，例如 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="2cf86-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="2cf86-106">（可选） 可以获取具有资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="2cf86-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="2cf86-107">当您退出`Using`块中， [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ，以便它不用于其他代码以使用自动释放资源。</span><span class="sxs-lookup"><span data-stu-id="2cf86-107">When you exit the `Using` block, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="2cf86-108">资源必须是本地且可释放。</span><span class="sxs-lookup"><span data-stu-id="2cf86-108">The resource must be local and disposable.</span></span> <span data-ttu-id="2cf86-109">有关详细信息，请参阅[Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf86-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="2cf86-110">使用...以构造结尾</span><span class="sxs-lookup"><span data-stu-id="2cf86-110">With...End With Construction</span></span>  
 <span data-ttu-id="2cf86-111">`With...End With`构造允许您指定的对象引用一次，然后运行一系列访问其成员的语句。</span><span class="sxs-lookup"><span data-stu-id="2cf86-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="2cf86-112">这可以简化代码，并提高性能，因为[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]无需重新建立访问它的每个语句的引用。</span><span class="sxs-lookup"><span data-stu-id="2cf86-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="2cf86-113">有关详细信息，请参阅[与...使用语句结束](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf86-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf86-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf86-114">See Also</span></span>  
 <span data-ttu-id="2cf86-115">[控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="2cf86-115">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="2cf86-116"> [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="2cf86-116"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="2cf86-117"> [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="2cf86-117"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="2cf86-118"> [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="2cf86-118"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="2cf86-119"> [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2cf86-119"> [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md) </span></span>  
<span data-ttu-id="2cf86-120"> [With...End With 语句](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2cf86-120"> [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
