---
title: 演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211601"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="60c21-102">演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="60c21-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="60c21-103">自定义控件有时将公开为属性的集合。</span><span class="sxs-lookup"><span data-stu-id="60c21-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="60c21-104">本演练演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>类来控制在设计时序列化集合的方式。</span><span class="sxs-lookup"><span data-stu-id="60c21-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="60c21-105">将应用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>到集合属性的值可确保将序列化属性。</span><span class="sxs-lookup"><span data-stu-id="60c21-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="60c21-106">要将本主题中的代码作为单个列表进行复制，请参阅[如何：序列化使用 DesignerSerializationVisibilityAttribute 标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="60c21-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60c21-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="60c21-107">Prerequisites</span></span>

<span data-ttu-id="60c21-108">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="60c21-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="60c21-109">创建具有可序列化集合的控件</span><span class="sxs-lookup"><span data-stu-id="60c21-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="60c21-110">第一步是创建具有可序列化集合作为属性的控件。</span><span class="sxs-lookup"><span data-stu-id="60c21-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="60c21-111">您可以编辑此集合使用的内容**集合编辑器**，使用户能够从**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="60c21-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="60c21-112">在 Visual Studio 中，创建一个名为 Windows 控件库项目`SerializationDemoControlLib`。</span><span class="sxs-lookup"><span data-stu-id="60c21-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="60c21-113">有关详细信息，请参阅[Windows 控件库模板](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="60c21-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="60c21-114">重命名`UserControl1`到`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="60c21-115">有关详细信息，请参阅[重命名代码符号重构](/visualstudio/ide/reference/rename)。</span><span class="sxs-lookup"><span data-stu-id="60c21-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="60c21-116">在中**属性**窗口中，设置的值<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>属性设置为`10`。</span><span class="sxs-lookup"><span data-stu-id="60c21-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="60c21-117">位置<xref:System.Windows.Forms.TextBox>控件中`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="60c21-118">选择 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="60c21-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="60c21-119">在中**属性**窗口中，设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="60c21-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="60c21-120">属性</span><span class="sxs-lookup"><span data-stu-id="60c21-120">Property</span></span>|<span data-ttu-id="60c21-121">更改为</span><span class="sxs-lookup"><span data-stu-id="60c21-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="60c21-122">**多行**</span><span class="sxs-lookup"><span data-stu-id="60c21-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="60c21-123">**Dock**</span><span class="sxs-lookup"><span data-stu-id="60c21-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="60c21-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="60c21-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="60c21-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="60c21-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="60c21-126">在中**代码编辑器**，声明一个名为的字符串数组字段`stringsValue`中`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="60c21-127">定义`Strings`属性上的`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="60c21-128"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>值用于启用序列化的集合。</span><span class="sxs-lookup"><span data-stu-id="60c21-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="60c21-129">按**F5**以生成项目，然后运行控件**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="60c21-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="60c21-130">查找`Strings`中的属性<xref:System.Windows.Forms.PropertyGrid>的**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="60c21-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="60c21-131">单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.</span><span class="sxs-lookup"><span data-stu-id="60c21-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="60c21-132">输入中的多个字符串**字符串集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="60c21-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="60c21-133">通过按分隔**Enter**密钥在每个字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="60c21-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="60c21-134">单击**确定**完后输入字符串。</span><span class="sxs-lookup"><span data-stu-id="60c21-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="60c21-135">您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="60c21-136">序列化集合属性</span><span class="sxs-lookup"><span data-stu-id="60c21-136">Serializing a Collection Property</span></span>

<span data-ttu-id="60c21-137">若要测试您的控件的序列化行为，会将其放在窗体上并更改与集合中的内容**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="60c21-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="60c21-138">可以通过查看特殊的设计器文件，在其中看到序列化的集合状态**Windows 窗体设计器**发出的代码。</span><span class="sxs-lookup"><span data-stu-id="60c21-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="60c21-139">序列化集合</span><span class="sxs-lookup"><span data-stu-id="60c21-139">To serialize a collection</span></span>

