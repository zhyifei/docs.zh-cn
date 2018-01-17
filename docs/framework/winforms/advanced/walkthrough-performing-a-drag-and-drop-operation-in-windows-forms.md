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
ms.workload: dotnet
ms.openlocfilehash: 173af57f1ec5d9ed14afc0ef5d6ddd391e15d534
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>演练：在 Windows 窗体中执行拖放操作
若要执行拖放操作中基于 Windows 的应用程序必须处理一系列事件，最值得注意的是<xref:System.Windows.Forms.Control.DragEnter>， <xref:System.Windows.Forms.Control.DragLeave>，和<xref:System.Windows.Forms.Control.DragDrop>事件。 通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。  
  
## <a name="dragging-data"></a>拖动数据  
 所有拖放操作都从拖动开始。 中实现的功能以启用数据拖动开始时要收集<xref:System.Windows.Forms.Control.DoDragDrop%2A>方法。  
  
 在下面的示例中，<xref:System.Windows.Forms.Control.MouseDown>事件用于启动拖动操作，因为它是最直观 （大多数拖放操作开始与按下鼠标按钮）。 但是，请记住，任何事件都可用于启动拖放过程。  
  
> [!NOTE]
>  某些控件具有特定于拖动的自定义事件。 <xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件，例如，具有<xref:System.Windows.Forms.TreeView.ItemDrag>事件。  
  
#### <a name="to-start-a-drag-operation"></a>启动拖动操作  
  
1.  在<xref:System.Windows.Forms.Control.MouseDown>控件拖动开始的位置，使用事件`DoDragDrop`方法以设置要拖动的数据和允许的效果拖动将具有。 有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。  
  
     下面的示例演示如何启动拖动操作。 控件中拖动操作开始是<xref:System.Windows.Forms.Button>控件，要拖动的数据是字符串，表示<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.Button>控制和允许的效果是复制或移动。  
  
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
    >  任何数据可作为参数传入`DoDragDrop`方法; 在上例中，<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.Button>控制已使用 （而不是一个值进行硬编码或从数据集检索数据） 因为相关属性从要拖动的位置 (<xref:System.Windows.Forms.Button>控件)。 在将拖放操作合并到基于 Windows 的应用程序中时，请牢记这一点。  
  
 在拖动操作期间生效，你可以处理<xref:System.Windows.Forms.Control.QueryContinueDrag>"询问权限"的事件的系统继续拖动操作。 时处理此方法时，它也是合适的点，您才能调用方法将会影响上拖动操作，例如展开<xref:System.Windows.Forms.TreeNode>中<xref:System.Windows.Forms.TreeView>控制当光标悬停在其上。  
  
## <a name="dropping-data"></a>放置数据  
 开始从 Windows 窗体或控件上的某个位置拖动数据后，当然会想要将其放置在某处。 当光标经过为放置数据而进行了正确配置的窗体或控件区域时，会发生改变。 通过设置接受放置的数据可在 Windows 窗体或控件的任何区域<xref:System.Windows.Forms.Control.AllowDrop%2A>属性和处理<xref:System.Windows.Forms.Control.DragEnter>和<xref:System.Windows.Forms.Control.DragDrop>事件。  
  
#### <a name="to-perform-a-drop"></a>执行放置  
  
1.  设置<xref:System.Windows.Forms.Control.AllowDrop%2A>属性为 true。  
  
2.  在`DragEnter`控件将在其中放置发生，事件确保要拖动的数据的可接受的类型 (在这种情况下， <xref:System.Windows.Forms.Control.Text%2A>)。 代码随后设置下拉发生中的值时将发生这种情况的影响<xref:System.Windows.Forms.DragDropEffects>枚举。 有关详细信息，请参阅<xref:System.Windows.Forms.DragEventArgs.Effect%2A>。  
  
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
    >  你可以定义自己<xref:System.Windows.Forms.DataFormats>通过指定您自己的对象作为<xref:System.Object>参数<xref:System.Windows.Forms.DataObject.SetData%2A>方法。 在进行该操作时，请确保指定的对象可序列化。 有关详细信息，请参阅<xref:System.Runtime.Serialization.ISerializable>。  
  
3.  在<xref:System.Windows.Forms.Control.DragDrop>控件将在其中放置发生，使用事件<xref:System.Windows.Forms.DataObject.GetData%2A>方法来检索要拖动的数据。 有关详细信息，请参阅<xref:System.Security.Cryptography.Xml.DataObject.Data%2A>。  
  
     在示例中，<xref:System.Windows.Forms.TextBox>控件是正在拖动到 （将在其中放置发生） 的控件。 该代码设置<xref:System.Windows.Forms.Control.Text%2A>属性<xref:System.Windows.Forms.TextBox>控制等于要拖动的数据。  
  
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
    >  此外，你可以使用<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>属性，以便根据键按下在拖放操作时，某些效果发生 （例如，它位于标准版，以将拖动的数据复制时按下 CTRL 键）。  
  
## <a name="see-also"></a>请参阅  
 [如何：将数据添加到剪贴板](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [如何：从剪贴板检索数据](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [拖放操作和剪贴板支持](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
