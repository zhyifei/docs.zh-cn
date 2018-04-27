---
title: 任务 1：创建一个新的 Windows Presentation Foundation 应用程序
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd21013331e19fa9e18ad7cbee0a7bb07abaf3d2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>任务 1：创建一个新的 Windows Presentation Foundation 应用程序
在此任务中，你将使用 WPF 应用程序 Visual Studio 模板创建空的 Windows Presentation Foundation (WPF) 应用程序并添加对相应的引用[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]工作流程序集。  
  
### <a name="to-create-the-wpf-application-project"></a>创建 WPF 应用程序项目  
  
1.  打开 Visual Studio 并在**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在**新项目**对话框框中，选择**Visual C#** 或**Visual Basic**从**已安装的模板**的左侧窗格中框。 如果未出现所选的语言，查找在**其他语言**。  
  
3.  选择**Windows**中**已安装的模板**窗格。  
  
4.  在顶部窗格中，确认 （默认值） **.NET Framework 4**已选定在下拉列表框中，然后选择**WPF 应用程序**。  
  
5.  设置到项目的名称**HostingApplication**在窗口的底部。  
  
6.  将解决方案名称设置为**RehostingTheDesigner**。  
  
7.  单击**确定**创建应用程序项目。 Visual Studio 创建你的应用程序一个基本 WPF UI，并包括相应的 XAML 和代码隐藏文件。  
  
8.  将引用添加到**WorkflowModel**程序集。 为此，请在**解决方案资源管理器**，右键单击**HostingApplication**项目，然后选择**添加引用**。  
  
9. 在**添加引用**对话框中，单击 **.NET**选项卡上，请按住 CTRL 键，选择下列程序集，，然后单击**确定**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. 单击 **“确定”**。  
  
11. 请参阅[任务 2： 承载工作流设计器](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)若要了解如何承载工作流设计器设计画布。  
  
## <a name="see-also"></a>请参阅  
 [重新托管工作流设计器](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [任务 2：托管工作流设计器](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
