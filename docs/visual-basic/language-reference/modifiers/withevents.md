---
title: "WithEvents (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
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
ms.openlocfilehash: b956f8f0d6f0a2fd9f41c5df6d6c82b43fa09018
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="withevents-visual-basic"></a><span data-ttu-id="06a13-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06a13-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="06a13-103">指定一个或多个声明的成员变量指可以引发事件的类的实例。</span><span class="sxs-lookup"><span data-stu-id="06a13-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06a13-104">备注</span><span class="sxs-lookup"><span data-stu-id="06a13-104">Remarks</span></span>  
 <span data-ttu-id="06a13-105">当使用定义一个变量`WithEvents`，您可以以声明方式指定一种方法，可使用的变量的事件处理`Handles`关键字。</span><span class="sxs-lookup"><span data-stu-id="06a13-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="06a13-106">您可以使用`WithEvents`只能在类或模块级别。</span><span class="sxs-lookup"><span data-stu-id="06a13-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="06a13-107">这意味着的声明上下文`WithEvents`变量必须是类或模块，且不能为源文件、 命名空间、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="06a13-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="06a13-108">不能使用`WithEvents`对结构成员。</span><span class="sxs-lookup"><span data-stu-id="06a13-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="06a13-109">您可以声明只有单个变量-不数组 — 与`WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="06a13-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="06a13-110">规则</span><span class="sxs-lookup"><span data-stu-id="06a13-110">Rules</span></span>  
  
-   <span data-ttu-id="06a13-111">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="06a13-111">**Element Types.**</span></span> <span data-ttu-id="06a13-112">您必须声明`WithEvents`变量为对象变量，以使它们可以接受类实例。</span><span class="sxs-lookup"><span data-stu-id="06a13-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="06a13-113">但是，您无法声明这些变量作为`Object`。</span><span class="sxs-lookup"><span data-stu-id="06a13-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="06a13-114">您必须将它们声明为可引发事件的特定类。</span><span class="sxs-lookup"><span data-stu-id="06a13-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="06a13-115">`WithEvents`修饰符可用于在此上下文中︰ [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="06a13-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a13-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06a13-116">See Also</span></span>  
 <span data-ttu-id="06a13-117">[句柄](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="06a13-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="06a13-118"> [关键字](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="06a13-118"> [Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="06a13-119"> [事件](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="06a13-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
