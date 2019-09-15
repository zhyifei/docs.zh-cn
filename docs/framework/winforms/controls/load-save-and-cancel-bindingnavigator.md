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
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991739"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮

控件是一种特殊用途<xref:System.Windows.Forms.ToolStrip>的控件，用于在窗体上导航和操作绑定到数据的控件。 <xref:System.Windows.Forms.BindingNavigator>

由于它是一个<xref:System.Windows.Forms.ToolStrip>控件<xref:System.Windows.Forms.BindingNavigator> ，因此可以轻松修改组件，以包含用户的其他或其他命令。

在下面的过程中， <xref:System.Windows.Forms.TextBox>控件绑定到数据， <xref:System.Windows.Forms.ToolStrip>添加到窗体中的控件将被修改为包含 "加载"、"保存" 和 "取消" 按钮。

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>向 BindingNavigator 组件添加 "加载"、"保存" 和 "取消" 按钮

1. 在 Visual Studio 中，向<xref:System.Windows.Forms.TextBox>窗体添加一个控件。

2. 将其绑定到<xref:System.Windows.Forms.BindingSource>绑定到数据源的。 在<xref:System.Windows.Forms.BindingSource>此示例中，绑定到数据库。

3. 生成数据集和表适配器后，将<xref:System.Windows.Forms.BindingNavigator>控件拖到窗体上。

4. 在绑定到控件<xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>的窗体上，将控件的属性设置为。<xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingSource>

5. 选择 <xref:System.Windows.Forms.BindingNavigator> 控件。

6. 单击智能标记字形（![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），将显示 " **BindingNavigator 任务**" 对话框，然后选择 "**编辑项目**"。

     **项集合编辑器**随即出现。

7. 在**Items 集合编辑器**中，完成以下操作：

    1. 通过<xref:System.Windows.Forms.ToolStripSeparator> <xref:System.Windows.Forms.ToolStripButton>选择适当的类型并单击"添加"按钮，添加一个和三个项。<xref:System.Windows.Forms.ToolStripItem>

    2. 分别将按钮的属性设置为LoadButton、SaveButton和<xref:System.Windows.Forms.ToolStripItem.Name%2A> **CancelButton**。

    3. 将按钮的属性设置为 "加载"、"保存" 和 "取消"。 <xref:System.Windows.Forms.ToolStripItem.Text%2A>

    4. 将每<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>个按钮的属性设置为 "**文本**"。 或者，您可以将此属性设置为**image**或**ImageAndText**，并将该图像设置为<xref:System.Windows.Forms.ToolStripItem.Image%2A>显示在属性中。

    5. 单击“确定”关闭对话框。 这些按钮将添加到<xref:System.Windows.Forms.ToolStrip>。

8. 右键单击窗体，然后选择 "**查看代码**"。

9. 在代码编辑器中，找到将数据加载到表适配器的代码行。 此代码是在步骤2中设置数据绑定时生成的。 此代码应类似于以下内容： `TableAdapterName.Fill(DataSetName.TableName)`。 它最有可能是窗体的<xref:System.Windows.Forms.Form.Load>事件。

10. 为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的**负载** <xref:System.Windows.Forms.ToolStripButton>的事件创建事件处理程序，并将此数据加载到其中。

     你的代码现在应如下所示：

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

11. 为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的**Save** <xref:System.Windows.Forms.ToolStripButton>的事件创建事件处理程序，并编写代码以更新控件所绑定到的表中的数据。

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
    > 在某些情况下， <xref:System.Windows.Forms.BindingNavigator>组件已经有 "**保存**" 按钮，但 Windows 窗体设计器未生成任何代码。 在这种情况下，你可以将前面的代码<xref:System.Windows.Forms.ToolStripItem.Click>放在该按钮的事件处理程序中，而不是<xref:System.Windows.Forms.ToolStrip>在上创建一个全新的按钮。 但是，默认情况下，此按钮处于禁用状态，因此必须<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>将该按钮的属性`true`设置为才能使按钮正常工作。

12. 为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的 "**取消** <xref:System.Windows.Forms.ToolStripButton> " 事件创建事件处理程序，然后编写代码以取消对显示的数据记录所做的任何更改。

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
    > <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>方法的作用域为数据行。 在导航到下一条记录之前，保存在查看单个记录时所做的任何更改。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator 控件](bindingnavigator-control-windows-forms.md)
- [BindingSource 组件概述](bindingsource-component-overview.md)
