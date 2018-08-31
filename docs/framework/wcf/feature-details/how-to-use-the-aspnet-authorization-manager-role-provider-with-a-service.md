---
title: 如何：将 ASP.NET 授权管理器角色提供程序与服务一起使用
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: c21c1a80468bd81f2df69009afd2be86ee714250
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331704"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="3f631-102">如何：将 ASP.NET 授权管理器角色提供程序与服务一起使用</span><span class="sxs-lookup"><span data-stu-id="3f631-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="3f631-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 承载 Web 服务时，您可以将授权管理器集成到应用程序以向服务提供授权。</span><span class="sxs-lookup"><span data-stu-id="3f631-103">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="3f631-104">授权管理器允许应用程序开发人员定义各个操作，这些操作可组织在一起形成任务。</span><span class="sxs-lookup"><span data-stu-id="3f631-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="3f631-105">然后管理员可以授权角色执行特定任务或各个操作。</span><span class="sxs-lookup"><span data-stu-id="3f631-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="3f631-106">授权管理器提供管理工具，并将其作为 Microsoft 管理控制台 (MMC) 管理单元来管理角色、任务、操作和用户。</span><span class="sxs-lookup"><span data-stu-id="3f631-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="3f631-107">管理员在 XML 文件、Active Directory 或 Active Directory 应用程序模式 (ADAM) 存储区中配置授权管理器策略存储区。</span><span class="sxs-lookup"><span data-stu-id="3f631-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="3f631-108">通过为承载 Web 服务的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序配置授权管理器 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 角色提供程序可以将授权管理器集成到该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="3f631-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider for the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is hosting the Web service.</span></span> <span data-ttu-id="3f631-109">像其他 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 角色提供程序一样，授权管理器 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 角色提供程序是使用 <`providers`> 元素进行配置的。</span><span class="sxs-lookup"><span data-stu-id="3f631-109">Like other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role providers, the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="3f631-110">下面的代码示例是 Web 服务配置文件的一部分，该 Web 服务将授权管理器集成到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="3f631-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="3f631-111">有关将集成的详细信息[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]角色提供程序与 WCF 应用程序，请参阅[如何： 使用 ASP.NET 角色提供程序与服务一起](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)。</span><span class="sxs-lookup"><span data-stu-id="3f631-111">For more information about integrating an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="3f631-112">有关使用授权管理器与详细信息[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]，请参阅[如何： 将授权管理器 (AzMan) 与 ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303)。</span><span class="sxs-lookup"><span data-stu-id="3f631-112">For more information about using Authorization Manager with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f631-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f631-113">See Also</span></span>  
 [<span data-ttu-id="3f631-114">如何：将 ASP.NET 角色提供程序与服务一起使用</span><span class="sxs-lookup"><span data-stu-id="3f631-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
