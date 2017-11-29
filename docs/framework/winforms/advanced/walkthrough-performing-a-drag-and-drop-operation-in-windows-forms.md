---
title: "演练：在 Windows 窗体中执行拖放操作"
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
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fe2b54123e117f21f3bda7bc78bc9c5b45fc9ae3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="8a0bb-102">演练：在 Windows 窗体中执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="8a0bb-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="8a0bb-103">若要执行拖放操作中基于 Windows 的应用程序必须处理一系列事件，最值得注意的是<xref:System.Windows.Forms.Control.DragEnter>， <xref:System.Windows.Forms.Control.DragLeave>，和<xref:System.Windows.Forms.Control.DragDrop>事件。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="8a0bb-104">通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="8a0bb-105">拖动数据</span><span class="sxs-lookup"><span data-stu-id="8a0bb-105">Dragging Data</span></span>  
 <span data-ttu-id="8a0bb-106">所有拖放操作都从拖动开始。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="8a0bb-107">中实现的功能以启用数据拖动开始时要收集<xref:System.Windows.Forms.Control.DoDragDrop%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="8a0bb-108">在下面的示例中，<xref:System.Windows.Forms.Control.MouseDown>事件用于启动拖动操作，因为它是最直观 （大多数拖放操作开始与按下鼠标按钮）。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="8a0bb-109">但是，请记住，任何事件都可用于启动拖放过程。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a0bb-110">某些控件具有特定于拖动的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="8a0bb-111"><xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件，例如，具有<xref:System.Windows.Forms.TreeView.ItemDrag>事件。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="8a0bb-112">启动拖动操作</span><span class="sxs-lookup"><span data-stu-id="8a0bb-112">To start a drag operation</span></span>  
  
1.  <span data-ttu-id="8a0bb-113">在<xref:System.Windows.Forms.Control.MouseDown>控件拖动开始的位置，使用事件`DoDragDrop`方法以设置要拖动的数据和允许的效果拖动将具有。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="8a0bb-114">有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="8a0bb-115">下面的示例演示如何启动拖动操作。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="8a0bb-116">控件中拖动操作开始是<xref:System.Windows.Forms.Button>控件，要拖动的数据是字符串，表示<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.Button>控制和允许的效果是复制或移动。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8a0bb-117">任何数据可作为参数传入`DoDragDrop`方法; 在上例中，<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.Button>控制已使用 （而不是一个值进行硬编码或从数据集检索数据） 因为相关属性从要拖动的位置 (<xref:System.Windows.Forms.Button>控件)。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="8a0bb-118">在将拖放操作合并到基于 Windows 的应用程序中时，请牢记这一点。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="8a0bb-119">在拖动操作期间生效，你可以处理<xref:System.Windows.Forms.Control.QueryContinueDrag>"询问权限"的事件的系统继续拖动操作。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="8a0bb-120">时处理此方法时，它也是合适的点，您才能调用方法将会影响上拖动操作，例如展开<xref:System.Windows.Forms.TreeNode>中<xref:System.Windows.Forms.TreeView>控制当光标悬停在其上。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="8a0bb-121">放置数据</span><span class="sxs-lookup"><span data-stu-id="8a0bb-121">Dropping Data</span></span>  
 <span data-ttu-id="8a0bb-122">开始从 Windows 窗体或控件上的某个位置拖动数据后，当然会想要将其放置在某处。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="8a0bb-123">当光标经过为放置数据而进行了正确配置的窗体或控件区域时，会发生改变。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="8a0bb-124">通过设置接受放置的数据可在 Windows 窗体或控件的任何区域<xref:System.Windows.Forms.Control.AllowDrop%2A>属性和处理<xref:System.Windows.Forms.Control.DragEnter>和<xref:System.Windows.Forms.Control.DragDrop>事件。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="8a0bb-125">执行放置</span><span class="sxs-lookup"><span data-stu-id="8a0bb-125">To perform a drop</span></span>  
  
1.  <span data-ttu-id="8a0bb-126">设置<xref:System.Windows.Forms.Control.AllowDrop%2A>属性为 true。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2.  <span data-ttu-id="8a0bb-127">在`DragEnter`控件将在其中放置发生，事件确保要拖动的数据的可接受的类型 (在这种情况下， <xref:System.Windows.Forms.Control.Text%2A>)。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="8a0bb-128">代码随后设置下拉发生中的值时将发生这种情况的影响<xref:System.Windows.Forms.DragDropEffects>枚举。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="8a0bb-129">有关详细信息，请参阅<xref:System.Windows.Forms.DragEventArgs.Effect%2A>。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8a0bb-130">你可以定义自己<xref:System.Windows.Forms.DataFormats>通过指定您自己的对象作为<xref:System.Object>参数<xref:System.Windows.Forms.DataObject.SetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="8a0bb-131">在进行该操作时，请确保指定的对象可序列化。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="8a0bb-132">有关更多信息，请参见<xref:System.Runtime.Serialization.ISerializable>。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3.  <span data-ttu-id="8a0bb-133">在<xref:System.Windows.Forms.Control.DragDrop>控件将在其中放置发生，使用事件<xref:System.Windows.Forms.DataObject.GetData%2A>方法来检索要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="8a0bb-134">有关更多信息，请参见<xref:System.Security.Cryptography.Xml.DataObject.Data%2A>。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="8a0bb-135">在示例中，<xref:System.Windows.Forms.TextBox>控件是正在拖动到 （将在其中放置发生） 的控件。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="8a0bb-136">该代码设置<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.TextBox>控制等于要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8a0bb-137">此外，你可以使用<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>属性，以便根据键按下在拖放操作时，某些效果发生 （例如，它位于标准版，以将拖动的数据复制时按下 CTRL 键）。</span><span class="sxs-lookup"><span data-stu-id="8a0bb-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0bb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a0bb-138">See Also</span></span>  
 [<span data-ttu-id="8a0bb-139">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="8a0bb-139">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="8a0bb-140">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="8a0bb-140">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="8a0bb-141">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="8a0bb-141">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
