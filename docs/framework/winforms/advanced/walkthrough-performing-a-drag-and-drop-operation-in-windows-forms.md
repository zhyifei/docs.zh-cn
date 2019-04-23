---
title: 演练：在 Windows 窗体中执行拖放操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: f7551f28d07c9517865f60af99954eb40e57daa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340719"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="434cc-102">演练：在 Windows 窗体中执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="434cc-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="434cc-103">若要执行拖放操作中基于 Windows 的应用程序必须处理一系列事件，最值得注意的是<xref:System.Windows.Forms.Control.DragEnter>， <xref:System.Windows.Forms.Control.DragLeave>，和<xref:System.Windows.Forms.Control.DragDrop>事件。</span><span class="sxs-lookup"><span data-stu-id="434cc-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="434cc-104">通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。</span><span class="sxs-lookup"><span data-stu-id="434cc-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="434cc-105">拖动数据</span><span class="sxs-lookup"><span data-stu-id="434cc-105">Dragging Data</span></span>  
 <span data-ttu-id="434cc-106">所有拖放操作都从拖动开始。</span><span class="sxs-lookup"><span data-stu-id="434cc-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="434cc-107">若要启用要拖动开始时收集的数据的功能实现中<xref:System.Windows.Forms.Control.DoDragDrop%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="434cc-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="434cc-108">在以下示例中，<xref:System.Windows.Forms.Control.MouseDown>事件用于启动拖放操作，因为它是最直观 （大部分拖放操作开始与按下鼠标按钮）。</span><span class="sxs-lookup"><span data-stu-id="434cc-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="434cc-109">但是，请记住，任何事件都可用于启动拖放过程。</span><span class="sxs-lookup"><span data-stu-id="434cc-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="434cc-110">某些控件具有特定于拖动的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="434cc-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="434cc-111"><xref:System.Windows.Forms.ListView>并<xref:System.Windows.Forms.TreeView>控件，例如，具有<xref:System.Windows.Forms.TreeView.ItemDrag>事件。</span><span class="sxs-lookup"><span data-stu-id="434cc-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="434cc-112">启动拖动操作</span><span class="sxs-lookup"><span data-stu-id="434cc-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="434cc-113">在中<xref:System.Windows.Forms.Control.MouseDown>控件拖动开始的位置，使用事件`DoDragDrop`方法以设置要拖动的数据和允许的效果拖动将具有。</span><span class="sxs-lookup"><span data-stu-id="434cc-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="434cc-114">有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。</span><span class="sxs-lookup"><span data-stu-id="434cc-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="434cc-115">下面的示例演示如何启动拖动操作。</span><span class="sxs-lookup"><span data-stu-id="434cc-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="434cc-116">拖动起始的控件是<xref:System.Windows.Forms.Button>控件，要拖动的数据是字符串，表示<xref:System.Windows.Forms.Control.Text%2A>属性的<xref:System.Windows.Forms.Button>控制和允许的效果是复制或移动。</span><span class="sxs-lookup"><span data-stu-id="434cc-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    >  <span data-ttu-id="434cc-117">任何数据可作为中的参数`DoDragDrop`方法; 在上述示例中，<xref:System.Windows.Forms.Control.Text%2A>属性的<xref:System.Windows.Forms.Button>控件使用 （而不是硬编码值或从数据集检索数据） 因为该属性是否与拖动起始位置 (<xref:System.Windows.Forms.Button>控件)。</span><span class="sxs-lookup"><span data-stu-id="434cc-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="434cc-118">在将拖放操作合并到基于 Windows 的应用程序中时，请牢记这一点。</span><span class="sxs-lookup"><span data-stu-id="434cc-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="434cc-119">在拖动操作生效时，可以处理<xref:System.Windows.Forms.Control.QueryContinueDrag>事件，"询问权限"的系统，以继续拖动操作。</span><span class="sxs-lookup"><span data-stu-id="434cc-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="434cc-120">处理此方法时，它是还为您调用将会影响拖动操作，如扩展的方法的相应点<xref:System.Windows.Forms.TreeNode>在<xref:System.Windows.Forms.TreeView>控制当光标悬停在其上。</span><span class="sxs-lookup"><span data-stu-id="434cc-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="434cc-121">放置数据</span><span class="sxs-lookup"><span data-stu-id="434cc-121">Dropping Data</span></span>  
 <span data-ttu-id="434cc-122">开始从 Windows 窗体或控件上的某个位置拖动数据后，当然会想要将其放置在某处。</span><span class="sxs-lookup"><span data-stu-id="434cc-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="434cc-123">当光标经过为放置数据而进行了正确配置的窗体或控件区域时，会发生改变。</span><span class="sxs-lookup"><span data-stu-id="434cc-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="434cc-124">Windows 窗体或控件内的任何区域可通过设置接受放置的数据<xref:System.Windows.Forms.Control.AllowDrop%2A>属性和处理<xref:System.Windows.Forms.Control.DragEnter>和<xref:System.Windows.Forms.Control.DragDrop>事件。</span><span class="sxs-lookup"><span data-stu-id="434cc-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="434cc-125">执行放置</span><span class="sxs-lookup"><span data-stu-id="434cc-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="434cc-126">设置<xref:System.Windows.Forms.Control.AllowDrop%2A>属性设为 true。</span><span class="sxs-lookup"><span data-stu-id="434cc-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="434cc-127">在中`DragEnter`将要发生放置控件事件确保正在拖动的数据的可接受的类型 (在这种情况下， <xref:System.Windows.Forms.Control.Text%2A>)。</span><span class="sxs-lookup"><span data-stu-id="434cc-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="434cc-128">代码随后设置中的值发生放置操作时将发生这种情况的效果<xref:System.Windows.Forms.DragDropEffects>枚举。</span><span class="sxs-lookup"><span data-stu-id="434cc-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="434cc-129">有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>。</span><span class="sxs-lookup"><span data-stu-id="434cc-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    >  <span data-ttu-id="434cc-130">可以定义自己<xref:System.Windows.Forms.DataFormats>通过指定你自己的对象作为<xref:System.Object>参数的<xref:System.Windows.Forms.DataObject.SetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="434cc-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="434cc-131">在进行该操作时，请确保指定的对象可序列化。</span><span class="sxs-lookup"><span data-stu-id="434cc-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="434cc-132">有关详细信息，请参阅 <xref:System.Runtime.Serialization.ISerializable>。</span><span class="sxs-lookup"><span data-stu-id="434cc-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="434cc-133">在中<xref:System.Windows.Forms.Control.DragDrop>将要发生放置控件使用事件<xref:System.Windows.Forms.DataObject.GetData%2A>方法来检索正在拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="434cc-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="434cc-134">有关详细信息，请参阅 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>。</span><span class="sxs-lookup"><span data-stu-id="434cc-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="434cc-135">在以下示例中，<xref:System.Windows.Forms.TextBox>控件是控件拖到 （发生放置操作的位置）。</span><span class="sxs-lookup"><span data-stu-id="434cc-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="434cc-136">该代码设置<xref:System.Windows.Forms.Control.Text%2A>属性的<xref:System.Windows.Forms.TextBox>控制等于正在拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="434cc-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    >  <span data-ttu-id="434cc-137">此外，您可以使用<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>属性，以便根据键按下的拖放操作期间，某些会产生影响 （例如，它是标准按下了 CTRL 键时复制拖动的数据）。</span><span class="sxs-lookup"><span data-stu-id="434cc-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434cc-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="434cc-138">See also</span></span>

- [<span data-ttu-id="434cc-139">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="434cc-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="434cc-140">如何：从剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="434cc-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="434cc-141">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="434cc-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