1. <span data-ttu-id="60c21-140">向解决方案添加一个 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="60c21-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="60c21-141">将项目命名为 `SerializationDemoControlTest`。</span><span class="sxs-lookup"><span data-stu-id="60c21-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="60c21-142">在中**工具箱**，找到名为选项卡**SerializationDemoControlLib 组件**。</span><span class="sxs-lookup"><span data-stu-id="60c21-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="60c21-143">在此选项卡上，您会发现`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="60c21-144">有关详细信息，请参见[演练：自动填充工具箱与自定义组件](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="60c21-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="60c21-145">位置`SerializationDemoControl`窗体上。</span><span class="sxs-lookup"><span data-stu-id="60c21-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="60c21-146">查找`Strings`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="60c21-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="60c21-147">单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.</span><span class="sxs-lookup"><span data-stu-id="60c21-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="60c21-148">键入在多个字符串**字符串集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="60c21-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="60c21-149">分隔通过按每个字符串的末尾处的 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="60c21-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="60c21-150">单击**确定**完后输入字符串。</span><span class="sxs-lookup"><span data-stu-id="60c21-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="60c21-151">您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="60c21-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="60c21-152">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="60c21-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="60c21-153">打开**Form1**节点。</span><span class="sxs-lookup"><span data-stu-id="60c21-153">Open the **Form1** node.</span></span> <span data-ttu-id="60c21-154">它是名为的文件下**Form1.Designer.cs**或**Form1.Designer.vb**。</span><span class="sxs-lookup"><span data-stu-id="60c21-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="60c21-155">这是在其中的文件**Windows 窗体设计器**发出代码，表示窗体及其子控件的设计时状态。</span><span class="sxs-lookup"><span data-stu-id="60c21-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="60c21-156">在“代码编辑器”中打开此文件。</span><span class="sxs-lookup"><span data-stu-id="60c21-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="60c21-157">打开名为的区域**Windows 窗体设计器生成的代码**并找到标记为部分**serializationDemoControl1**。</span><span class="sxs-lookup"><span data-stu-id="60c21-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="60c21-158">在此标签下是表示控件的序列化的状态的代码。</span><span class="sxs-lookup"><span data-stu-id="60c21-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="60c21-159">键入在步骤 5 中的字符串出现在赋值`Strings`属性。</span><span class="sxs-lookup"><span data-stu-id="60c21-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="60c21-160">C# 和 Visual Basic 中的以下代码示例显示的代码类似于您将看到的内容键入字符串"red"、"橙色"和"黄色"。</span><span class="sxs-lookup"><span data-stu-id="60c21-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="60c21-161">在中**代码编辑器**，更改的值<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>上`Strings`属性设置为<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>。</span><span class="sxs-lookup"><span data-stu-id="60c21-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="60c21-162">重新生成解决方案和重复执行步骤 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="60c21-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="60c21-163">在这种情况下， **Windows 窗体设计器**发出分配给`Strings`属性。</span><span class="sxs-lookup"><span data-stu-id="60c21-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="60c21-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="60c21-164">Next Steps</span></span>

<span data-ttu-id="60c21-165">一旦您知道如何进行序列化标准类型的集合，请考虑将你的自定义控件更深入地集成到设计时环境。</span><span class="sxs-lookup"><span data-stu-id="60c21-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="60c21-166">以下主题介绍如何增强你的自定义控件的设计时集成：</span><span class="sxs-lookup"><span data-stu-id="60c21-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="60c21-167">[设计时体系结构](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="60c21-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="60c21-168">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="60c21-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="60c21-169">[设计器序列化概述](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="60c21-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="60c21-170">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="60c21-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="60c21-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="60c21-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="60c21-172">[设计器序列化概述](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="60c21-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="60c21-173">[如何：序列化使用 DesignerSerializationVisibilityAttribute 标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="60c21-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="60c21-174">演练：自动填充工具箱与自定义组件</span><span class="sxs-lookup"><span data-stu-id="60c21-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
