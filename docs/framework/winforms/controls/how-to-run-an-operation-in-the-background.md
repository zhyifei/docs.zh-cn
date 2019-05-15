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
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591611"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="21663-102">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="21663-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="21663-103">如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。</span><span class="sxs-lookup"><span data-stu-id="21663-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="21663-104">以下代码示例显示如何在后台运行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="21663-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="21663-105">此窗体具有“启动”和“取消”按钮。</span><span class="sxs-lookup"><span data-stu-id="21663-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="21663-106">单击“启动”按钮运行异步操作。</span><span class="sxs-lookup"><span data-stu-id="21663-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="21663-107">单击“取消”按钮停止运行异步操作。</span><span class="sxs-lookup"><span data-stu-id="21663-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="21663-108">每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。</span><span class="sxs-lookup"><span data-stu-id="21663-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="21663-109">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="21663-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="21663-110">另请参阅[演练：在后台运行操作](walkthrough-running-an-operation-in-the-background.md)。</span><span class="sxs-lookup"><span data-stu-id="21663-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21663-111">示例</span><span class="sxs-lookup"><span data-stu-id="21663-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21663-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="21663-112">Compiling the Code</span></span>  
 <span data-ttu-id="21663-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="21663-113">This example requires:</span></span>  
  
- <span data-ttu-id="21663-114">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="21663-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21663-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="21663-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="21663-116">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="21663-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="21663-117">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="21663-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)
