---
title: "如何：创建自定义主体标识"
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
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90dbd173293a91ab4c2fb1aa34c0aefc5e4ffefa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="cdc9a-102">如何：创建自定义主体标识</span><span class="sxs-lookup"><span data-stu-id="cdc9a-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="cdc9a-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute> 是一种控制对服务方法进行访问的声明性方式。</span><span class="sxs-lookup"><span data-stu-id="cdc9a-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="cdc9a-104">当使用此属性时，<xref:System.ServiceModel.Description.PrincipalPermissionMode> 枚举指定执行授权检查的模式。</span><span class="sxs-lookup"><span data-stu-id="cdc9a-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="cdc9a-105">当此模式设置为 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> 时，用户可以使用它指定一个由 <xref:System.Security.Principal.IPrincipal> 属性返回的自定义 <xref:System.Threading.Thread.CurrentPrincipal%2A> 类。</span><span class="sxs-lookup"><span data-stu-id="cdc9a-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="cdc9a-106">本主题演示的是将 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> 与自定义授权策略和自定义主体结合使用的方案。</span><span class="sxs-lookup"><span data-stu-id="cdc9a-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="cdc9a-107">有关使用<xref:System.Security.Permissions.PrincipalPermissionAttribute>，请参阅[如何： 使用 PrincipalPermissionAttribute 类限制访问](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc9a-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc9a-108">示例</span><span class="sxs-lookup"><span data-stu-id="cdc9a-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdc9a-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="cdc9a-109">Compiling the Code</span></span>  
 <span data-ttu-id="cdc9a-110">编译代码需要引用以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="cdc9a-110">References to the following namespaces are needed to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="cdc9a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdc9a-111">See Also</span></span>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [<span data-ttu-id="cdc9a-112">如何： 与服务一起使用 ASP.NET 角色提供程序</span><span class="sxs-lookup"><span data-stu-id="cdc9a-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="cdc9a-113">如何：使用 PrincipalPermissionAttribute 类限制访问</span><span class="sxs-lookup"><span data-stu-id="cdc9a-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
