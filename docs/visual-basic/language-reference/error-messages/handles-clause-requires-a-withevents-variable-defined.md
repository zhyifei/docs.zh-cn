---
title: Handles 子句需要在包含类型或它的基类型之一中定义的 WithEvents 变量
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582827"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="d417f-102">Handles 子句需要在包含类型或它的基类型之一中定义的 WithEvents 变量</span><span class="sxs-lookup"><span data-stu-id="d417f-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="d417f-103">未在 `Handles` 子句中提供 `WithEvents` 变量。</span><span class="sxs-lookup"><span data-stu-id="d417f-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="d417f-104">过程声明末尾的 `Handles` 关键字会使其处理由使用 `WithEvents` 关键字声明的对象变量引发的事件。</span><span class="sxs-lookup"><span data-stu-id="d417f-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="d417f-105">**错误 ID：** BC30506</span><span class="sxs-lookup"><span data-stu-id="d417f-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d417f-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d417f-106">To correct this error</span></span>

<span data-ttu-id="d417f-107">提供必需的 `WithEvents` 变量。</span><span class="sxs-lookup"><span data-stu-id="d417f-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="d417f-108">示例</span><span class="sxs-lookup"><span data-stu-id="d417f-108">Example</span></span>

<span data-ttu-id="d417f-109">在下面的示例中，Visual Basic 生成编译器错误 `BC30506`，因为 <xref:System.Timers.Timer?displayProperty=nameWithType> 实例的定义中未使用[WithEvents](../modifiers/withevents.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="d417f-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

<span data-ttu-id="d417f-110">下面的示例成功编译，因为 `_timer1` 变量是用 `WithEvents` 关键字定义的：</span><span class="sxs-lookup"><span data-stu-id="d417f-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a><span data-ttu-id="d417f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d417f-111">See also</span></span>

- [<span data-ttu-id="d417f-112">Handles</span><span class="sxs-lookup"><span data-stu-id="d417f-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
