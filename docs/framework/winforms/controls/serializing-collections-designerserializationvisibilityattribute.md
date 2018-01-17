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
ms.openlocfilehash: 060f411dfc7c3153fdf0e0d6e19781f0d60b141b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合
你自定义控件有时将公开为属性的集合。 本演练演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>类来控制在设计时序列化集合的方式。 应用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>对您集合的属性的值可确保将序列化属性。  
  
 若要将代码复制本主题中的一个单独的清单，请参阅[如何： 序列化集合的标准类型与 DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   若要能够创建和运行 Windows 窗体应用程序项目的计算机上安装了 Visual Studio 的足够权限。  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>创建控件都有一个可序列化集合  
 第一步是创建具有可序列化集合作为属性的控件。 你可以编辑此集合使用的内容**集合编辑器**，使用户能够从**属性**窗口。  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>若要创建与可序列化集合的控件  
  
1.  创建一个名为的 Windows 控件库项目`SerializationDemoControlLib`。 有关详细信息，请参阅[Windows 控件库模板](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4)。  
  
2.  重命名`UserControl1`到`SerializationDemoControl`。 有关详细信息，请参阅[如何： 重命名标识符](http://msdn.microsoft.com/en-us/2430f732-2b70-4516-8cf6-a7bb71cc9724)。  
  
3.  在**属性**窗口中，设置的值<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>属性`10`。  
  
4.  位置<xref:System.Windows.Forms.TextBox>中控制`SerializationDemoControl`。  
  
5.  选择 <xref:System.Windows.Forms.TextBox> 控件。 在**属性**窗口中，设置以下属性。  
  
    |属性|更改为|  
    |--------------|---------------|  
    |**多行**|`true`|  
    |**停靠**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**滚动条**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  在**代码编辑器**，声明一个名为的字符串数组字段`stringsValue`中`SerializationDemoControl`。  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  定义`Strings`属性`SerializationDemoControl`。  
  
> [!NOTE]
>  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>值用于启用序列化的集合。  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  按 F5 生成项目并在“UserControl 测试容器”中运行该控件。  
  
2.  查找`Strings`中的属性<xref:System.Windows.Forms.PropertyGrid>的**UserControl 测试容器**。 单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.  
  
3.  输入中的多个字符串**字符串集合编辑器**。 通过按 ENTER 键末尾的每个字符串分隔。 单击**确定**在完成输入字符串时。  
  
> [!NOTE]
>  您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。  
  
## <a name="serializing-a-collection-property"></a>序列化集合属性  
 若要测试你的控件的序列化行为，才会将其放在窗体上，并更改与该集合的内容**集合编辑器**。 可以通过查看特殊的设计器文件，在其中看到的序列化的集合状态**Windows 窗体设计器**发出代码。  
  
#### <a name="to-serialize-a-collection"></a>要序列化集合  
  
1.  将 Windows 应用程序项目添加到解决方案。 将项目命名为 `SerializationDemoControlTest`。  
  
2.  在**工具箱**，查找名为选项卡**SerializationDemoControlLib 组件**。 在此选项卡上，你将找到`SerializationDemoControl`。 有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。  
  
3.  位置`SerializationDemoControl`窗体上。  
  
4.  查找`Strings`中的属性**属性**窗口。 单击`Strings`属性，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**字符串集合编辑器**.  
  
5.  键入在几个字符串**字符串集合编辑器**。 通过按 ENTER 键末尾的每个字符串分隔。 单击**确定**在完成输入字符串时。  
  
> [!NOTE]
>  您键入的字符串出现在<xref:System.Windows.Forms.TextBox>的`SerializationDemoControl`。  
  
1.  在“解决方案资源管理器”中，单击“显示所有文件”按钮。  
  
2.  打开**Form1**节点。 它是名为的文件的下方**Form1.Designer.cs**或**Form1.Designer.vb**。 这是在其中的文件**Windows 窗体设计器**发出代码，表示窗体及其子控件的设计时状态。 在“代码编辑器”中打开此文件。  
  
3.  打开调用的区域**Windows 窗体设计器生成的代码**并查找标记为部分**serializationDemoControl1**。 在此标签下是控件的表示序列化的状态的代码。 键入在步骤 5 中的字符串出现在向赋值`Strings`属性。 下面的代码示例用 C# 和 Visual Basic 中，显示代码类似于你将看到的内容类型字符串"red"、"橙色"和"黄色"。  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  在**代码编辑器**，更改的值<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>上`Strings`属性<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>。  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. 重新生成解决方案和重复执行步骤 3 和 4。  
  
> [!NOTE]
>  在这种情况下， **Windows 窗体设计器**不发出任何分配到`Strings`属性。  
  
## <a name="next-steps"></a>后续步骤  
 一次你知道如何序列化标准类型的集合，请考虑将自定义控件更深入地集成到设计时环境。 以下主题介绍如何增强你自定义控件的设计时集成：  
  
-   [设计时体系结构](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Windows 窗体控件中的特性](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [设计器的序列化概述](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [设计器的序列化概述](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [如何： 序列化与 DesignerSerializationVisibilityAttribute 标准类型的集合](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
