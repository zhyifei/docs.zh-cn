---
title: "如何：实现使用后台操作的窗体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a519f1611e419ec439a70ec86f457049582c4ceb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="9578b-102">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="9578b-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="9578b-103">以下示例程序创建一个计算 Fibonacci 数字的窗体。</span><span class="sxs-lookup"><span data-stu-id="9578b-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="9578b-104">计算在独立于用户界面线程的线程上运行，因此用户界面将随计算继续运行，不会延迟。</span><span class="sxs-lookup"><span data-stu-id="9578b-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="9578b-105">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="9578b-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="9578b-106">另请参阅[演练：实现使用后台操作的窗体](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="9578b-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9578b-107">示例</span><span class="sxs-lookup"><span data-stu-id="9578b-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9578b-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="9578b-108">Compiling the Code</span></span>  
 <span data-ttu-id="9578b-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9578b-109">This example requires:</span></span>  
  
-   <span data-ttu-id="9578b-110">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9578b-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9578b-111">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="9578b-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9578b-112">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="9578b-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="9578b-113">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="9578b-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9578b-114">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9578b-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9578b-115">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="9578b-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="9578b-116">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](../../../../docs/standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="9578b-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9578b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9578b-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="9578b-118">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="9578b-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="9578b-119">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="9578b-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
