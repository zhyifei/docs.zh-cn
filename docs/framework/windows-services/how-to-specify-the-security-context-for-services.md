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
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512471"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="25c4d-102">如何：为服务指定安全上下文</span><span class="sxs-lookup"><span data-stu-id="25c4d-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="25c4d-103">默认情况下，服务在与登录用户不同的安全性上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="25c4d-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="25c4d-104">服务在名为 `LocalSystem` 的默认系统帐户的上下文中运行，这样使服务拥有与用户不同的针对系统资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="25c4d-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="25c4d-105">可以更改此行为以指定应在其下运行服务的其他用户帐户。</span><span class="sxs-lookup"><span data-stu-id="25c4d-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="25c4d-106">可以通过操作服务运行于其中的进程的 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 属性来设置安全性上下文。</span><span class="sxs-lookup"><span data-stu-id="25c4d-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="25c4d-107">此属性允许将服务设置为以下四种帐户类型之一：</span><span class="sxs-lookup"><span data-stu-id="25c4d-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="25c4d-108">`User`，该帐户会导致系统在安装服务时提示输入有效的用户名和密码，并在网络上单个用户指定的帐户的上下文中运行；</span><span class="sxs-lookup"><span data-stu-id="25c4d-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="25c4d-109">`LocalService`，该帐户在用作本地计算机上的非特权用户的帐户的上下文中运行，并向任意远程服务器提供匿名凭据；</span><span class="sxs-lookup"><span data-stu-id="25c4d-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="25c4d-110">`LocalSystem`，该帐户在提供广泛本地权限的帐户的上下文中运行，并向任意远程服务器提供计算机凭据；</span><span class="sxs-lookup"><span data-stu-id="25c4d-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="25c4d-111">`NetworkService`，该帐户在用作本地计算机上的非特权用户的帐户的上下文中运行，并向任意远程服务器提供计算机凭据。</span><span class="sxs-lookup"><span data-stu-id="25c4d-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="25c4d-112">有关详细信息，请参见 <xref:System.ServiceProcess.ServiceAccount> 枚举。</span><span class="sxs-lookup"><span data-stu-id="25c4d-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="25c4d-113">为服务指定安全性上下文</span><span class="sxs-lookup"><span data-stu-id="25c4d-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="25c4d-114">在创建服务后为其添加必要的安装程序。</span><span class="sxs-lookup"><span data-stu-id="25c4d-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="25c4d-115">有关详细信息，请参阅[如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="25c4d-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="25c4d-116">在设计器中，访问 `ProjectInstaller` 类并单击正在使用的服务的服务进程安装程序。</span><span class="sxs-lookup"><span data-stu-id="25c4d-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25c4d-117">对于每个服务应用程序，在 `ProjectInstaller` 类中至少有两个安装组件 — 一个用于安装项目中所有服务的进程，另一个是应用程序包含的每个服务的安装程序。</span><span class="sxs-lookup"><span data-stu-id="25c4d-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="25c4d-118">在这种情况下，你要选择 <xref:System.ServiceProcess.ServiceProcessInstaller>。</span><span class="sxs-lookup"><span data-stu-id="25c4d-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="25c4d-119">在“属性”窗口中，将 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="25c4d-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c4d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="25c4d-120">See Also</span></span>  
 [<span data-ttu-id="25c4d-121">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="25c4d-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="25c4d-122">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="25c4d-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="25c4d-123">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="25c4d-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
