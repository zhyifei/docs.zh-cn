---
title: "如何：使用 Windows Server App Fabric 承载工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 69911b2baf0e184957158ac536fa2271524cb2ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>如何：使用 Windows Server App Fabric 承载工作流服务
在 App Fabric 中承载工作流服务类似于在 IIS/WAS 下承载。 唯一的区别在于 App Fabric 提供的用于部署、监控和管理工作流服务的工具。 本主题使用在创建的工作流服务[创建长时间运行工作流服务](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)。 本主题将指导您创建工作流服务。 本主题将介绍如何使用 App Fabric 承载工作流服务。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Windows Server App Fabric，请参阅[Windows Server App Fabric 文档](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)。 完成以下步骤之前，请确保已安装 Windows Server App Fabric。  为此，请打开 Internet Information services (inetmgr.exe)，请单击服务器名称**连接**查看，单击站点，然后单击**Default Web Site**。 在屏幕的右侧，你应该看到名为一节**App Fabric**。 如果您看不到这一部分（它位于右侧窗格的顶部），则表示您还未安装 App Fabric。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]安装 Windows Server App Fabric 请参阅[安装 Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136)。  
  
### <a name="creating-a-simple-workflow-service"></a>创建简单工作流服务  
  
1.  打开[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]和加载 OrderProcessing 解决方案中创建[创建长时间运行工作流服务](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)主题。  
  
2.  右键单击**OrderService**项目，然后选择**属性**和选择**Web**选项卡。  
  
3.  在**启动操作**部分的属性页上，选择**特定页**和编辑框中键入 Service1.xamlx。  
  
4.  在**服务器**部分的属性页上，选择**使用本地 IIS Web 服务器**并键入以下 URL: `http://localhost/OrderService`。  
  
5.  单击**创建虚拟目录**按钮。 这将新建一个虚拟目录，并将项目设置为在生成项目时将所需文件复制到此虚拟目录。  或者，您也可以手动将 .xamlx、web.config 以及任何所需的 DLL 复制到此虚拟目录。  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>配置承载于 Windows Server App Fabric 中的工作流服务  
  
1.  打开 Internet 信息服务管理器 (inetmgr.exe)。  
  
2.  导航到 OrderService 虚拟目录中**连接**窗格。  
  
3.  右击 OrderService 并选择**管理 WCF 和 WF 服务**，**配置...**. **为应用程序配置 WCF 和 WF**对话框随即显示。  
  
4.  选择**常规**选项卡以显示有关应用程序的常规信息，如下面的屏幕快照中所示。  
  
     ![常规选项卡上的应用程序结构配置对话框](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-常规")  
  
5.  选择**监视**选项卡。这将显示各种监控设置，如下面的屏幕快照所示。  
  
     ![应用程序结构配置监视选项卡](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration 监视")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]配置在 App Fabric 中的工作流服务监视请参阅[配置使用 App Fabric 监视](http://go.microsoft.com/fwlink/?LinkId=193153)。  
  
6.  选择**工作流持久性**选项卡。这样，您可以将应用程序配置为使用 App Fabric 的默认暂留提供程序，如下面的屏幕快照所示。  
  
     ![应用程序结构配置 &#45;持久性](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration 持久性")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]在 Windows Server App Fabric 中配置工作流持久性请参阅[App Fabric 中配置工作流持久性](http://go.microsoft.com/fwlink/?LinkId=193148)。  
  
7.  选择**工作流主机管理**选项卡。这样，您可以指定何时应卸载和暂留空闲的工作流服务实例，如下面的屏幕快照所示。  
  
     ![应用程序结构配置工作流主机管理](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration 管理")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]配置工作流主机管理，请参阅[App Fabric 中配置工作流主机管理](http://go.microsoft.com/fwlink/?LinkId=193151)。  
  
8.  选择**自动启动**选项卡。这样，您可以为应用程序中的工作流服务指定自动启动设置，如下面的屏幕快照所示。  
  
     ![应用程序结构自动 &#45; 开始配置](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]配置自动启动请参阅[使用 App Fabric 配置的自动启动](http://go.microsoft.com/fwlink/?LinkId=193150)。  
  
9. 选择**限制**选项卡。这样，您可以为工作流服务配置限制设置，如下面的屏幕快照所示。  
  
     ![应用程序结构配置限制](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]请参阅配置限制[配置限制使用 App Fabric](http://go.microsoft.com/fwlink/?LinkId=193149)。  
  
10. 选择**安全**选项卡。这样，您可以为应用程序配置安全设置，如下面的屏幕快照所示。  
  
     ![应用程序结构安全性配置](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration 安全")  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]请参阅使用 Windows Server App Fabric 中配置安全性[使用 App Fabric 中配置安全性](http://go.microsoft.com/fwlink/?LinkId=193152)。  
  
### <a name="using-windows-server-app-fabric"></a>使用 Windows Server App Fabric  
  
1.  生成解决方案以便将所需的文件复制到虚拟目录。  
  
2.  右键单击 OrderClient 项目，然后选择**调试**，**启动新实例**以启动客户端应用程序。  
  
3.  客户端的运行时间以及 Visual Studio 将显示**附加安全警告**对话框中，单击**不附加**按钮。 这会告知 Visual Studio 不要附加到 IIS 进程进行调试。  
  
4.  客户端应用程序将立即调用工作流服务，然后等待。 工作流服务将转为空闲暂留状态。 通过启动 Internet 信息服务 (inetmgr.exe)，在“连接”窗格中导航至 OrderService 并将其选中，可以对此进行验证。 接下来，单击右侧窗格中的“App Fabric 仪表板”图标。 在“暂留的 WF 实例”下，您将看到存在一个暂留的工作流服务实例，如下面的屏幕快照所示。  
  
     ![App Fabric 仪表板](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")  
  
     **WF 实例历史记录**列出有关工作流服务的工作流服务激活次数、 工作流服务实例的完成数等包含失败操作的工作流实例数的信息。 在活动或空闲实例下将显示一个链接，单击此链接将显示更多有关空闲工作流实例的信息，如下面的屏幕快照所示。  
  
     ![持久化工作流实例详细信息](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")  
  
     有关 Windows Server App Fabric 功能以及如何使用它们查看[Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)  
  
## <a name="see-also"></a>另请参阅  
 [创建长时间运行工作流服务](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)  
 [Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkId=193143)  
 [安装 Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136)  
 [Windows Server App Fabric 文档](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)
