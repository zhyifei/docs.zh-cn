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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>演练：在 Windows 窗体中执行拖放操作
要在基于 Windows 的应用程序中执行拖放操作，必须处理一系列事件，其中最著名的是<xref:System.Windows.Forms.Control.DragEnter>，<xref:System.Windows.Forms.Control.DragLeave>和<xref:System.Windows.Forms.Control.DragDrop>事件。 通过使用这些事件的事件参数中的可用信息，可以轻松地实现拖放操作。  
  
## <a name="dragging-data"></a>拖动数据  
 所有拖放操作都从拖动开始。 在<xref:System.Windows.Forms.Control.DoDragDrop%2A>方法中实现了在方法中实现在拖动开始时启用收集数据的功能。  
  
 在下面的示例中，<xref:System.Windows.Forms.Control.MouseDown>该事件用于启动拖动操作，因为它是最直观的（大多数拖放操作从按下鼠标按钮开始）。 但是，请记住，任何事件都可用于启动拖放过程。  
  
> [!NOTE]
> 某些控件具有特定于拖动的自定义事件。 <xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件，例如，有一个<xref:System.Windows.Forms.TreeView.ItemDrag>事件。  
  
#### <a name="to-start-a-drag-operation"></a>启动拖动操作  
  
1. 对于将开始<xref:System.Windows.Forms.Control.MouseDown>拖动的控件，使用`DoDragDrop`方法设置要拖动的数据，并且允许的效果拖动将具有。 有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 和 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>。  
  
     下面的示例演示如何启动拖动操作。 拖动开始的控件是<xref:System.Windows.Forms.Button>控件，要拖动的数据是表示控件<xref:System.Windows.Forms.Control.Text%2A>属性的<xref:System.Windows.Forms.Button>字符串，允许的效果是复制或移动。  
  
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
    > 任何数据都可以用作`DoDragDrop`方法中的参数;在上面的示例中，使用了<xref:System.Windows.Forms.Control.Text%2A><xref:System.Windows.Forms.Button>控件的属性（而不是硬编码值或从数据集检索数据），因为该属性与从中拖动的位置（<xref:System.Windows.Forms.Button>控件）相关。 在将拖放操作合并到基于 Windows 的应用程序中时，请牢记这一点。  
  
 当拖动操作有效时，您可以处理<xref:System.Windows.Forms.Control.QueryContinueDrag>事件，该事件"请求"系统的权限以继续拖动操作。 处理此方法时，调用对拖动操作有影响的方法也是适当的点，例如当光标悬停在<xref:System.Windows.Forms.TreeNode><xref:System.Windows.Forms.TreeView>控件上时展开 控件中的 。  
  
## <a name="dropping-data"></a>放置数据  
 开始从 Windows 窗体或控件上的某个位置拖动数据后，当然会想要将其放置在某处。 当光标经过为放置数据而进行了正确配置的窗体或控件区域时，会发生改变。 可以通过设置<xref:System.Windows.Forms.Control.AllowDrop%2A>属性和处理<xref:System.Windows.Forms.Control.DragEnter>和<xref:System.Windows.Forms.Control.DragDrop>事件来使 Windows 窗体或控件中的任何区域接受丢弃的数据。  
  
#### <a name="to-perform-a-drop"></a>执行放置  
  
1. 将<xref:System.Windows.Forms.Control.AllowDrop%2A>属性设置为 true。  
  
2. 对于`DragEnter`发生丢弃的控件，请确保拖动的数据是可接受的类型（在本例中为<xref:System.Windows.Forms.Control.Text%2A>）。 然后，代码设置在枚举中<xref:System.Windows.Forms.DragDropEffects>放置到值时将发生的效果。 有关详细信息，请参阅 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>。  
  
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
    > 可以通过将自己的对象指定<xref:System.Windows.Forms.DataFormats>为方法的<xref:System.Object>参数来<xref:System.Windows.Forms.DataObject.SetData%2A>定义您自己的对象。 在进行该操作时，请确保指定的对象可序列化。 有关详细信息，请参阅 <xref:System.Runtime.Serialization.ISerializable>。  
  
3. 对于<xref:System.Windows.Forms.Control.DragDrop>发生放置的控件，使用 方法<xref:System.Windows.Forms.DataObject.GetData%2A>检索要拖动的数据。 有关详细信息，请参阅 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>。  
  
     在下面的示例中，<xref:System.Windows.Forms.TextBox>控件是拖动到（将发生丢弃的位置）的控件。 代码设置控件<xref:System.Windows.Forms.Control.Text%2A>的属性<xref:System.Windows.Forms.TextBox>等于要拖动的数据。  
  
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
    > 此外，您可以使用 该<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>属性，以便根据拖放操作期间按下的键，会发生某些效果（例如，在按下 CTRL 键时复制拖动的数据是标准）。  
  
## <a name="see-also"></a>另请参阅

- [如何：将数据添加到剪贴板](how-to-add-data-to-the-clipboard.md)
- [如何：从剪贴板检索数据](how-to-retrieve-data-from-the-clipboard.md)
- [拖放操作和剪贴板支持](drag-and-drop-operations-and-clipboard-support.md)
