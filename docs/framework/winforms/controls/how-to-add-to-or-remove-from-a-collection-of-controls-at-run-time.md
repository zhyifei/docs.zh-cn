---
title: 如何：在运行时在控件集合中进行添加或移除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182280"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="59814-102">如何：在运行时在控件集合中进行添加或移除</span><span class="sxs-lookup"><span data-stu-id="59814-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="59814-103">应用程序开发中的常见任务是向窗体上的任何容器控件（如<xref:System.Windows.Forms.Panel>或<xref:System.Windows.Forms.GroupBox>控件，甚至窗体本身）添加控件并删除控件。</span><span class="sxs-lookup"><span data-stu-id="59814-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="59814-104">在设计时，可直接将控件拖到面板或分组框上。</span><span class="sxs-lookup"><span data-stu-id="59814-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="59814-105">在运行时，这些控件维护一个 `Controls` 集合，该集合会跟踪集合中放置了哪些控件。</span><span class="sxs-lookup"><span data-stu-id="59814-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59814-106">以下代码示例适用于其中维护了一个控件集合的任何控件。</span><span class="sxs-lookup"><span data-stu-id="59814-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="59814-107">以编程方式向集合添加控件</span><span class="sxs-lookup"><span data-stu-id="59814-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="59814-108">创建要添加的控件实例。</span><span class="sxs-lookup"><span data-stu-id="59814-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="59814-109">设置新控件的属性。</span><span class="sxs-lookup"><span data-stu-id="59814-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="59814-110">将控件添加到父控件的 `Controls` 集合。</span><span class="sxs-lookup"><span data-stu-id="59814-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="59814-111">以下代码示例演示如何创建控件的<xref:System.Windows.Forms.Button>实例。</span><span class="sxs-lookup"><span data-stu-id="59814-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="59814-112">它需要具有<xref:System.Windows.Forms.Panel>控件的窗体，并且正在创建的`NewPanelButton_Click`按钮的事件处理方法已存在。</span><span class="sxs-lookup"><span data-stu-id="59814-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="59814-113">以编程方式从集合移除控件</span><span class="sxs-lookup"><span data-stu-id="59814-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="59814-114">从事件中移除事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="59814-114">Remove the event handler from the event.</span></span> <span data-ttu-id="59814-115">在可视化基本版中，使用"删除处理程序语句"关键字;在"可视基本"中，使用["删除处理程序语句"](../../../visual-basic/language-reference/statements/removehandler-statement.md)关键字。在 C# 中，使用[-# 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="59814-115">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="59814-116">使用 `Remove` 方法，从面板的 `Controls` 集合中删除所需控件。</span><span class="sxs-lookup"><span data-stu-id="59814-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="59814-117">调用<xref:System.Windows.Forms.Control.Dispose%2A>方法以释放控件使用的所有资源。</span><span class="sxs-lookup"><span data-stu-id="59814-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59814-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59814-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="59814-119">Panel 控件</span><span class="sxs-lookup"><span data-stu-id="59814-119">Panel Control</span></span>](panel-control-windows-forms.md)
