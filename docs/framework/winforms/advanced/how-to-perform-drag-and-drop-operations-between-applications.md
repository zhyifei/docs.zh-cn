---
title: "如何：在应用程序之间执行拖放操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 514c283575ca54e74d23ae31d3590979be2c3ef0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="fc811-102">如何：在应用程序之间执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="fc811-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="fc811-103">执行应用程序间的拖放操作与在一个应用程序内启用此操作并无差别，只要涉及的两个应用程序均按照 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> 和 <xref:System.Windows.Forms.DragEventArgs.Effect%2A> 属性之间建立的“协定”实施行为。</span><span class="sxs-lookup"><span data-stu-id="fc811-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="fc811-104">在下面的过程中，你将使用你创建的基于 Windows 的应用程序和 Windows 操作系统附带的“写字板”字处理器，以在应用程序之间执行拖放操作。</span><span class="sxs-lookup"><span data-stu-id="fc811-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="fc811-105">写字板具有一组特定的用于被拖放文本的允许的效果；你要为其编写代码的基于 Windows 的应用程序将使用这些效果来成功地完成拖放操作。</span><span class="sxs-lookup"><span data-stu-id="fc811-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="fc811-106">在应用程序之间执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="fc811-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="fc811-107">创建新的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc811-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="fc811-108">向窗体添加一个 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="fc811-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="fc811-109">配置 <xref:System.Windows.Forms.TextBox> 控件以接收放置的数据。</span><span class="sxs-lookup"><span data-stu-id="fc811-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="fc811-110">有关详细信息，请参阅[演练： 在 Windows 窗体中执行拖放操作](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="fc811-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="fc811-111">运行基于 Windows 的应用程序，并在运行该应用程序时运行写字板。</span><span class="sxs-lookup"><span data-stu-id="fc811-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="fc811-112">写字板是由 Windows 安装的允许拖放操作的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="fc811-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="fc811-113">对其进行访问通过按**启动**按钮，选择**运行**，，然后键入`WordPad`的文本框**运行**对话框框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fc811-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="fc811-114">打开写字板后，在其中键入文本字符串。</span><span class="sxs-lookup"><span data-stu-id="fc811-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="fc811-115">使用鼠标选择该文本，然后将所选的文本拖动到基于 Windows 的应用程序中的 <xref:System.Windows.Forms.TextBox> 控件之上。</span><span class="sxs-lookup"><span data-stu-id="fc811-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="fc811-116">注意，当你将鼠标移到 <xref:System.Windows.Forms.TextBox> 控件上（并因此引发 <xref:System.Windows.Forms.Control.DragEnter> 事件）时，光标会改变，可以将所选的文本放入 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="fc811-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="fc811-117">此外，还可以配置 <xref:System.Windows.Forms.TextBox> 控件，以允许将文本字符串拖放到写字板中。</span><span class="sxs-lookup"><span data-stu-id="fc811-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="fc811-118">有关详细信息，请参阅[演练： 在 Windows 窗体中执行拖放操作](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="fc811-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc811-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc811-119">See Also</span></span>  
 [<span data-ttu-id="fc811-120">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="fc811-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="fc811-121">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="fc811-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="fc811-122">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="fc811-122">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
