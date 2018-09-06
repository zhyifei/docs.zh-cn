---
title: 如何：在后台运行操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 94abd36affdccec1d01c030fcff4c6de93ca6c72
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773494"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="34a61-102">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="34a61-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="34a61-103">如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。</span><span class="sxs-lookup"><span data-stu-id="34a61-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="34a61-104">以下代码示例显示如何在后台运行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="34a61-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="34a61-105">此窗体具有“启动”和“取消”按钮。</span><span class="sxs-lookup"><span data-stu-id="34a61-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="34a61-106">单击“启动”按钮运行异步操作。</span><span class="sxs-lookup"><span data-stu-id="34a61-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="34a61-107">单击“取消”按钮停止运行异步操作。</span><span class="sxs-lookup"><span data-stu-id="34a61-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="34a61-108">每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。</span><span class="sxs-lookup"><span data-stu-id="34a61-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="34a61-109">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="34a61-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="34a61-110">另请参阅[演练：在后台运行操作](walkthrough-running-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="34a61-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a61-111">示例</span><span class="sxs-lookup"><span data-stu-id="34a61-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34a61-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="34a61-112">Compiling the Code</span></span>  
 <span data-ttu-id="34a61-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="34a61-113">This example requires:</span></span>  
  
-   <span data-ttu-id="34a61-114">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="34a61-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="34a61-115">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="34a61-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="34a61-116">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="34a61-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="34a61-117">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="34a61-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a61-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="34a61-118">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="34a61-119">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="34a61-119">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="34a61-120">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="34a61-120">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
