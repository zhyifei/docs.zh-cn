---
title: 如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 8f331c67dd22a6a9e2382ecc11d23c67cd2a5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮
<xref:System.Windows.Forms.BindingNavigator>控件是特殊用途<xref:System.Windows.Forms.ToolStrip>旨在用于导航和操作窗体上的控件绑定到数据的控件。  
  
 因为它是<xref:System.Windows.Forms.ToolStrip>控件，<xref:System.Windows.Forms.BindingNavigator>组件可以轻松地修改为包括附加或替代用户的命令。  
  
 在下面的过程中，<xref:System.Windows.Forms.TextBox>控件绑定到数据，与<xref:System.Windows.Forms.ToolStrip>控件添加到窗体修改为包括负载，保存、 和取消按钮。  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>若要添加负载，保存和取消按钮 BindingNavigator 组件  
  
1.  向窗体添加一个 <xref:System.Windows.Forms.TextBox> 控件。  
  
2.  将其绑定到<xref:System.Windows.Forms.BindingSource>，后者绑定到数据源。 对于此示例，<xref:System.Windows.Forms.BindingSource>绑定到数据库。  
  
3.  生成数据集和表适配器后，将拖动<xref:System.Windows.Forms.BindingNavigator>到窗体控件。  
  
4.  设置<xref:System.Windows.Forms.BindingNavigator>控件的<xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>属性<xref:System.Windows.Forms.BindingSource>绑定到控件的窗体上。  
  
5.  选择 <xref:System.Windows.Forms.BindingNavigator> 控件。  
  
6.  单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 因此**BindingNavigator 任务**对话框并选择**编辑项**.  
  
     **项集合编辑器**显示。  
  
7.  在**项集合编辑器**，完成以下操作：  
  
    1.  添加<xref:System.Windows.Forms.ToolStripSeparator>和三个<xref:System.Windows.Forms.ToolStripButton>通过选择适当的类型的项<xref:System.Windows.Forms.ToolStripItem>并单击**添加**按钮。  
  
    2.  设置<xref:System.Windows.Forms.ToolStripItem.Name%2A>到这些按钮属性**LoadButton**，**SaveButton**，和**CancelButton**分别。  
  
    3.  设置<xref:System.Windows.Forms.ToolStripItem.Text%2A>到这些按钮属性**负载**`,` **保存**，和**取消**。  
  
    4.  设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>的按钮添加到每个属性**文本**。 或者，可以将此属性设置为**映像**或**ImageAndText**并设置中显示的图像<xref:System.Windows.Forms.ToolStripItem.Image%2A>属性。  
  
    5.  单击**确定**以关闭对话框。按钮会添加到<xref:System.Windows.Forms.ToolStrip>。  
  
8.  右键单击该表单，然后选择**查看代码**。  
  
9. 在代码编辑器中，找到将数据加载到表适配器的代码的行。 设置在步骤 2 中的数据绑定时，已生成此代码。 代码应类似于以下： `TableAdapterName.Fill(DataSetName.TableName)`。 它将最有可能是窗体的<xref:System.Windows.Forms.Form.Load>事件。  
  
10. 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**负载**<xref:System.Windows.Forms.ToolStripButton>您之前创建并将此数据加载代码移动到其中。  
  
     现在，你的代码应类似于以下：  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**保存**<xref:System.Windows.Forms.ToolStripButton>之前创建并编写代码以更新表控件内的数据绑定到。  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  在某些情况下，<xref:System.Windows.Forms.BindingNavigator>组件将已有**保存**按钮，但没有代码将由生成的 Windows 窗体设计器。 在这种情况下，你可以将放置在前面的代码<xref:System.Windows.Forms.ToolStripItem.Click>有关该按钮，而不是创建一个全新的按钮上的事件处理程序<xref:System.Windows.Forms.ToolStrip>。 但是，按钮默认处于禁用状态，因此必须设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>到按钮属性`true`正确具有按钮函数。  
  
12. 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**取消**<xref:System.Windows.Forms.ToolStripButton>之前创建并编写代码来取消对显示的数据记录的任何更改。  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>方法作用于数据的行。 保存在导航到下一条记录之前查看该单个记录时所做的任何更改。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [BindingNavigator 控件](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [BindingSource 组件概述](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
