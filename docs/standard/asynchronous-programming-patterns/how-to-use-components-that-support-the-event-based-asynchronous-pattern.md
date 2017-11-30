---
title: "如何：使用支持基于事件的异步模式的组件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="3dbbe-102">如何：使用支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="3dbbe-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="3dbbe-103">许多组件都为你提供了以异步方式执行其工作的选项。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="3dbbe-104"><xref:System.Media.SoundPlayer>和<xref:System.Windows.Forms.PictureBox>组件，例如，启用可加载听起来和图像"在后台"，同时主线程继续运行而不中断。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="3dbbe-105">支持的类上使用异步方法[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)可以很简单，例如将事件处理程序附加到组件的*MethodName* `Completed`事件，正如你的任何其他事件一样。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="3dbbe-106">当调用*MethodName* `Async`方法，你的应用程序将继续运行而不会中断，直到*MethodName* `Completed`引发事件。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="3dbbe-107">在事件处理程序，可以检查<xref:System.ComponentModel.AsyncCompletedEventArgs>参数以确定是否已成功完成异步操作，或者已取消。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="3dbbe-108">有关使用事件处理程序的详细信息，请参阅[事件处理程序概述](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="3dbbe-109">下面的过程演示如何使用的异步图像加载功能<xref:System.Windows.Forms.PictureBox>控件。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="3dbbe-110">若要启用 PictureBox 控件以异步加载图像</span><span class="sxs-lookup"><span data-stu-id="3dbbe-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="3dbbe-111">创建的实例<xref:System.Windows.Forms.PictureBox>组件窗体中。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="3dbbe-112">分配到一个事件处理程序<xref:System.Windows.Forms.PictureBox.LoadCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="3dbbe-113">检查有异步下载过程中可能发生的任何错误。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="3dbbe-114">这是你到哪里检查取消。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="3dbbe-115">添加两个按钮，调用`loadButton`和`cancelLoadButton`，向窗体。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="3dbbe-116">添加<xref:System.Windows.Forms.Control.Click>事件处理程序来启动和取消下载。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="3dbbe-117">运行您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-117">Run your application.</span></span>  
  
     <span data-ttu-id="3dbbe-118">映像下载开始后，你可以自由地移动窗体、 降到最低，和其最大化。</span><span class="sxs-lookup"><span data-stu-id="3dbbe-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbbe-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dbbe-119">See Also</span></span>  
 [<span data-ttu-id="3dbbe-120">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="3dbbe-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="3dbbe-121">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="3dbbe-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="3dbbe-122">不在生成中： Visual Basic 中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="3dbbe-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
