---
title: 在 Windows 服务应用程序中承载
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: e440961055ccd40bf56b4b88ea73d167f1903245
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-in-a-windows-service-application"></a>在 Windows 服务应用程序中承载
Windows 服务（以前称为 Windows NT 服务）提供了一种尤其适合于下面这样的应用程序的进程模型：必须在长时间运行的可执行程序中生存，并且不显示任何形式的用户界面。 Windows 服务应用程序的进程生存期由服务控制管理器 (SCM) 管理，您可以通过该管理器启动、停止和暂停 Windows 服务应用程序。 你可以配置 Windows 服务进程启动计算机，使其成为"始终运行的"应用程序的合适的宿主环境时自动启动。 有关 Windows 服务应用程序的详细信息，请参阅[Windows 服务应用程序](http://go.microsoft.com/fwlink/?LinkId=89450)。  
  
 承载长时间运行 Windows Communication Foundation (WCF) 服务的应用程序与 Windows 服务共享许多特性。 具体而言，WCF 服务是长时间运行服务器的可执行文件并不直接与用户交互，因此未实现任何形式的用户界面。 在这种情况下，托管 Windows 服务应用程序的 WCF 服务是用于构建可靠的、 长时间运行的 WCF 应用程序的一个选项。  
  
 通常情况下，WCF 开发人员必须决定是否承载其 WCF 应用程序是 Windows 服务应用程序或 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 宿主环境内。 在下列条件下，应考虑使用 Windows 服务应用程序：  
  
-   应用程序要求显式激活。 例如，在服务器启动时应用程序必须自动启动（而不是动态启动以响应第一个传入消息）的条件下，应使用 Windows 服务。  
  
-   承载应用程序的进程必须在启动后保持运行状态。 Windows 服务进程一旦启动将一直保持运行状态，直到服务器管理员使用服务控制管理器显式关闭该进程。 在 IIS 或 WAS 中承载的应用程序可能会动态地启动和停止，以便最佳地使用系统资源。 需要显式控制其托管进程的生存期的应用程序应使用 Windows 服务而非 IIS 或 WAS。  
  
-   您的 WCF 服务必须在 Windows Server 2003 上运行，并使用 HTTP 之外的传输。 在 Windows Server 2003 上，[!INCLUDE[iis601](../../../../includes/iis601-md.md)] 宿主环境限制为仅可进行 HTTP 通信。 Windows 服务应用程序不受此限制，并且可以使用任何传输 WCF 支持的功能，包括 net.tcp、 net.pipe 和 net.msmq。  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>在 Windows 服务应用程序内承载 WCF  
  
1.  创建 Windows 服务应用程序。 可以使用 <xref:System.ServiceProcess> 命名空间中的类以托管代码的形式编写 Windows 服务应用程序。 此应用程序必须包含一个继承自 <xref:System.ServiceProcess.ServiceBase> 的类。  
  
2.  WCF 服务的生存期链接到 Windows 服务应用程序的生存期。 通常，人们希望 Windows 服务应用程序，要在宿主服务启动时变为活动状态，请停止侦听消息后，在宿主服务停止，WCF 服务时遇到错误时关闭宿主进程中承载的 WCF 服务。 这可以通过以下操作实现：  
  
    -   重写 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 以打开一个或多个 <xref:System.ServiceModel.ServiceHost> 实例。 一个 Windows 服务应用程序可以承载多个 WCF 服务的启动和停止作为一个组。  
  
    -   重写<xref:System.ServiceProcess.ServiceBase.OnStop%2A>调用<xref:System.ServiceModel.Channels.CommunicationObject.Closed>上<xref:System.ServiceModel.ServiceHost>任何正在运行的 WCF 服务启动期间<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>。  
  
    -   订阅 <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> 的 <xref:System.ServiceModel.ServiceHost> 事件，并使用 <xref:System.ServiceProcess.ServiceController> 类以在出现错误时关闭 Windows 服务应用程序。  
  
     部署和管理方式相同，因为 Windows 服务应用程序不能使用 WCF 的 Windows 服务应用程序承载 WCF 服务。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceProcess>  
 [演练：在组件设计器中创建 Windows 服务应用程序](http://go.microsoft.com/fwlink/?LinkId=94875)  
 [如何：在托管 Windows 服务中承载 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Windows 服务主机](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [服务应用程序编程体系结构](http://go.microsoft.com/fwlink/?LinkId=94876)  
 [Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkId=201276)
