---
title: "Windows 服务应用程序介绍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 613107a13820ad71b854dcba93f21c41f2a5fa5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-windows-service-applications"></a>Windows 服务应用程序介绍
Microsoft Windows 服务，以前称为 NT 服务，可以创建长时间运行的可执行应用程序在其自己的 Windows 会话中运行。 这些服务可以自动启动启动计算机后，可以暂停和重新启动，并且没有显示任何用户界面。 这些功能使服务最适用于在服务器上或每当您需要不干扰其他工作的用户可以在同一台计算机上的长时间运行功能。 此外可以在不同于登录的用户的特定用户帐户或默认计算机帐户的安全上下文中运行服务。 有关服务和 Windows 会话的详细信息，请参阅 Windows SDK 文档。  
  
 通过创建作为服务安装的应用程序，可以轻松创建服务。 例如，假设你想要监视性能计数器数据和响应阈值的值。 您无法编写一个 Windows 服务应用程序侦听的性能计数器数据、 部署应用程序，并开始收集和分析数据。  
  
 创建你的服务为 Microsoft Visual Studio 项目，定义控制哪些命令中它的代码可以发送给服务，收到的这些命令时，应采取哪些措施。 可以发送到服务的命令包括启动、 暂停、 继续和停止服务;你还可以执行自定义命令。  
  
 创建和生成应用程序后，你可以通过运行 InstallUtil.exe 的命令行实用工具并将路径传递给服务的可执行文件来安装它。 然后，可以使用**服务控制管理器**来启动、 停止、 暂停、 继续和配置你的服务。 你可以完成这些任务在中的许多**服务**中的节点**服务器资源管理器**或通过使用<xref:System.ServiceProcess.ServiceController>类。  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>服务应用程序 vs。其他 Visual Studio 应用程序  
 服务应用程序以不同的方式从以下几种方式的许多其他项目类型的函数：  
  
-   必须在服务器上安装的服务应用程序项目创建的已编译可执行文件，项目才能以有意义的方式。 你无法调试或通过按 F5 或 F11; 运行服务应用程序你不能入其代码立即运行服务或步骤。 相反，你必须安装并启动你的服务，然后将调试器附加到服务的进程。 有关详细信息，请参阅[如何： 调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)。  
  
-   与某些类型的项目，你必须创建服务应用程序的安装组件。 安装组件安装和注册的服务器上的服务并与 Windows 创建你的服务的条目**服务控制管理器**。 有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。  
  
-   `Main`方法的服务应用程序必须发出运行命令的服务你的项目包含。 `Run`方法加载到服务**服务控制管理器**相应服务器上。 如果你使用**Windows 服务**项目模板中，此方法为你自动编写。 请注意，加载服务不是一样启动该服务。 请参阅"服务"下面的生存期的详细信息。  
  
-   在不同的窗口工作站比登录的用户的交互区域中运行 Windows 服务应用程序。 窗口工作站是包含剪贴板、 一套通用原子和一组桌面对象的安全对象。 由于 Windows 服务的工作站不是交互式的工作站，对话框从引发内 Windows 服务应用程序将不会被发现，并且可能导致程序停止响应。 同样，错误消息应该在 Windows 事件日志中记录而不是在用户界面中引发。  
  
     .NET Framework 支持的 Windows 服务类不支持与交互式工作站，即，登录的用户交互。 .NET Framework 还不包括表示工作站和桌面的类。 如果你的 Windows 服务必须与其他工作站进行交互，你将需要访问非托管的 Windows API。 有关详细信息，请参阅 Windows SDK 文档。  
  
     Windows 服务与用户或其他工作站必须谨慎地设计进行某些情况，例如因为没有登录的用户或用户具有一组意外的桌面的对象进行交互。 在某些情况下，它可能更适合编写的 Windows 应用程序运行在用户的控制之下。  
  
-   Windows 服务应用程序在其自己的安全上下文中运行，并在用户登录之前启动到 Windows 计算机在其安装它们。 你应仔细规划哪些用户帐户来运行服务在服务内;在系统帐户下运行的服务有更多的权限和特权的用户帐户比。  
  
