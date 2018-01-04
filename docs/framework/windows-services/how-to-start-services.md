---
title: "如何：启动服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 8352edaa9386adc1fbf3057c6e98f5a9cf9ce4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-start-services"></a>如何：启动服务
安装的服务后，必须启动。 从开始调用<xref:System.ServiceProcess.ServiceBase.OnStart%2A>服务类的方法。 通常情况下，<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法定义有用的服务将执行的工作。 服务启动后，它保持活动状态直到被手动暂停或停止。  
  
 服务可以设置自动或手动启动。 重新启动或首次打开在其安装的计算机时，将启动服务，它会自动启动。 用户必须启动手动启动服务。  
  
> [!NOTE]
>  默认情况下，使用创建服务[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]设置为手动启动。  
  
 有几种方法，你可以手动启动服务 — 从**服务器资源管理器**，从**服务控制管理器**，或代码中使用的组件调用<xref:System.ServiceProcess.ServiceController>。  
  
 你设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性<xref:System.ServiceProcess.ServiceInstaller>类以确定是否应手动或自动启动服务。  
  
### <a name="to-specify-how-a-service-should-start"></a>若要指定服务应如何启动  
  
1.  创建你的服务之后, 添加为其所必需的安装。 有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。  
  
2.  在设计器中，单击的服务安装程序正在使用的服务。  
  
3.  在**属性**窗口中，设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性设置为以下项之一：  
  
    |若要安装服务|将此值设置|  
    |----------------------------------|--------------------|  
    |重新启动计算机|**自动**|  
    |当显式用户操作启动服务|**手动**|  
  
    > [!TIP]
    >  若要防止根本正在启动你的服务，可以设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性**禁用**。 如果你将多次重新启动服务器，并想要通过阻止通常会启动中启动的服务可以节省时间，你可能需要这样做。  
  
    > [!NOTE]
    >  安装你的服务后，可以更改这些属性和其他属性。  
  
     有几种方法可以启动服务具有其<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>过程设置为**手动**-从**服务器资源管理器**，从**Windows 服务控制管理器**，或从代码。 务必要注意并非所有这些方法实际的上下文中启动服务**服务控制管理器**;**服务器资源管理器**和启动服务的编程方法实际操作控制器。  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>若要从服务器资源管理器中手动启动服务  
  
1.  在**服务器资源管理器**，添加所需如果未列出的服务器。 有关详细信息，请参阅如何： 访问和初始化服务器资源管理器数据库资源管理器。  
  
2.  展开**服务**节点，然后找到你想要启动的服务。  
  
3.  右键单击服务名称，然后单击**启动**。  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>若要手动启动服务从服务控制管理器  
  
1.  打开**服务控制管理器**通过执行下列操作之一：  
  
    -   在 Windows XP 和 2000 Professional 中，右键单击**我的电脑**桌面，，然后单击**管理**。 在显示的对话框中，展开**服务和应用程序**节点。  
  
         \- 或 -  
  
    -   在 Windows Server 2003 和 Windows 2000 Server 中，单击**启动**，指向**程序**，单击**管理工具**，然后单击**服务**.  
  
        > [!NOTE]
        >  在 Windows NT 4.0 版中，你可以打开此对话框中，从**控制面板**。  
  
     现在，你应看到您的服务列在**服务**窗口部分。  
  
2.  选择你的服务列表中，右键单击它，，然后单击**启动**。  
  
### <a name="to-manually-start-a-service-from-code"></a>若要从代码中手动启动服务  
  
1.  创建的实例<xref:System.ServiceProcess.ServiceController>类，并将其配置为与你想要管理的服务进行交互。  
  
2.  调用 <xref:System.ServiceProcess.ServiceController.Start%2A> 方法以启动该服务。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
