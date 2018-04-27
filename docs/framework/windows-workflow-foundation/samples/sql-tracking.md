---
title: SQL 跟踪
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2eeb5cf57e6efac77de4a76fe8131189273d5438
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="sql-tracking"></a>SQL 跟踪
此示例演示如何编写一个自定义 SQL 跟踪参与者，该参与者将跟踪记录写入到一个 SQL 数据库。 Windows Workflow Foundation (WF) 提供工作流跟踪以查看工作流实例的执行。 跟踪运行时在工作流执行过程中会发出工作流跟踪记录。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 工作流跟踪，请参阅[工作流跟踪](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  确认您已安装 SQL Server 2008、 SQL Server 2008 Express 或更新版本。 与示例打包在一起的脚本假定在您的本地计算机上使用 SQL Express 实例。 如果您安装了不同的实例，请在运行此示例之前修改与数据库相关的脚本。  
  
2.  通过在脚本目录 (\WF\Basic\Tracking\SqlTracking\CS\Scripts) 中运行 Trackingsetup.cmd 来创建 SQL Server 跟踪数据库。 这会创建一个名为 TrackingSample 的数据库。  
  
    > [!NOTE]
    >  脚本将在 SQL Express 的默认实例上创建该数据库。 如果您想在不同的数据库实例上安装该数据库，请编辑 Trackingsetup.cmd 脚本。  
  
3.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 SqlTrackingSample.sln。  
  
4.  按 Ctrl+Shift+B 生成解决方案。  
  
5.  按 F5 运行该应用程序。  
  
     浏览器窗口打开和显示侦听应用程序的目录。  
  
6.  在浏览器中，单击 StockPriceService.xamlx。  
  
7.  浏览器显示 StockPriceService 页，其中包含本地服务 WSDL 地址。 复制此地址。  
  
     本地服务 WSDL 地址的一个示例是http://localhost:65193/StockPriceService.xamlx?wsdl。  
  
8.  使用 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，运行 WCF 测试客户端 (WcfTestClient.exe)。 它位于 Microsoft Visual Studio 10.0\Common7\IDE 目录下。  
  
9. 在 WCF 测试客户端中，单击**文件**菜单，然后选择**添加服务**。 将本地服务地址粘贴到文本框中。 单击**确定**关闭对话框。  
  
10. 在 WCF 测试客户端中，双击**GetStockPrice**。 这将打开`GetStockPrice`采用一个参数，值中的类型的操作`Contoso`单击**Invoke**。  
  
11. 发出的跟踪记录将写入一个 SQL 数据库中。 若要查看跟踪记录，请在 SQL Management Studio 中打开 TrackingSample 数据库，然后导航到表。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] SQL Server Management Studio，请参阅[SQL Server Management Studio 简介](http://go.microsoft.com/fwlink/?LinkId=165645)。 可以下载 SQL Server 2008 Management Studio Express[此处](http://go.microsoft.com/fwlink/?LinkId=180520)。 对表运行一个选择查询，将显示存储在相关表中的跟踪记录内的数据。  
  
#### <a name="to-uninstall-the-sample"></a>卸载此示例  
  
1.  在示例目录 (\WF\Basic\Tracking\SqlTracking) 中运行 Trackingcleanup.cmd 脚本。  
  
    > [!NOTE]
    >  Trackingcleanup.cmd 将尝试删除本地计算机 SQL Express 中的数据库。 如果您使用的是其他 SQL Server 实例，请编辑 Trackingcleanup.cmd。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>请参阅  
 [AppFabric 监视示例](http://go.microsoft.com/fwlink/?LinkId=193959)
