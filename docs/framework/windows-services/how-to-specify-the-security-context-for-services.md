---
title: 如何：为服务指定安全上下文
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
manager: douge
ms.openlocfilehash: e3e5ad7dd44dcaf1593ac80bbe6d0a367964e4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-security-context-for-services"></a>如何：为服务指定安全上下文
默认情况下，服务以外的登录的用户的不同的安全上下文中运行。 默认的系统帐户的上下文中运行的服务调用`LocalSystem`，这将给予他们不同的访问权限到用户以外的系统资源。 你可以更改此行为，以指定应在其下运行你的服务的不同用户帐户。  
  
 通过操作设置的安全上下文<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>服务在其中运行的进程的属性。 此属性可以将服务设置为四种帐户类型之一：  
  
-   `User`这会导致系统提示输入有效的用户名和密码，该服务已安装且由网络; 上的单一用户指定的帐户的上下文中运行时  
  
-   `LocalService`用于充当在本地计算机上的非特权用户，并向任意远程服务器; 提供匿名凭据的帐户的上下文中运行  
  
-   `LocalSystem`其中提供了广泛的本地权限，并提供了向任意远程服务器; 的计算机的凭据的帐户的上下文中运行  
  
-   `NetworkService`其中用作在本地计算机上的非特权用户，并提供向任意远程服务器的计算机的凭据的帐户的上下文中运行。  
  
 有关详细信息，请参见 <xref:System.ServiceProcess.ServiceAccount> 枚举。  
  
### <a name="to-specify-the-security-context-for-a-service"></a>指定服务的安全上下文  
  
1.  创建你的服务之后, 添加为其所必需的安装。 有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。  
  
2.  在设计器中，访问`ProjectInstaller`类并单击你正在使用的服务的服务过程安装。  
  
    > [!NOTE]
    >  对于每个服务应用程序中，有中的至少两个安装组件`ProjectInstaller`类-一个项目，并为该应用程序包含每个服务的一个安装程序在安装所有服务的进程。 在此情况下，你想要选择<xref:System.ServiceProcess.ServiceProcessInstaller>。  
  
3.  在**属性**窗口中，设置<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>为适当的值。  
  
## <a name="see-also"></a>请参阅  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)
