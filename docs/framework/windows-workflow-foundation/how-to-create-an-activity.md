---
title: "如何：创建活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a3b9698d6a060120addff52e6600916a2de19fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-activity"></a>如何：创建活动
活动是 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 中的核心行为单元。 活动的执行逻辑可以使用托管代码实现，也可以使用其他活动实现。 本主题演示如何创建两个活动。 第一个活动是简单活动，它使用代码来实现其执行逻辑。 第二个活动的实现是用其他活动定义的。 后续教程步骤会使用这些活动。  
  
> [!NOTE]
>  若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。  
  
### <a name="to-create-the-activity-library-project"></a>创建活动库项目  
  
1.  打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]选择**新建**，**项目**从**文件**菜单。  
  
2.  展开**其他项目类型**中的节点**已安装**，**模板**列表并选择**Visual Studio 解决方案**。  
  
3.  选择**空白解决方案**从**Visual Studio 解决方案**列表。 请确保在 .NET Framework 版本下拉列表中选择 **“.NET Framework 4.5”** 。 类型`WF45GettingStartedTutorial`中**名称**中，然后单击**确定**。  
  
4.  右键单击**WF45GettingStartedTutorial**中**解决方案资源管理器**选择**添加**，**新项目**。  
  
    > [!TIP]
    >  如果未显示 **解决方案资源管理器** 窗口，请从 **“视图”** 菜单选择 **“解决方案资源管理器** 。  
  
5.  在 **“已安装”** 节点中，选择 **“Visual C#”**、 **“工作流”** （或 **“Visual Basic”**、 **“工作流”**）。 确保**.NET Framework 4.5**中选择[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]版本下拉列表。 选择**活动库**从**工作流**列表。 类型`NumberGuessWorkflowActivities`中**名称**中，然后单击**确定**。  
  
    > [!NOTE]
    >  根据的编程语言配置为主要语言中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]、 **Visual C#**或**Visual Basic**节点可能位于**其他语言**中的节点**已安装**节点。  
  
6.  右键单击**Activity1.xaml**中**解决方案资源管理器**选择**删除**。 单击 **“确定”** 以确认。  
  
### <a name="to-create-the-readint-activity"></a>创建 ReadInt 活动  
  
1.  选择**添加新项**从**项目**菜单。  
  
2.  在**已安装**，**通用项**节点中，选择**工作流**。 选择**代码活动**从**工作流**列表。  
  
3.  类型`ReadInt`到**名称**中，然后单击**添加**。  
  
4.  将现有的 `ReadInt` 定义替换为下面的定义。  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  `ReadInt` 活动派生自 <xref:System.Activities.NativeActivity%601> 而不是 <xref:System.Activities.CodeActivity>，这是默认的代码活动模板。 如果活动提供单个结果，可以使用 <xref:System.Activities.CodeActivity%601>，它是通过 <xref:System.Activities.Activity%601.Result%2A> 参数公开的，但是 <xref:System.Activities.CodeActivity%601> 不支持使用书签，因此使用 <xref:System.Activities.NativeActivity%601>。  
  
### <a name="to-create-the-prompt-activity"></a>创建 Prompt 活动  
  
1.  按 Ctrl+Shift+B 生成项目。 通过生成项目，可以使用此项目中的 `ReadInt` 活动生成此步骤中的自定义活动。  
  
2.  选择**添加新项**从**项目**菜单。  
  
3.  在**已安装**，**通用项**节点中，选择**工作流**。 选择**活动**从**工作流**列表。  
  
4.  类型`Prompt`到**名称**中，然后单击**添加**。  
  
5.  双击**Prompt.xaml**中**解决方案资源管理器**以将其显示在设计器中，如果未显示。  
  
6.  单击**参数**左下方的活动设计器以显示**参数**窗格。  
  
7.  单击**创建自变量**。  
  
8.  类型`BookmarkName`到**名称**框中，选择**中**从**方向**下拉列表中，选择**字符串**从**自变量类型**下拉列表，然后按 ENTER 保存该自变量。  
  
9. 单击**创建自变量**。  
  
10. 类型`Result`到**名称**是下新添加的框`BookmarkName`自变量中，选择**出**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER。  
  
11. 单击**创建自变量**。  
  
12. 类型`Text`到**名称**框中，选择**中**从**方向**下拉列表中，选择**字符串**从**自变量类型**下拉列表，然后按 ENTER 保存该自变量。  
  
     在以下步骤中，这三个参数将绑定到添加到 <xref:System.Activities.Statements.WriteLine> 活动中的 `ReadInt` 和 `Prompt` 活动的相应参数。  
  
13. 单击**参数**要关闭的活动设计器左下方**参数**窗格。  
  
14. 拖动**序列**活动从**控制流**部分**工具箱**拖放到**将活动拖至此处**标签**提示**活动设计器。  
  
    > [!TIP]
    >  如果**工具箱**不显示窗口中，选择**工具箱**从**视图**菜单。  
  
15. 拖动**WriteLine**活动从**基元**部分**工具箱**拖放到**将活动拖至此处**标签**序列**活动。  
  
16. 将绑定**文本**参数**WriteLine**活动**文本**参数**提示**通过键入活动`Text`到**输入 C# 表达式**或**输入 VB 表达式**框中**属性**窗口中，然后按 TAB 键两次。 这会关闭 IntelliSense 列表成员窗口，并通过将选择范围移离属性保存属性值。 此外可以通过键入设置此属性`Text`到**输入 C# 表达式**或**输入 VB 表达式**在活动本身的框。  
  
    > [!TIP]
    >  如果**属性窗口**未显示，选择**属性窗口**从**视图**菜单。  
  
17. 拖动**ReadInt**活动从**NumberGuessWorkflowActivities**部分**工具箱**拖放**序列**活动使其**WriteLine**活动。  
  
18. 将绑定**BookmarkName**参数**ReadInt**活动**BookmarkName**参数**提示**通过键入活动`BookmarkName`到**输入 VB 表达式**右侧的框中**BookmarkName**中的参数**属性窗口**，然后按 TAB 键两个以下情况下关闭 IntelliSense 列表成员窗口并保存属性。  
  
19. 将绑定**结果**参数**ReadInt**活动**结果**参数**提示**通过键入活动`Result`到**输入 VB 表达式**右侧的框中**结果**中的参数**属性窗口**，然后按 TAB 键两次。  
  
20. 按 Ctrl+Shift+B 生成解决方案。  
  
     有关说明如何使用这些活动创建工作流在本教程，请参阅下一步[如何： 创建工作流](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [设计和实现自定义活动](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [入门教程](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [如何：创建工作流](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [在自定义活动设计器中使用 ExpressionTextBox](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
