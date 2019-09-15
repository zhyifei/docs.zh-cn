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
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="d9481-102">如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="d9481-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="d9481-103">控件是一种特殊用途<xref:System.Windows.Forms.ToolStrip>的控件，用于在窗体上导航和操作绑定到数据的控件。 <xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="d9481-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="d9481-104">由于它是一个<xref:System.Windows.Forms.ToolStrip>控件<xref:System.Windows.Forms.BindingNavigator> ，因此可以轻松修改组件，以包含用户的其他或其他命令。</span><span class="sxs-lookup"><span data-stu-id="d9481-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="d9481-105">在下面的过程中， <xref:System.Windows.Forms.TextBox>控件绑定到数据， <xref:System.Windows.Forms.ToolStrip>添加到窗体中的控件将被修改为包含 "加载"、"保存" 和 "取消" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d9481-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="d9481-106">向 BindingNavigator 组件添加 "加载"、"保存" 和 "取消" 按钮</span><span class="sxs-lookup"><span data-stu-id="d9481-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="d9481-107">在 Visual Studio 中，向<xref:System.Windows.Forms.TextBox>窗体添加一个控件。</span><span class="sxs-lookup"><span data-stu-id="d9481-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="d9481-108">将其绑定到<xref:System.Windows.Forms.BindingSource>绑定到数据源的。</span><span class="sxs-lookup"><span data-stu-id="d9481-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="d9481-109">在<xref:System.Windows.Forms.BindingSource>此示例中，绑定到数据库。</span><span class="sxs-lookup"><span data-stu-id="d9481-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="d9481-110">生成数据集和表适配器后，将<xref:System.Windows.Forms.BindingNavigator>控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="d9481-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="d9481-111">在绑定到控件<xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>的窗体上，将控件的属性设置为。<xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="d9481-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="d9481-112">选择 <xref:System.Windows.Forms.BindingNavigator> 控件。</span><span class="sxs-lookup"><span data-stu-id="d9481-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="d9481-113">单击智能标记字形（![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），将显示 " **BindingNavigator 任务**" 对话框，然后选择 "**编辑项目**"。</span><span class="sxs-lookup"><span data-stu-id="d9481-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="d9481-114">**项集合编辑器**随即出现。</span><span class="sxs-lookup"><span data-stu-id="d9481-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="d9481-115">在**Items 集合编辑器**中，完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9481-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="d9481-116">通过<xref:System.Windows.Forms.ToolStripSeparator> <xref:System.Windows.Forms.ToolStripButton>选择适当的类型并单击"添加"按钮，添加一个和三个项。<xref:System.Windows.Forms.ToolStripItem></span><span class="sxs-lookup"><span data-stu-id="d9481-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="d9481-117">分别将按钮的属性设置为LoadButton、SaveButton和<xref:System.Windows.Forms.ToolStripItem.Name%2A> **CancelButton**。</span><span class="sxs-lookup"><span data-stu-id="d9481-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="d9481-118">将按钮的属性设置为 "加载"、"保存" 和 "取消"。 <xref:System.Windows.Forms.ToolStripItem.Text%2A></span><span class="sxs-lookup"><span data-stu-id="d9481-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="d9481-119">将每<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>个按钮的属性设置为 "**文本**"。</span><span class="sxs-lookup"><span data-stu-id="d9481-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="d9481-120">或者，您可以将此属性设置为**image**或**ImageAndText**，并将该图像设置为<xref:System.Windows.Forms.ToolStripItem.Image%2A>显示在属性中。</span><span class="sxs-lookup"><span data-stu-id="d9481-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="d9481-121">单击“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d9481-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="d9481-122">这些按钮将添加到<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="d9481-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="d9481-123">右键单击窗体，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="d9481-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="d9481-124">在代码编辑器中，找到将数据加载到表适配器的代码行。</span><span class="sxs-lookup"><span data-stu-id="d9481-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="d9481-125">此代码是在步骤2中设置数据绑定时生成的。</span><span class="sxs-lookup"><span data-stu-id="d9481-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="d9481-126">此代码应类似于以下内容： `TableAdapterName.Fill(DataSetName.TableName)`。</span><span class="sxs-lookup"><span data-stu-id="d9481-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="d9481-127">它最有可能是窗体的<xref:System.Windows.Forms.Form.Load>事件。</span><span class="sxs-lookup"><span data-stu-id="d9481-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="d9481-128">为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的**负载** <xref:System.Windows.Forms.ToolStripButton>的事件创建事件处理程序，并将此数据加载到其中。</span><span class="sxs-lookup"><span data-stu-id="d9481-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="d9481-129">你的代码现在应如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9481-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="d9481-130">为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的**Save** <xref:System.Windows.Forms.ToolStripButton>的事件创建事件处理程序，并编写代码以更新控件所绑定到的表中的数据。</span><span class="sxs-lookup"><span data-stu-id="d9481-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="d9481-131">在某些情况下， <xref:System.Windows.Forms.BindingNavigator>组件已经有 "**保存**" 按钮，但 Windows 窗体设计器未生成任何代码。</span><span class="sxs-lookup"><span data-stu-id="d9481-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="d9481-132">在这种情况下，你可以将前面的代码<xref:System.Windows.Forms.ToolStripItem.Click>放在该按钮的事件处理程序中，而不是<xref:System.Windows.Forms.ToolStrip>在上创建一个全新的按钮。</span><span class="sxs-lookup"><span data-stu-id="d9481-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="d9481-133">但是，默认情况下，此按钮处于禁用状态，因此必须<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>将该按钮的属性`true`设置为才能使按钮正常工作。</span><span class="sxs-lookup"><span data-stu-id="d9481-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="d9481-134">为<xref:System.Windows.Forms.ToolStripItem.Click>之前创建的 "**取消** <xref:System.Windows.Forms.ToolStripButton> " 事件创建事件处理程序，然后编写代码以取消对显示的数据记录所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d9481-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="d9481-135"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A>方法的作用域为数据行。</span><span class="sxs-lookup"><span data-stu-id="d9481-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="d9481-136">在导航到下一条记录之前，保存在查看单个记录时所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d9481-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9481-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9481-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="d9481-138">BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="d9481-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="d9481-139">BindingSource 组件概述</span><span class="sxs-lookup"><span data-stu-id="d9481-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
