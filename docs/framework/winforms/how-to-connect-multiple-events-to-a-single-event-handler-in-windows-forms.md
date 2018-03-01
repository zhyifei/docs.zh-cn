---
title: "如何：将多个事件连接到 Windows 窗体中的单个事件处理程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfd955b4153c7a2bc54d8b52ff1801541c3a7559
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="299b9-102">如何：将多个事件连接到 Windows 窗体中的单个事件处理程序</span><span class="sxs-lookup"><span data-stu-id="299b9-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="299b9-103">在应用程序设计中，你可能会发现多个事件用于单个事件处理程序或具有多个事件执行相同的过程所需。</span><span class="sxs-lookup"><span data-stu-id="299b9-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="299b9-104">例如，它通常是功能强大的时间的保护程序具有引发同一事件，因为它们公开相同的功能时，将执行你的窗体上的按钮的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="299b9-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="299b9-105">你可以执行此操作通过使用 C# 中的属性窗口的事件视图或使用`Handles`关键字和**类名**和**方法名称**下拉列表框在 Visual Basic 代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="299b9-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="299b9-106">若要将多个事件连接到在 Visual Basic 中的单个事件处理程序</span><span class="sxs-lookup"><span data-stu-id="299b9-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="299b9-107">右键单击该表单，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="299b9-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="299b9-108">从**类名**下拉列表框中，选择一个你想要处理的事件处理程序的控件。</span><span class="sxs-lookup"><span data-stu-id="299b9-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="299b9-109">从**方法名称**下拉列表框中，选择一个你想要处理的事件处理程序的事件。</span><span class="sxs-lookup"><span data-stu-id="299b9-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="299b9-110">代码编辑器将插入相应的事件处理程序并将插入点放在方法内。</span><span class="sxs-lookup"><span data-stu-id="299b9-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="299b9-111">在下面的示例中，它是<xref:System.Windows.Forms.Control.Click>事件<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="299b9-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="299b9-112">追加的其他事件你想要处理到`Handles`子句。</span><span class="sxs-lookup"><span data-stu-id="299b9-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="299b9-113">将相应的代码添加到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="299b9-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="299b9-114">若要将多个事件连接到在 C# 中的单个事件处理程序</span><span class="sxs-lookup"><span data-stu-id="299b9-114">To connect multiple events to a single event handler in C#</span></span>  
  
1.  <span data-ttu-id="299b9-115">选择你想要连接的事件处理程序的控件。</span><span class="sxs-lookup"><span data-stu-id="299b9-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="299b9-116">在属性窗口中，单击**事件**按钮 (![事件按钮](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))。</span><span class="sxs-lookup"><span data-stu-id="299b9-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="299b9-117">单击你想要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="299b9-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="299b9-118">在事件名称旁边的值部分中，单击下拉列表按钮，以显示与你想要处理的事件的方法签名匹配的现有事件处理程序的列表。</span><span class="sxs-lookup"><span data-stu-id="299b9-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="299b9-119">从列表中选择相应的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="299b9-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="299b9-120">会将代码添加到窗体，以将该事件绑定到现有的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="299b9-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299b9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="299b9-121">See Also</span></span>  
 [<span data-ttu-id="299b9-122">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="299b9-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="299b9-123">事件处理程序概述</span><span class="sxs-lookup"><span data-stu-id="299b9-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
