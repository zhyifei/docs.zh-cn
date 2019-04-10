---
title: 如何：在运行时在控件的集合中进行添加或删除
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
ms.openlocfilehash: 85c1d398c1aabbb73d5ae34186775e2c63666cfb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309441"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="defba-102">如何：在运行时在控件的集合中进行添加或删除</span><span class="sxs-lookup"><span data-stu-id="defba-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="defba-103">应用程序开发中的常见任务是添加到控件和窗体上任何容器控件中移除控件 (如<xref:System.Windows.Forms.Panel>或<xref:System.Windows.Forms.GroupBox>控件或甚至窗体本身)。</span><span class="sxs-lookup"><span data-stu-id="defba-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="defba-104">在设计时，可直接将控件拖到面板或分组框上。</span><span class="sxs-lookup"><span data-stu-id="defba-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="defba-105">在运行时，这些控件维护一个 `Controls` 集合，该集合会跟踪集合中放置了哪些控件。</span><span class="sxs-lookup"><span data-stu-id="defba-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="defba-106">以下代码示例适用于其中维护了一个控件集合的任何控件。</span><span class="sxs-lookup"><span data-stu-id="defba-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="defba-107">以编程方式向集合添加控件</span><span class="sxs-lookup"><span data-stu-id="defba-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="defba-108">创建要添加的控件实例。</span><span class="sxs-lookup"><span data-stu-id="defba-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="defba-109">设置新控件的属性。</span><span class="sxs-lookup"><span data-stu-id="defba-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="defba-110">将控件添加到父控件的 `Controls` 集合。</span><span class="sxs-lookup"><span data-stu-id="defba-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="defba-111">下面的代码示例演示如何创建的实例<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="defba-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="defba-112">它需要一个具有窗体<xref:System.Windows.Forms.Panel>控制的和要创建的按钮的事件处理方法， `NewPanelButton_Click`，已存在。</span><span class="sxs-lookup"><span data-stu-id="defba-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="defba-113">以编程方式从集合移除控件</span><span class="sxs-lookup"><span data-stu-id="defba-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="defba-114">从事件中移除事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="defba-114">Remove the event handler from the event.</span></span> <span data-ttu-id="defba-115">在 Visual Basic 中，使用[RemoveHandler 语句](~/docs/visual-basic/language-reference/statements/removehandler-statement.md)关键字; 在视觉对象中C#，使用[-= 运算符 (C#引用)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="defba-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in Visual C#, use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2. <span data-ttu-id="defba-116">使用 `Remove` 方法，从面板的 `Controls` 集合中删除所需控件。</span><span class="sxs-lookup"><span data-stu-id="defba-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="defba-117">调用<xref:System.Windows.Forms.Control.Dispose%2A>方法来释放控件使用的所有资源。</span><span class="sxs-lookup"><span data-stu-id="defba-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="defba-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="defba-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="defba-119">Panel 控件</span><span class="sxs-lookup"><span data-stu-id="defba-119">Panel Control</span></span>](panel-control-windows-forms.md)
