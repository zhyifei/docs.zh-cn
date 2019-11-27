---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 2309c675b50a2025d73841a47fe8e30e7cecd522
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350744"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="cb760-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb760-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="cb760-103">指定一个或多个已声明的成员变量引用可引发事件的类的实例。</span><span class="sxs-lookup"><span data-stu-id="cb760-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb760-104">备注</span><span class="sxs-lookup"><span data-stu-id="cb760-104">Remarks</span></span>

<span data-ttu-id="cb760-105">使用 `WithEvents`定义变量时，可以通过声明方式指定方法使用 `Handles` 关键字来处理变量的事件。</span><span class="sxs-lookup"><span data-stu-id="cb760-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="cb760-106">只能在类或模块级别使用 `WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="cb760-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="cb760-107">这意味着 `WithEvents` 变量的声明上下文必须是类或模块，不能是源文件、命名空间、结构或过程。</span><span class="sxs-lookup"><span data-stu-id="cb760-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="cb760-108">不能对结构成员使用 `WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="cb760-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="cb760-109">您只能用 `WithEvents`声明单个变量（而非数组）。</span><span class="sxs-lookup"><span data-stu-id="cb760-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="cb760-110">规则</span><span class="sxs-lookup"><span data-stu-id="cb760-110">Rules</span></span>

<span data-ttu-id="cb760-111">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="cb760-111">**Element Types.**</span></span> <span data-ttu-id="cb760-112">必须将 `WithEvents` 变量声明为对象变量，以便它们可以接受类实例。</span><span class="sxs-lookup"><span data-stu-id="cb760-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="cb760-113">但是，不能将它们声明为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="cb760-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="cb760-114">您必须将它们声明为可引发事件的特定类。</span><span class="sxs-lookup"><span data-stu-id="cb760-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="cb760-115">`WithEvents` 修饰符可以在此上下文中使用： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="cb760-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="cb760-116">示例</span><span class="sxs-lookup"><span data-stu-id="cb760-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="cb760-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb760-117">See also</span></span>

- <span data-ttu-id="cb760-118">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="cb760-118">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="cb760-119">关键字</span><span class="sxs-lookup"><span data-stu-id="cb760-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="cb760-120">事件</span><span class="sxs-lookup"><span data-stu-id="cb760-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
