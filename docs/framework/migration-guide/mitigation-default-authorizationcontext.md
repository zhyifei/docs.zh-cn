---
title: "缓解：默认 AuthorizationContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a><span data-ttu-id="f5474-102">缓解：默认 AuthorizationContext</span><span class="sxs-lookup"><span data-stu-id="f5474-102">Mitigation: Default AuthorizationContext</span></span>
<span data-ttu-id="f5474-103">调用具有 `null``authorizationPolicies` 自变量的 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> 所返回的 <xref:System.IdentityModel.Policy.AuthorizationContext> 实现更改了其在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中的实现。</span><span class="sxs-lookup"><span data-stu-id="f5474-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> with a `null``authorizationPolicies` argument has changed its implementation in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f5474-104">影响</span><span class="sxs-lookup"><span data-stu-id="f5474-104">Impact</span></span>  
 <span data-ttu-id="f5474-105">在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。</span><span class="sxs-lookup"><span data-stu-id="f5474-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f5474-106">缓解操作</span><span class="sxs-lookup"><span data-stu-id="f5474-106">Mitigation</span></span>  
 <span data-ttu-id="f5474-107">你可以采用两种方式之一还原以前的行为：</span><span class="sxs-lookup"><span data-stu-id="f5474-107">You can restore the previous behavior in either of two ways:</span></span>  
  
-   <span data-ttu-id="f5474-108">重新编译你的应用以面向早于 4.6 的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="f5474-108">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="f5474-109">对于 IIS 承载的服务，请使用 `<httpRuntime targetFramework="x.x" />` 元素以面向早期版本的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="f5474-109">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x" />` element to target an earlier version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="f5474-110">将下面的行添加到 app.config 文件的 `<appSettings>` 部分：</span><span class="sxs-lookup"><span data-stu-id="f5474-110">Add the following line to the `<appSettings>` section of your app.config file:</span></span>  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5474-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5474-111">See Also</span></span>  
 [<span data-ttu-id="f5474-112">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="f5474-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

