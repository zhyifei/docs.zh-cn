---
title: "演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合"
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
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0267020f7e7a52e92b05a0bda0ee397e5c3393fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="7b0e5-102">演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="7b0e5-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="7b0e5-103">你自定义控件有时将公开为属性的集合。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="7b0e5-104">本演练演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>类来控制在设计时序列化集合的方式。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="7b0e5-105">应用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>对您集合的属性的值可确保将序列化属性。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="7b0e5-106">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 序列化集合的标准类型与 DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0e5-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7b0e5-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7b0e5-109">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b0e5-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="7b0e5-110">Prerequisites</span></span>  
 <span data-ttu-id="7b0e5-111">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="7b0e5-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="7b0e5-112">若要能够创建和运行 Windows 窗体应用程序项目的计算机上安装了 Visual Studio 的足够权限。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="7b0e5-113">创建控件都有一个可序列化集合</span><span class="sxs-lookup"><span data-stu-id="7b0e5-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="7b0e5-114">第一步是创建具有可序列化集合作为属性的控件。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="7b0e5-115">你可以编辑此集合使用的内容**集合编辑器**，使用户能够从**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="7b0e5-116">若要创建与可序列化集合的控件</span><span class="sxs-lookup"><span data-stu-id="7b0e5-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="7b0e5-117">创建一个名为的 Windows 控件库项目`SerializationDemoControlLib`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="7b0e5-118">有关详细信息，请参阅[Windows 控件库模板](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-118">For more information, see [Windows Control Library Template](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="7b0e5-119">重命名`UserControl1`到`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="7b0e5-120">有关详细信息，请参阅[如何： 重命名标识符](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724)。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-120">For more information, see [How to: Rename Identifiers](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span></span>  
  
3.  <span data-ttu-id="7b0e5-121">在**属性**窗口中，设置的值<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>属性`10`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="7b0e5-122">位置<xref:System.Windows.Forms.TextBox>中控制`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="7b0e5-123">选择 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="7b0e5-124">在**属性**窗口中，设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="7b0e5-125">属性</span><span class="sxs-lookup"><span data-stu-id="7b0e5-125">Property</span></span>|<span data-ttu-id="7b0e5-126">更改为</span><span class="sxs-lookup"><span data-stu-id="7b0e5-126">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="7b0e5-127">**多行**</span><span class="sxs-lookup"><span data-stu-id="7b0e5-127">**Multiline**</span></span>|`true`|  
    |<span data-ttu-id="7b0e5-128">**Dock**</span><span class="sxs-lookup"><span data-stu-id="7b0e5-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |<span data-ttu-id="7b0e5-129">**滚动条**</span><span class="sxs-lookup"><span data-stu-id="7b0e5-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |<span data-ttu-id="7b0e5-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="7b0e5-130">**ReadOnly**</span></span>|`true`|  
  
6.  <span data-ttu-id="7b0e5-131">在**代码编辑器**，声明一个名为的字符串数组字段`stringsValue`中`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="7b0e5-132">定义`Strings`属性`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0e5-133"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>值用于启用序列化的集合。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="7b0e5-134">按 F5 生成项目并在“UserControl 测试容器”中运行该控件。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="7b0e5-135">查找`Strings`中的属性<xref:System.Windows.Forms.PropertyGrid>的**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="7b0e5-136">单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.</span><span class="sxs-lookup"><span data-stu-id="7b0e5-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="7b0e5-137">输入中的多个字符串**字符串集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="7b0e5-138">通过按 ENTER 键末尾的每个字符串分隔。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="7b0e5-139">单击**确定**在完成输入字符串时。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0e5-140">您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="7b0e5-141">序列化集合属性</span><span class="sxs-lookup"><span data-stu-id="7b0e5-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="7b0e5-142">若要测试你的控件的序列化行为，才会将其放在窗体上，并更改与该集合的内容**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="7b0e5-143">可以通过查看特殊的设计器文件，在其中看到的序列化的集合状态**Windows 窗体设计器**发出代码。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="7b0e5-144">要序列化集合</span><span class="sxs-lookup"><span data-stu-id="7b0e5-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="7b0e5-145">将 Windows 应用程序项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="7b0e5-146">将项目命名为 `SerializationDemoControlTest`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="7b0e5-147">在**工具箱**，查找名为选项卡**SerializationDemoControlLib 组件**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="7b0e5-148">在此选项卡上，你将找到`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="7b0e5-149">有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="7b0e5-150">位置`SerializationDemoControl`窗体上。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="7b0e5-151">查找`Strings`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="7b0e5-152">单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.</span><span class="sxs-lookup"><span data-stu-id="7b0e5-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="7b0e5-153">键入在几个字符串**字符串集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="7b0e5-154">通过按 ENTER 键末尾的每个字符串分隔。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="7b0e5-155">单击**确定**在完成输入字符串时。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0e5-156">您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="7b0e5-157">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="7b0e5-158">打开**Form1**节点。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-158">Open the **Form1** node.</span></span> <span data-ttu-id="7b0e5-159">它是名为的文件的下方**Form1.Designer.cs**或**Form1.Designer.vb**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="7b0e5-160">这是在其中的文件**Windows 窗体设计器**发出代码，表示窗体及其子控件的设计时状态。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="7b0e5-161">在“代码编辑器”中打开此文件。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="7b0e5-162">打开调用的区域**Windows 窗体设计器生成的代码**并查找标记为部分**serializationDemoControl1**。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="7b0e5-163">在此标签下是控件的表示序列化的状态的代码。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="7b0e5-164">键入在步骤 5 中的字符串出现在向赋值`Strings`属性。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="7b0e5-165">下面的代码示例用 C# 和 Visual Basic 中，显示代码类似于你将看到的内容类型字符串"red"、"橙色"和"黄色"。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="7b0e5-166">在**代码编辑器**，更改的值<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>上`Strings`属性<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="7b0e5-167">重新生成解决方案和重复执行步骤 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0e5-168">在这种情况下， **Windows 窗体设计器**不发出任何分配到`Strings`属性。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b0e5-169">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7b0e5-169">Next Steps</span></span>  
 <span data-ttu-id="7b0e5-170">一次你知道如何序列化标准类型的集合，请考虑将自定义控件更深入地集成到设计时环境。</span><span class="sxs-lookup"><span data-stu-id="7b0e5-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="7b0e5-171">以下主题介绍如何增强你自定义控件的设计时集成：</span><span class="sxs-lookup"><span data-stu-id="7b0e5-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   [<span data-ttu-id="7b0e5-172">设计时体系结构</span><span class="sxs-lookup"><span data-stu-id="7b0e5-172">Design-Time Architecture</span></span>](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [<span data-ttu-id="7b0e5-173">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="7b0e5-173">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [<span data-ttu-id="7b0e5-174">设计器的序列化概述</span><span class="sxs-lookup"><span data-stu-id="7b0e5-174">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [<span data-ttu-id="7b0e5-175">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7b0e5-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b0e5-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b0e5-176">See Also</span></span>  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [<span data-ttu-id="7b0e5-177">设计器的序列化概述</span><span class="sxs-lookup"><span data-stu-id="7b0e5-177">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [<span data-ttu-id="7b0e5-178">如何： 序列化与 DesignerSerializationVisibilityAttribute 标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="7b0e5-178">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [<span data-ttu-id="7b0e5-179">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="7b0e5-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
