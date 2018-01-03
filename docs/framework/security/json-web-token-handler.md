---
title: "JSON Web 标记处理程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a822e87f03c4fa7e1ce7449f09efd178b87cc99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="json-web-token-handler"></a><span data-ttu-id="44fe8-102">JSON Web 标记处理程序</span><span class="sxs-lookup"><span data-stu-id="44fe8-102">JSON Web Token Handler</span></span>
<span data-ttu-id="44fe8-103">Windows Identity Foundation 的 JSON Web 标记处理程序扩展使你能够在应用程序中创建和验证 JSON Web 标记 (JWT)。</span><span class="sxs-lookup"><span data-stu-id="44fe8-103">The JSON Web Token Handler extension for Windows Identity Foundation enables you to create and validate JSON Web Tokens (JWT) in your applications.</span></span> <span data-ttu-id="44fe8-104">可将 JWT 标记处理程序配置为像其他内置安全标记处理程序一样在 WIF 管线中运行，但也可以单独使用它来在轻型应用程序中执行标记验证。</span><span class="sxs-lookup"><span data-stu-id="44fe8-104">The JWT Token Handler can be configured to run in the WIF pipeline like other built-in security token handlers, but it can also be used independently to perform token validation in lightweight applications.</span></span> <span data-ttu-id="44fe8-105">在使用 OAuth 2.0 持有人标记方案（例如，对 Microsoft Azure Active Directory 进行身份验证）时，JWT 标记处理程序尤其有用。</span><span class="sxs-lookup"><span data-stu-id="44fe8-105">The JWT Token Handler is particularly useful when using an OAuth 2.0 bearer token scheme, such as authenticating to Windows Azure Active Directory.</span></span>  
  
 <span data-ttu-id="44fe8-106">JWT 标记处理程序将作为 NuGet 程序包提供。</span><span class="sxs-lookup"><span data-stu-id="44fe8-106">The JWT Token Handler is available as a NuGet package.</span></span> <span data-ttu-id="44fe8-107">有关详细信息，请参阅[下载 JSON Web 令牌处理程序包](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md)。</span><span class="sxs-lookup"><span data-stu-id="44fe8-107">See [Downloading the JSON Web Token Handler Package](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md) for more information.</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="44fe8-108">方案</span><span class="sxs-lookup"><span data-stu-id="44fe8-108">Scenarios</span></span>  
 <span data-ttu-id="44fe8-109">JWT 标记处理程序支持以下关键方案：</span><span class="sxs-lookup"><span data-stu-id="44fe8-109">The JWT Token Handler enables the following key scenarios:</span></span>  
  
-   <span data-ttu-id="44fe8-110">**在服务器应用程序中验证 JWT 令牌**：在此方案中，一家名为 Litware 的公司具有使用 WIF 处理 Web 登录请求的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="44fe8-110">**Validate a JWT Token in a Server Application**: In this scenario, a company named Litware has a server application that uses WIF to handle web sign-on requests.</span></span> <span data-ttu-id="44fe8-111">Litware 希望使其应用程序能够使用 JWT 标记进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="44fe8-111">Litware wants to enable their application to use JWT tokens for authentication.</span></span> <span data-ttu-id="44fe8-112">应用程序与 JWT 标记处理程序一起更新，然后更新应用程序配置以在 WIF 管线中添加 JWT 标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="44fe8-112">The application is updated with the JWT Token Handler, and then the application configuration is updated to add the JWT Token Handler in the WIF pipeline.</span></span> <span data-ttu-id="44fe8-113">在更新完成且新请求输入 WIF 管线后，会使用新的处理程序验证 JWT 标记，并且身份验证将获得成功。</span><span class="sxs-lookup"><span data-stu-id="44fe8-113">After the updates have been made and a new request enters the WIF pipeline, the JWT token is validated using the new handler and successful authentication occurs.</span></span>  
  
-   <span data-ttu-id="44fe8-114">**在 REST Web 服务中验证 JWT 令牌**：在此方案中，一家名为 Litware 的公司具有由 Microsoft Azure Active Directory 保护的 REST Web 服务。</span><span class="sxs-lookup"><span data-stu-id="44fe8-114">**Validate a JWT Token in a REST Web Service**: In this scenario, a company named Litware has a REST web service that is secured by Windows Azure Active Directory.</span></span> <span data-ttu-id="44fe8-115">对 Web 服务的请求必须由 Microsoft Azure AD 进行身份验证，后者在身份验证成功完成后会发出 JWT 标记。</span><span class="sxs-lookup"><span data-stu-id="44fe8-115">Requests to the web service must be authenticated by Windows Azure AD, which issues a JWT token upon successful authentication.</span></span> <span data-ttu-id="44fe8-116">Litware 的客户端应用程序需要访问 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="44fe8-116">Litware has a client application that needs to access the web service.</span></span> <span data-ttu-id="44fe8-117">客户端向 Web 服务发出请求，并显示 Microsoft Azure AD 中的 JWT 标记，然后 Web 服务使用 JWT 标记处理程序验证此标记。</span><span class="sxs-lookup"><span data-stu-id="44fe8-117">The client makes a request to the web service and presents its JWT token from Windows Azure AD, which is then validated by the web service using the JWT Token Handler.</span></span> <span data-ttu-id="44fe8-118">在 JWT 标记处理程序验证该标记之后，Web 服务会将所需的资源返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="44fe8-118">After the JWT Token Handler has validated the token, the desired resource is returned to the client by the web service.</span></span>  
  
## <a name="features"></a><span data-ttu-id="44fe8-119">功能</span><span class="sxs-lookup"><span data-stu-id="44fe8-119">Features</span></span>  
 <span data-ttu-id="44fe8-120">JWT 标记处理程序具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="44fe8-120">The JWT Token Handler offers the following features:</span></span>  
  
-   <span data-ttu-id="44fe8-121">**验证 JWT 令牌**：JWT 令牌可由令牌处理程序的验证逻辑轻松验证，后者可作为应用程序的 WIF 管线的一部分或独立于 WIF 进行调用</span><span class="sxs-lookup"><span data-stu-id="44fe8-121">**Validate a JWT Token**: JWT tokens can be easily validated by the token handler’s validation logic, either as a part of the application’s WIF pipeline or called independently of WIF</span></span>  
  
-   <span data-ttu-id="44fe8-122">**创建 JWT 令牌**：JWT 令牌处理程序可用于创建 JWT 标记以便在下游服务中进行授权</span><span class="sxs-lookup"><span data-stu-id="44fe8-122">**Create a JWT Token**: The JWT Token Handler can be used to create JWT tokens for authorization in downstream services</span></span>
