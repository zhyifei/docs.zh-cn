---
title: "如何：为服务指定安全上下文"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 50a9c6ff7f02cda4475aa5390181fa5d410af161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="9ce69-102">如何：为服务指定安全上下文</span><span class="sxs-lookup"><span data-stu-id="9ce69-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="9ce69-103">默认情况下，服务以外的登录的用户的不同的安全上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="9ce69-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="9ce69-104">默认的系统帐户的上下文中运行的服务调用`LocalSystem`，这将给予他们不同的访问权限到用户以外的系统资源。</span><span class="sxs-lookup"><span data-stu-id="9ce69-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="9ce69-105">你可以更改此行为，以指定应在其下运行你的服务的不同用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9ce69-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="9ce69-106">通过操作设置的安全上下文<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>服务在其中运行的进程的属性。</span><span class="sxs-lookup"><span data-stu-id="9ce69-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="9ce69-107">此属性可以将服务设置为四种帐户类型之一：</span><span class="sxs-lookup"><span data-stu-id="9ce69-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="9ce69-108">`User`这会导致系统提示输入有效的用户名和密码，该服务已安装且由网络; 上的单一用户指定的帐户的上下文中运行时</span><span class="sxs-lookup"><span data-stu-id="9ce69-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="9ce69-109">`LocalService`用于充当在本地计算机上的非特权用户，并向任意远程服务器; 提供匿名凭据的帐户的上下文中运行</span><span class="sxs-lookup"><span data-stu-id="9ce69-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="9ce69-110">`LocalSystem`其中提供了广泛的本地权限，并提供了向任意远程服务器; 的计算机的凭据的帐户的上下文中运行</span><span class="sxs-lookup"><span data-stu-id="9ce69-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="9ce69-111">`NetworkService`其中用作在本地计算机上的非特权用户，并提供向任意远程服务器的计算机的凭据的帐户的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="9ce69-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="9ce69-112">有关详细信息，请参见 <xref:System.ServiceProcess.ServiceAccount> 枚举。</span><span class="sxs-lookup"><span data-stu-id="9ce69-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="9ce69-113">指定服务的安全上下文</span><span class="sxs-lookup"><span data-stu-id="9ce69-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="9ce69-114">创建你的服务之后, 添加为其所必需的安装。</span><span class="sxs-lookup"><span data-stu-id="9ce69-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="9ce69-115">有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9ce69-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="9ce69-116">在设计器中，访问`ProjectInstaller`类并单击你正在使用的服务的服务过程安装。</span><span class="sxs-lookup"><span data-stu-id="9ce69-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ce69-117">对于每个服务应用程序中，有中的至少两个安装组件`ProjectInstaller`类-一个项目，并为该应用程序包含每个服务的一个安装程序在安装所有服务的进程。</span><span class="sxs-lookup"><span data-stu-id="9ce69-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="9ce69-118">在此情况下，你想要选择<xref:System.ServiceProcess.ServiceProcessInstaller>。</span><span class="sxs-lookup"><span data-stu-id="9ce69-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="9ce69-119">在**属性**窗口中，设置<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>为适当的值。</span><span class="sxs-lookup"><span data-stu-id="9ce69-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce69-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ce69-120">See Also</span></span>  
 [<span data-ttu-id="9ce69-121">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="9ce69-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="9ce69-122">如何： 将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="9ce69-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="9ce69-123">如何： 创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="9ce69-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
