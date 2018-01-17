---
title: "服务应用程序编程体系结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a>服务应用程序编程体系结构
Windows 服务应用程序都基于从继承的类<xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>类。 重写此类的方法，并为这些表来确定你的服务的行为方式定义功能。  
  
 所涉及的服务创建的主类如下：  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>-您重写方法从<xref:System.ServiceProcess.ServiceBase>类创建服务时，并定义代码，以确定如何在此您服务的函数继承类。  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>和<xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType>-使用这些类用于安装和卸载你的服务。  
  
 此外，类名为<xref:System.ServiceProcess.ServiceController>可用于操作服务本身。 此类不参与创建服务，但可以用于启动和停止该服务，将命令传递到它，并返回一系列的枚举。  
  
## <a name="defining-your-services-behavior"></a>定义你的服务行为  
 在服务类中，您重写基类函数，以确定你的服务的状态更改服务控制管理器中时，会发生什么情况。 <xref:System.ServiceProcess.ServiceBase>类公开以下方法，可以重写以添加自定义行为。  
  
|方法|重写到|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|指示在你的服务开始运行时，应采取哪些措施。 在此过程中为你的服务以执行有用的工作，必须编写代码。|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|指示当你的服务已暂停时应发生。|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|指示当你的服务停止运行时应发生。|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|指示当你的服务后继续正常工作正在暂停时应发生。|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|指示应发生之前你的系统关闭，如果你的服务运行在该时间。|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|指示当你的服务接收自定义命令时应发生。 自定义命令的详细信息，请参阅 MSDN 联机。|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|指示服务应如何响应收到电源管理事件时，如电池电量不足或挂起的操作。|  
  
> [!NOTE]
>  这些方法表示在其生存期内; 通过将移动的服务的状态服务从一个状态转换到下一步。 例如，你将永远不会使服务正常响应<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>命令之前<xref:System.ServiceProcess.ServiceBase.OnStart%2A>已调用。  
  
 有几个其他属性和方法所感兴趣。 这些方法包括：  
  
-   <xref:System.ServiceProcess.ServiceBase.Run%2A>方法<xref:System.ServiceProcess.ServiceBase>类。 这是服务的主入口点。 当你创建使用 Windows 服务模板的服务时，在你的应用程序中插入代码`Main`方法以运行服务。 此代码类似如下所示：  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  这些示例使用类型的数组<xref:System.ServiceProcess.ServiceBase>、 在其中可以添加你的应用程序包含每个服务，并随后的所有服务可以运行在一起。 如果你仅创建单一服务，但是，你可以选择不使用数组而只是声明新对象继承自<xref:System.ServiceProcess.ServiceBase>，然后运行它。 有关示例，请参阅[如何： 编写服务以编程方式](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)。  
  
-   上的属性的一系列<xref:System.ServiceProcess.ServiceBase>类。 这些文件确定何种方法可以在服务上调用。 例如，当<xref:System.ServiceProcess.ServiceBase.CanStop%2A>属性设置为`true`、<xref:System.ServiceProcess.ServiceBase.OnStop%2A>可以调用在服务上的方法。 当<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>属性设置为`true`、<xref:System.ServiceProcess.ServiceBase.OnPause%2A>和<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>方法可以调用。 当你将设置到这些属性之一`true`，然后应重写，并为关联的方法定义处理。  
  
    > [!NOTE]
    >  你的服务必须重写至少<xref:System.ServiceProcess.ServiceBase.OnStart%2A>和<xref:System.ServiceProcess.ServiceBase.OnStop%2A>才有用。  
  
 你还可以使用名为的组件<xref:System.ServiceProcess.ServiceController>与进行通信并控制现有服务的行为。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)
