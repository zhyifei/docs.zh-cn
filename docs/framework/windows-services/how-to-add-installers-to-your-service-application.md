---
title: "如何：将安装程序添加到服务应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 8137e41f92335849916dfc9e9ce72afeb186e73c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a>如何：将安装程序添加到服务应用程序
Visual Studio 会安装组件，可以安装与你的服务应用程序关联的资源。 安装组件注册到它正在安装并让服务控制管理器知道存在该服务在系统上的某一项服务。 当与服务应用程序时，你可以在属性窗口，自动将适当的安装程序添加到你的项目中选择一个链接。  
  
> [!NOTE]
>  你的服务的属性值将服务类中复制到安装程序类。 如果你更新服务类上的属性值，它们不会自动更新在安装程序。  
  
 将安装程序添加到项目中，新类 (其中，默认情况下，名为`ProjectInstaller`) 中的项目，以及适当的安装选项在其中创建组件的实例创建。 此类的所有安装组件的中心点充当你的项目需要。 例如，如果您将第二个服务添加到你的应用程序，并单击添加安装程序链接，并不会创建第二个安装程序类;相反，第二个服务的必需的其他安装组件将添加到现有的类。  
  
 不需要在要使您正确安装的服务的安装程序中任何特殊编码。 但是，你有时可能需要修改安装程序的内容，如果你需要将特殊的功能添加到安装过程。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-installers-to-your-service-application"></a>将安装程序添加到服务应用程序  
  
1.  在**解决方案资源管理器**，访问**设计**你想要添加的安装组件服务的视图。  
  
2.  本身，而不是它的任何内容，请单击要选择的服务的设计器的背景。  
  
3.  与设计器中焦点，右键单击，然后单击**添加安装程序**。  
  
     一个新的类， `ProjectInstaller`，和两个安装组件，<xref:System.ServiceProcess.ServiceProcessInstaller>和<xref:System.ServiceProcess.ServiceInstaller>，为服务复制到组件添加到你的项目，然后属性值。  
  
4.  单击<xref:System.ServiceProcess.ServiceInstaller>组件并验证的值<xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>属性设置为相同的值<xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>服务本身上的属性。  
  
5.  若要确定你的服务将启动方式如何，请单击<xref:System.ServiceProcess.ServiceInstaller>组件，并且已设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>为适当的值的属性。  
  
    |值|结果|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|安装后必须手动启动该服务。 有关详细信息，请参阅[如何： 启动服务](../../../docs/framework/windows-services/how-to-start-services.md)。|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|该服务将启动时，计算机重新启动。|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|无法启动服务。|  
  
6.  若要确定你的服务将在其中运行的安全上下文，请单击<xref:System.ServiceProcess.ServiceProcessInstaller>组件，并设置适当的属性值。 有关详细信息，请参阅[如何： 指定服务的安全上下文](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)。  
  
7.  重写任何方法，你需要执行自定义处理。  
  
8.  为你的项目中每项附加服务执行步骤 1 至 7。  
  
    > [!NOTE]
    >  对于你的项目中每个其他服务，必须添加其他<xref:System.ServiceProcess.ServiceInstaller>到项目的组件`ProjectInstaller`类。 <xref:System.ServiceProcess.ServiceProcessInstaller>组件添加在步骤 3 中适用于所有项目中的单个服务安装程序。  
  
## <a name="see-also"></a>另请参阅  
 [Windows 服务应用程序简介](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [如何： 安装和卸载服务](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [如何： 启动服务](../../../docs/framework/windows-services/how-to-start-services.md)  
 [如何： 为服务指定的安全上下文](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
