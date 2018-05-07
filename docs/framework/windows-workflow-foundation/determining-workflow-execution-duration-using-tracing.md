---
title: 使用跟踪确定工作流执行持续时间
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: 9f9c65f2c873d54da443db14e7f5797ef1e14174
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>使用跟踪确定工作流执行持续时间
本主题演示如何使用工作流跟踪来确定执行成功完成的自承载工作流所需的时间。  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>使用工作流跟踪来确定工作流应用程序执行的持续时间  
  
1.  打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。  选择**文件**，**新**，**项目**。  下**C#**，选择**工作流**节点。  选择**工作流控制台应用程序**从模板列表中。  将新项目`WorkflowDurationTracing`单击**确定**。  
  
2.  打开 Workflow1.xaml。  将 <xref:System.Activities.Statements.Delay> 活动拖动到设计器图面上。 将值 00:00:10（10 秒）分配给活动的“持续时间”属性。  
  
3.  通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。  
  
4.  如果尚未启用工作流跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**. 选择**视图**，**显示分析和调试日志**。 右键单击**调试**和选择**启用日志**。 使事件查看器保持打开状态，以便在工作流运行后可以查看跟踪。  
  
5.  按 Ctrl+Shift+B 执行工作流应用程序。  
  
6.  在事件查看器中，查找 ID 为 1009 的最新事件和类似于以下内容的消息。 记下记录消息的时间。  
  
 **父 Activity '，DisplayName: '，InstanceId: ' 安排了子 Activity WorkflowDurationTracking.Workflow1、 DisplayName: Workflow1、 InstanceId:"1"。**  
  
7.  查找另一个 ID 为 1001 的最新事件和类似于以下内容的消息。  从此消息的记录值中减去以前的消息时间，以确定工作流执行的持续时间，应该大约为 10 秒钟。  
  
 **WorkflowInstance Id"1bbac57b-3322-498e-9e27-8833fda3a5bf"已完成处于关闭状态。**  
  
## <a name="see-also"></a>请参阅  
 [工作流跟踪](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Windows Server App Fabric 监视](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [使用 App Fabric 监视应用程序](http://go.microsoft.com/fwlink/?LinkId=201275)
