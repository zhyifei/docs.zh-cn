---
title: "客户端应用程序服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31738e205d0b2b88cbb049607eeb027db873db3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="client-application-services"></a><span data-ttu-id="98c07-102">客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="98c07-102">Client Application Services</span></span>
<span data-ttu-id="98c07-103">借助客户端应用程序服务，可以轻松使用 Microsoft ASP.NET 2.0 AJAX Extensions 中包含的 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 登录名、角色和配置文件应用程序服务，创建基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98c07-103">Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions.</span></span> <span data-ttu-id="98c07-104">这些服务使多个基于 Web 和 Windows 的应用程序共享来自单个服务器的用户信息和用户管理功能。</span><span class="sxs-lookup"><span data-stu-id="98c07-104">These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server.</span></span> <span data-ttu-id="98c07-105">例如，你可以使用这些服务来执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="98c07-105">For example, you can use these services to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="98c07-106">对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98c07-106">Authenticate a user.</span></span> <span data-ttu-id="98c07-107">你可以使用身份验证服务验证用户的身份。</span><span class="sxs-lookup"><span data-stu-id="98c07-107">You can use the authentication service to verify a user's identity.</span></span>  
  
-   <span data-ttu-id="98c07-108">确定经身份验证的用户的角色。</span><span class="sxs-lookup"><span data-stu-id="98c07-108">Determine the role or roles of an authenticated user.</span></span> <span data-ttu-id="98c07-109">你可以根据用户的角色使用角色服务来更改应用程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="98c07-109">You can use the roles service to change the user interface of your application depending on the user's role.</span></span> <span data-ttu-id="98c07-110">例如，你可以为管理员角色的用户提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="98c07-110">For example, you can provide additional features for users who are in an administrator role.</span></span>  
  
-   <span data-ttu-id="98c07-111">存储和访问位于服务器上的每用户应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="98c07-111">Store and access per-user application settings located on the server.</span></span> <span data-ttu-id="98c07-112">你可以使用 Web 设置服务（也称为配置文件服务）跨多个应用程序和位置共享设置。</span><span class="sxs-lookup"><span data-stu-id="98c07-112">You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.</span></span>  
  
 <span data-ttu-id="98c07-113">客户端应用程序服务通过可在应用程序配置文件中指定的客户端服务提供程序来利用 Web 服务扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="98c07-113">Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files.</span></span> <span data-ttu-id="98c07-114">网络连接不可用时，这些服务提供程序包括使用本地缓存进行身份验证、角色和设置数据等脱机功能。</span><span class="sxs-lookup"><span data-stu-id="98c07-114">These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.</span></span>  
  
 <span data-ttu-id="98c07-115">有关 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 应用程序服务的详细信息，请参阅 [ASP.NET 应用程序服务概述](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)。</span><span class="sxs-lookup"><span data-stu-id="98c07-115">For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98c07-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="98c07-116">In This Section</span></span>  
 [<span data-ttu-id="98c07-117">客户端应用程序服务概述</span><span class="sxs-lookup"><span data-stu-id="98c07-117">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 <span data-ttu-id="98c07-118">介绍可通过客户端应用程序服务提供程序提供的功能。</span><span class="sxs-lookup"><span data-stu-id="98c07-118">Describes the features available through the client application service providers.</span></span>  
  
 [<span data-ttu-id="98c07-119">如何：配置客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="98c07-119">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 <span data-ttu-id="98c07-120">介绍如何使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 项目设计器启用并配置应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="98c07-120">Describes how to use the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project designer to enable and configuration application services.</span></span> <span data-ttu-id="98c07-121">还介绍了对 App.config 文件的相应更改。</span><span class="sxs-lookup"><span data-stu-id="98c07-121">Also describes the corresponding changes to your App.config file.</span></span>  
  
 [<span data-ttu-id="98c07-122">如何：使用客户端应用程序服务来实现用户登录</span><span class="sxs-lookup"><span data-stu-id="98c07-122">How to: Implement User Login with Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 <span data-ttu-id="98c07-123">介绍如何在应用程序配置为使用客户端身份验证服务提供程序时验证用户。</span><span class="sxs-lookup"><span data-stu-id="98c07-123">Describes how to validate a user when your application is configured to use a client authentication service provider.</span></span>  
  
 [<span data-ttu-id="98c07-124">演练：使用客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="98c07-124">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 <span data-ttu-id="98c07-125">介绍如何在单个应用程序中合并所有客户端应用程序服务功能。</span><span class="sxs-lookup"><span data-stu-id="98c07-125">Describes how to combine all client application services features in a single application.</span></span> <span data-ttu-id="98c07-126">本演练提供了端到端指导。</span><span class="sxs-lookup"><span data-stu-id="98c07-126">This walkthrough provides end-to-end guidance.</span></span> <span data-ttu-id="98c07-127">例如，它包括有关如何创建可用于测试客户端应用程序服务的 ASP.NET Web 服务应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="98c07-127">For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="98c07-128">参考</span><span class="sxs-lookup"><span data-stu-id="98c07-128">Reference</span></span>  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a><span data-ttu-id="98c07-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98c07-129">See Also</span></span>  
 [<span data-ttu-id="98c07-130">ASP.NET 应用程序服务概述</span><span class="sxs-lookup"><span data-stu-id="98c07-130">ASP.NET Application Services Overview</span></span>](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [<span data-ttu-id="98c07-131">将 Forms 身份验证用于 Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="98c07-131">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [<span data-ttu-id="98c07-132">使用 Microsoft Ajax 角色信息</span><span class="sxs-lookup"><span data-stu-id="98c07-132">Using Roles Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [<span data-ttu-id="98c07-133">使用 Microsoft Ajax 的配置文件信息</span><span class="sxs-lookup"><span data-stu-id="98c07-133">Using Profile Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [<span data-ttu-id="98c07-134">ASP.NET 身份验证</span><span class="sxs-lookup"><span data-stu-id="98c07-134">ASP.NET Authentication</span></span>](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 <span data-ttu-id="98c07-135">[使用角色管理授权](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span><span class="sxs-lookup"><span data-stu-id="98c07-135">[Managing Authorization Using Roles](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span></span>  
 [<span data-ttu-id="98c07-136">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="98c07-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)
