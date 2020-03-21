---
title: 演练：执行拖放操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182446"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="7ff75-102">演练：在 Windows 窗体中执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="7ff75-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="7ff75-103">要在基于 Windows 的应用程序中执行拖放操作，必须处理一系列事件，其中最著名的是<xref:System.Windows.Forms.Control.DragEnter>，<xref:System.Windows.Forms.Control.DragLeave>和<xref:System.Windows.Forms.Control.DragDrop>事件。</span><span class="sxs-lookup"><span data-stu-id="7ff75-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="7ff75-104">通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。</span><span class="sxs-lookup"><span data-stu-id="7ff75-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="7ff75-105">拖动数据</span><span class="sxs-lookup"><span data-stu-id="7ff75-105">Dragging Data</span></span>  
 <span data-ttu-id="7ff75-106">所有拖放操作都从拖动开始。</span><span class="sxs-lookup"><span data-stu-id="7ff75-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="7ff75-107">在<xref:System.Windows.Forms.Control.DoDragDrop%2A>方法中实现了在方法中实现在拖动开始时启用收集数据的功能。</span><span class="sxs-lookup"><span data-stu-id="7ff75-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="7ff75-108">在下面的示例中，<xref:System.Windows.Forms.Control.MouseDown>该事件用于启动拖动操作，因为它是最直观的（大多数拖放操作从按下鼠标按钮开始）。</span><span class="sxs-lookup"><span data-stu-id="7ff75-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="7ff75-109">但是，请记住，任何事件都可用于启动拖放过程。</span><span class="sxs-lookup"><span data-stu-id="7ff75-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ff75-110">某些控件具有特定于拖动的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="7ff75-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="7ff75-111"><xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件，例如，有一个<xref:System.Windows.Forms.TreeView.ItemDrag>事件。</span><span class="sxs-lookup"><span data-stu-id="7ff75-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="7ff75-112">启动拖动操作</span><span class="sxs-lookup"><span data-stu-id="7ff75-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="7ff75-113">对于将开始<xref:System.Windows.Forms.Control.MouseDown>拖动的控件，使用`DoDragDrop`方法设置要拖动的数据，并且允许的效果拖动将具有。</span><span class="sxs-lookup"><span data-stu-id="7ff75-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="7ff75-114">有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。</span><span class="sxs-lookup"><span data-stu-id="7ff75-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="7ff75-115">下面的示例演示如何启动拖动操作。</span><span class="sxs-lookup"><span data-stu-id="7ff75-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="7ff75-116">拖动开始的控件是<xref:System.Windows.Forms.Button>控件，要拖动的数据是表示控件<xref:System.Windows.Forms.Control.Text%2A>属性的<xref:System.Windows.Forms.Button>字符串，允许的效果是复制或移动。</span><span class="sxs-lookup"><span data-stu-id="7ff75-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="7ff75-117">任何数据都可以用作`DoDragDrop`方法中的参数;在上面的示例中，使用了<xref:System.Windows.Forms.Control.Text%2A><xref:System.Windows.Forms.Button>控件的属性（而不是硬编码值或从数据集检索数据），因为该属性与从中拖动的位置（<xref:System.Windows.Forms.Button>控件）相关。</span><span class="sxs-lookup"><span data-stu-id="7ff75-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="7ff75-118">在将拖放操作合并到基于 Windows 的应用程序中时，请牢记这一点。</span><span class="sxs-lookup"><span data-stu-id="7ff75-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="7ff75-119">当拖动操作有效时，您可以处理<xref:System.Windows.Forms.Control.QueryContinueDrag>事件，该事件"请求"系统的权限以继续拖动操作。</span><span class="sxs-lookup"><span data-stu-id="7ff75-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="7ff75-120">处理此方法时，调用对拖动操作有影响的方法也是适当的点，例如当光标悬停在<xref:System.Windows.Forms.TreeNode><xref:System.Windows.Forms.TreeView>控件上时展开 控件中的 。</span><span class="sxs-lookup"><span data-stu-id="7ff75-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="7ff75-121">放置数据</span><span class="sxs-lookup"><span data-stu-id="7ff75-121">Dropping Data</span></span>  
 <span data-ttu-id="7ff75-122">开始从 Windows 窗体或控件上的某个位置拖动数据后，当然会想要将其放置在某处。</span><span class="sxs-lookup"><span data-stu-id="7ff75-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="7ff75-123">当光标经过为放置数据而进行了正确配置的窗体或控件区域时，会发生改变。</span><span class="sxs-lookup"><span data-stu-id="7ff75-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="7ff75-124">可以通过设置<xref:System.Windows.Forms.Control.AllowDrop%2A>属性和处理<xref:System.Windows.Forms.Control.DragEnter>和<xref:System.Windows.Forms.Control.DragDrop>事件来使 Windows 窗体或控件中的任何区域接受丢弃的数据。</span><span class="sxs-lookup"><span data-stu-id="7ff75-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="7ff75-125">执行放置</span><span class="sxs-lookup"><span data-stu-id="7ff75-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="7ff75-126">将<xref:System.Windows.Forms.Control.AllowDrop%2A>属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="7ff75-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="7ff75-127">对于`DragEnter`发生丢弃的控件，请确保拖动的数据是可接受的类型（在本例中为<xref:System.Windows.Forms.Control.Text%2A>）。</span><span class="sxs-lookup"><span data-stu-id="7ff75-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="7ff75-128">然后，代码设置在枚举中<xref:System.Windows.Forms.DragDropEffects>放置到值时将发生的效果。</span><span class="sxs-lookup"><span data-stu-id="7ff75-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="7ff75-129">有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>。</span><span class="sxs-lookup"><span data-stu-id="7ff75-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="7ff75-130">可以通过将自己的对象指定<xref:System.Windows.Forms.DataFormats>为方法的<xref:System.Object>参数来<xref:System.Windows.Forms.DataObject.SetData%2A>定义您自己的对象。</span><span class="sxs-lookup"><span data-stu-id="7ff75-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="7ff75-131">在进行该操作时，请确保指定的对象可序列化。</span><span class="sxs-lookup"><span data-stu-id="7ff75-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="7ff75-132">有关详细信息，请参阅 <xref:System.Runtime.Serialization.ISerializable>。</span><span class="sxs-lookup"><span data-stu-id="7ff75-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="7ff75-133">对于<xref:System.Windows.Forms.Control.DragDrop>发生放置的控件，使用 方法<xref:System.Windows.Forms.DataObject.GetData%2A>检索要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="7ff75-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="7ff75-134">有关详细信息，请参阅 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>。</span><span class="sxs-lookup"><span data-stu-id="7ff75-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="7ff75-135">在下面的示例中，<xref:System.Windows.Forms.TextBox>控件是拖动到（将发生丢弃的位置）的控件。</span><span class="sxs-lookup"><span data-stu-id="7ff75-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="7ff75-136">代码设置控件<xref:System.Windows.Forms.Control.Text%2A>的属性<xref:System.Windows.Forms.TextBox>等于要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="7ff75-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="7ff75-137">此外，您可以使用 该<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>属性，以便根据拖放操作期间按下的键，会发生某些效果（例如，在按下 CTRL 键时复制拖动的数据是标准）。</span><span class="sxs-lookup"><span data-stu-id="7ff75-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff75-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ff75-138">See also</span></span>

- [<span data-ttu-id="7ff75-139">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="7ff75-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="7ff75-140">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="7ff75-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="7ff75-141">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="7ff75-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
