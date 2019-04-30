---
title: 如何：将多个事件连接到 Windows 窗体中的单个事件处理程序
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: eec6a754b885cd169e5542221caefb3233c4c8af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967008"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="262d2-102">如何：将多个事件连接到 Windows 窗体中的单个事件处理程序</span><span class="sxs-lookup"><span data-stu-id="262d2-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="262d2-103">在应用程序设计中，您可能会发现需要使用多个事件的单个事件处理程序或具有多个事件执行相同的过程。</span><span class="sxs-lookup"><span data-stu-id="262d2-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="262d2-104">例如，它通常是功能强大的时间-保护程序已引发相同的事件，你的窗体上的按钮一样如果它们公开相同的功能的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="262d2-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="262d2-105">您可以执行此操作通过使用属性窗口中的事件视图C#或使用`Handles`关键字和**类名**并**方法名称**下拉列表框在 Visual Basic 代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="262d2-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="262d2-106">若要将多个事件连接到在 Visual Basic 中的单个事件处理程序</span><span class="sxs-lookup"><span data-stu-id="262d2-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="262d2-107">右键单击窗体，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="262d2-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="262d2-108">从**类名**下拉列表框中，选择一个想要处理的事件处理程序的控件。</span><span class="sxs-lookup"><span data-stu-id="262d2-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="262d2-109">从**方法名称**下拉列表框中，选择你想要处理的事件处理程序的事件之一。</span><span class="sxs-lookup"><span data-stu-id="262d2-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="262d2-110">在代码编辑器将插入相应的事件处理程序，并将插入点放在方法内。</span><span class="sxs-lookup"><span data-stu-id="262d2-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="262d2-111">在下面的示例中，它是<xref:System.Windows.Forms.Control.Click>事件<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="262d2-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="262d2-112">追加的其他事件所处理到`Handles`子句。</span><span class="sxs-lookup"><span data-stu-id="262d2-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="262d2-113">将相应的代码添加到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="262d2-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="262d2-114">若要将多个事件连接到在 C 中的单个事件处理程序\#</span><span class="sxs-lookup"><span data-stu-id="262d2-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="262d2-115">选择你想要连接的事件处理程序的控件。</span><span class="sxs-lookup"><span data-stu-id="262d2-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="262d2-116">在属性窗口中，单击**事件**按钮 (![事件按钮](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))。</span><span class="sxs-lookup"><span data-stu-id="262d2-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="262d2-117">单击你想要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="262d2-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="262d2-118">在事件名称旁边的值部分中，单击下拉列表按钮以显示与你想要处理的事件的方法签名匹配的现有事件处理程序的列表。</span><span class="sxs-lookup"><span data-stu-id="262d2-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="262d2-119">从列表中选择相应的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="262d2-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="262d2-120">代码将添加到要将事件绑定到现有的事件处理程序的窗体。</span><span class="sxs-lookup"><span data-stu-id="262d2-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262d2-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="262d2-121">See also</span></span>

- [<span data-ttu-id="262d2-122">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="262d2-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="262d2-123">事件处理程序概述</span><span class="sxs-lookup"><span data-stu-id="262d2-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
