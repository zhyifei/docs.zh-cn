---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583043"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="6bcd9-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bcd9-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="6bcd9-103">指定一个或多个已声明的成员变量引用可引发事件的类的实例。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bcd9-104">备注</span><span class="sxs-lookup"><span data-stu-id="6bcd9-104">Remarks</span></span>

<span data-ttu-id="6bcd9-105">使用 `WithEvents` 定义变量时，可以通过声明方式指定方法使用 `Handles` 关键字来处理变量的事件。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="6bcd9-106">只能在类或模块级别使用 `WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="6bcd9-107">这意味着 `WithEvents` 变量的声明上下文必须是类或模块，不能是源文件、命名空间、结构或过程。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="6bcd9-108">不能对结构成员使用 `WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="6bcd9-109">您只能用 `WithEvents` 声明单个变量（而非数组）。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="6bcd9-110">规则</span><span class="sxs-lookup"><span data-stu-id="6bcd9-110">Rules</span></span>

<span data-ttu-id="6bcd9-111">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="6bcd9-111">**Element Types.**</span></span> <span data-ttu-id="6bcd9-112">必须将 `WithEvents` 变量声明为对象变量，以便它们可以接受类实例。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="6bcd9-113">但是，不能将它们声明为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="6bcd9-114">您必须将它们声明为可引发事件的特定类。</span><span class="sxs-lookup"><span data-stu-id="6bcd9-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="6bcd9-115">@No__t_0 修饰符可以在此上下文中使用： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="6bcd9-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="6bcd9-116">示例</span><span class="sxs-lookup"><span data-stu-id="6bcd9-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="6bcd9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bcd9-117">See also</span></span>

- [<span data-ttu-id="6bcd9-118">Handles</span><span class="sxs-lookup"><span data-stu-id="6bcd9-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="6bcd9-119">关键字</span><span class="sxs-lookup"><span data-stu-id="6bcd9-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="6bcd9-120">事件</span><span class="sxs-lookup"><span data-stu-id="6bcd9-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