## <a name="service-lifetime"></a>服务生存期  
 服务在其生存期内经历若干内部状态。 首先，它将在其运行的系统上安装了服务。 此过程执行的安装程序服务项目并将加载到服务**服务控制管理器**为该计算机。 **服务控制管理器**是由 Windows 管理服务提供的中央实用程序。  
  
 加载服务完毕后，它必须启动。 启动该服务使它可以开始正常运行。 你可以从服务**服务控制管理器**，从**服务器资源管理器**，或从通过调用代码<xref:System.ServiceProcess.ServiceController.Start%2A>方法。 <xref:System.ServiceProcess.ServiceController.Start%2A>方法将处理传递给应用程序的<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法并处理已那里定义的任何代码。  
  
 无限期地直到它被停止或暂停或计算机关机，此状态中只能存在正在运行的服务。 服务可能存在三个基本状态中的一个： <xref:System.ServiceProcess.ServiceControllerStatus.Running>， <xref:System.ServiceProcess.ServiceControllerStatus.Paused>，或<xref:System.ServiceProcess.ServiceControllerStatus.Stopped>。 服务还可以报告挂起命令的状态： <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>， <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>， <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>，或<xref:System.ServiceProcess.ServiceControllerStatus.StopPending>。 这些状态指示命令已发出，如命令暂停正在运行的服务，但尚未执行。 您可以查询<xref:System.ServiceProcess.ServiceController.Status%2A>以确定何种状态服务是在中，也可以使用<xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>执行操作时任何这些状态时发生。  
  
 你可以暂停、 停止或恢复服务的步骤从**服务控制管理器**，从**服务器资源管理器**，或通过在代码中调用方法。 每个这些操作可以在服务中调用的关联的过程 (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>， <xref:System.ServiceProcess.ServiceBase.OnPause%2A>，或<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>)，在其中可以定义服务更改状态时要执行其他处理。  
  
## <a name="types-of-services"></a>类型的服务  
 有两种类型的服务可以使用.NET Framework 的 Visual Studio 中创建。 在进程中的唯一服务的服务分配类型<xref:System.ServiceProcess.ServiceType.Win32OwnProcess>。 与其他服务共享一个进程的服务分配类型<xref:System.ServiceProcess.ServiceType.Win32ShareProcess>。 你可以通过查询检索的服务类型<xref:System.ServiceProcess.ServiceController.ServiceType%2A>属性。  
  
 如果查询未在 Visual Studio 中创建的现有服务，你偶尔可能会看到其他的服务类型。 有关详细信息，请参阅<xref:System.ServiceProcess.ServiceType>。  
  
## <a name="services-and-the-servicecontroller-component"></a>服务和 ServiceController 组件  
 <xref:System.ServiceProcess.ServiceController>组件将用于连接到已安装的服务和操作其状态; 使用<xref:System.ServiceProcess.ServiceController>组件时，可以启动和停止服务、 暂停和继续其工作正常，以及向服务发送自定义命令。 但是，不需要使用<xref:System.ServiceProcess.ServiceController>组件创建服务应用程序时。 事实上，在大多数情况下你<xref:System.ServiceProcess.ServiceController>组件应存在于的 Windows 服务应用程序定义你的服务提供单独的应用程序。  
  
 有关详细信息，请参阅<xref:System.ServiceProcess.ServiceController>。  
  
## <a name="requirements"></a>惠?  
  
-   必须在创建服务**Windows 服务**应用程序项目或另一个已启用.NET Framework – 项目创建时生成的.exe 文件，并继承自<xref:System.ServiceProcess.ServiceBase>类。  
  
-   包含 Windows 服务的项目必须对于项目以及其服务的安装组件。 这可以轻松地实现从**属性**窗口。 有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序](../../../docs/framework/windows-services/index.md)  
 [服务应用程序编程体系结构](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [如何：安装和卸载服务](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [如何：启动服务](../../../docs/framework/windows-services/how-to-start-services.md)  
 [如何：调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [演练：在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
