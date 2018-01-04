---
title: "如何：以编程方式编写服务"
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
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a>如何：以编程方式编写服务
如果你选择不使用 Windows 服务项目模板，你可以通过设置继承和其他基础结构元素自己编写你自己的服务。 当以编程方式创建服务时，你必须执行该模板将为您处理的几个步骤：  
  
-   必须设置服务类继承自<xref:System.ServiceProcess.ServiceBase>类。  
  
-   你必须创建`Main`用于定义要运行的服务的服务项目和调用方法<xref:System.ServiceProcess.ServiceBase.Run%2A>对它们的方法。  
  
-   必须重写<xref:System.ServiceProcess.ServiceBase.OnStart%2A>和<xref:System.ServiceProcess.ServiceBase.OnStop%2A>过程和任何代码填写你想要运行。  
  
### <a name="to-write-a-service-programmatically"></a>若要以编程方式编写服务  
  
1.  按照这些步骤创建必要的命名空间的引用并创建一个空项目：  
  
    1.  在**解决方案资源管理器**，右键单击**引用**节点，然后单击**添加引用**。  
  
    2.  上**.NET Framework**选项卡上，向下滚动到**System.dll**单击**选择**。  
  
    3.  滚动到**System.ServiceProcess.dll**单击**选择**。  
  
    4.  单击 **“确定”**。  
  
2.  添加类并将其配置为从继承<xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  添加以下代码来配置你的服务类：  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  创建`Main`方法为您的类，并用它来定义你的类将包含; 的服务`userService1`是类的名称：  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  重写<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法，并定义你希望你的服务启动时执行任何的处理。  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  替代你想要定义自定义，处理的任何其他方法，并编写代码来确定服务中每种情况下应采取的操作。  
  
7.  添加服务应用程序所必需的安装程序。 有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。  
  
8.  通过选择生成你的项目**生成解决方案**从**生成**菜单。  
  
    > [!NOTE]
    >  不要通过按 F5 来运行你的项目 — 你无法通过这种方式运行服务项目。  
  
9. 创建安装项目和安装你的服务的自定义操作。 有关示例，请参阅[演练： 在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)。  
  
10. 安装服务。 有关更多信息，请参见 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [如何：记录关于服务的信息](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [演练：在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
