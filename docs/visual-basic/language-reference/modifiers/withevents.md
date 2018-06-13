---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596003"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="5ba21-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ba21-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="5ba21-103">指定一个或多个声明的成员变量引用可以引发事件的类的实例。</span><span class="sxs-lookup"><span data-stu-id="5ba21-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ba21-104">备注</span><span class="sxs-lookup"><span data-stu-id="5ba21-104">Remarks</span></span>  
 <span data-ttu-id="5ba21-105">当使用定义变量`WithEvents`，你可以以声明方式指定一种方法处理使用的变量的事件`Handles`关键字。</span><span class="sxs-lookup"><span data-stu-id="5ba21-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="5ba21-106">你可以使用`WithEvents`只能在类或模块级别。</span><span class="sxs-lookup"><span data-stu-id="5ba21-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="5ba21-107">这意味着的声明上下文`WithEvents`变量必须是类或模块，而不能是源文件、 命名空间、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="5ba21-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="5ba21-108">不能使用`WithEvents`结构成员上。</span><span class="sxs-lookup"><span data-stu-id="5ba21-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="5ba21-109">可以通过声明仅单个变量-不数组-与`WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="5ba21-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5ba21-110">规则</span><span class="sxs-lookup"><span data-stu-id="5ba21-110">Rules</span></span>  
  
-   <span data-ttu-id="5ba21-111">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="5ba21-111">**Element Types.**</span></span> <span data-ttu-id="5ba21-112">必须声明`WithEvents`变量是对象变量，以便它们可以接受类实例。</span><span class="sxs-lookup"><span data-stu-id="5ba21-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="5ba21-113">但是，您無法宣告它们作为`Object`。</span><span class="sxs-lookup"><span data-stu-id="5ba21-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="5ba21-114">你必须将它们声明为可引发事件的特定类。</span><span class="sxs-lookup"><span data-stu-id="5ba21-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="5ba21-115">`WithEvents`修饰符可用于在此上下文中： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="5ba21-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba21-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ba21-116">See Also</span></span>  
 [<span data-ttu-id="5ba21-117">Handles</span><span class="sxs-lookup"><span data-stu-id="5ba21-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="5ba21-118">关键字</span><span class="sxs-lookup"><span data-stu-id="5ba21-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="5ba21-119">事件</span><span class="sxs-lookup"><span data-stu-id="5ba21-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
