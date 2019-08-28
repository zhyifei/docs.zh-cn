---
title: 如何：实现使用后台操作的窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: e06b18558f6b3fa3cef47613bbaef16fb7c740f0
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046194"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="2af34-102">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="2af34-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="2af34-103">以下示例程序创建一个计算 Fibonacci 数字的窗体。</span><span class="sxs-lookup"><span data-stu-id="2af34-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="2af34-104">计算在独立于用户界面线程的线程上运行，因此用户界面将随计算继续运行，不会延迟。</span><span class="sxs-lookup"><span data-stu-id="2af34-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="2af34-105">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="2af34-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="2af34-106">另请[参阅演练:实现使用后台操作](walkthrough-implementing-a-form-that-uses-a-background-operation.md)的窗体。</span><span class="sxs-lookup"><span data-stu-id="2af34-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2af34-107">示例</span><span class="sxs-lookup"><span data-stu-id="2af34-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2af34-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="2af34-108">Compiling the Code</span></span>  
 <span data-ttu-id="2af34-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="2af34-109">This example requires:</span></span>  
  
- <span data-ttu-id="2af34-110">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="2af34-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2af34-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="2af34-111">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="2af34-112">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="2af34-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="2af34-113">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="2af34-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af34-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2af34-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="2af34-115">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="2af34-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="2af34-116">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2af34-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
