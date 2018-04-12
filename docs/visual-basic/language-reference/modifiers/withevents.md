---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68a58fd130c04f2ed0cb1f2e5b9250f6c85f120d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="9e6c0-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e6c0-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="9e6c0-103">指定一个或多个声明的成员变量引用可以引发事件的类的实例。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e6c0-104">备注</span><span class="sxs-lookup"><span data-stu-id="9e6c0-104">Remarks</span></span>  
 <span data-ttu-id="9e6c0-105">当使用定义变量`WithEvents`，你可以以声明方式指定一种方法处理使用的变量的事件`Handles`关键字。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="9e6c0-106">你可以使用`WithEvents`只能在类或模块级别。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="9e6c0-107">这意味着的声明上下文`WithEvents`变量必须是类或模块，而不能是源文件、 命名空间、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="9e6c0-108">不能使用`WithEvents`结构成员上。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="9e6c0-109">可以通过声明仅单个变量-不数组-与`WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9e6c0-110">规则</span><span class="sxs-lookup"><span data-stu-id="9e6c0-110">Rules</span></span>  
  
-   <span data-ttu-id="9e6c0-111">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="9e6c0-111">**Element Types.**</span></span> <span data-ttu-id="9e6c0-112">必须声明`WithEvents`变量是对象变量，以便它们可以接受类实例。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="9e6c0-113">但是，您無法宣告它们作为`Object`。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="9e6c0-114">你必须将它们声明为可引发事件的特定类。</span><span class="sxs-lookup"><span data-stu-id="9e6c0-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="9e6c0-115">`WithEvents`修饰符可用于在此上下文中： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9e6c0-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6c0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e6c0-116">See Also</span></span>  
 [<span data-ttu-id="9e6c0-117">Handles</span><span class="sxs-lookup"><span data-stu-id="9e6c0-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="9e6c0-118">关键字</span><span class="sxs-lookup"><span data-stu-id="9e6c0-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="9e6c0-119">事件</span><span class="sxs-lookup"><span data-stu-id="9e6c0-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
