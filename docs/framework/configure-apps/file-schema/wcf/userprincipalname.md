---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b93a0cc24953024e265df418ec6dd738598dd0f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="5ddd8-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="5ddd8-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="5ddd8-103">指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="5ddd8-104">有关设置 UPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="5ddd8-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="5ddd8-105">\<identity></span></span>  
<span data-ttu-id="5ddd8-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="5ddd8-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ddd8-107">语法</span><span class="sxs-lookup"><span data-stu-id="5ddd8-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ddd8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5ddd8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5ddd8-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ddd8-110">特性</span><span class="sxs-lookup"><span data-stu-id="5ddd8-110">Attributes</span></span>  
  
|<span data-ttu-id="5ddd8-111">特性</span><span class="sxs-lookup"><span data-stu-id="5ddd8-111">Attribute</span></span>|<span data-ttu-id="5ddd8-112">描述</span><span class="sxs-lookup"><span data-stu-id="5ddd8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ddd8-113">值</span><span class="sxs-lookup"><span data-stu-id="5ddd8-113">value</span></span>|<span data-ttu-id="5ddd8-114">一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="5ddd8-115">这是登录到 Windows 域的标准用法。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="5ddd8-116">格式： someone@example.com （对于电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-116">The format is: someone@example.com (as for an e-mail address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ddd8-117">子元素</span><span class="sxs-lookup"><span data-stu-id="5ddd8-117">Child Elements</span></span>  
 <span data-ttu-id="5ddd8-118">无。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ddd8-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5ddd8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5ddd8-120">元素</span><span class="sxs-lookup"><span data-stu-id="5ddd8-120">Element</span></span>|<span data-ttu-id="5ddd8-121">描述</span><span class="sxs-lookup"><span data-stu-id="5ddd8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ddd8-122">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="5ddd8-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="5ddd8-123">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ddd8-124">备注</span><span class="sxs-lookup"><span data-stu-id="5ddd8-124">Remarks</span></span>  
 <span data-ttu-id="5ddd8-125">通过此标识连接到终结点的安全 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端在使用终结点进行 SSPI 身份验证时将使用 UPN。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ddd8-126">示例</span><span class="sxs-lookup"><span data-stu-id="5ddd8-126">Example</span></span>  
 <span data-ttu-id="5ddd8-127">下面的配置代码指定要由客户端进行身份验证的服务的 UPN。</span><span class="sxs-lookup"><span data-stu-id="5ddd8-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ddd8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ddd8-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="5ddd8-129">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="5ddd8-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5ddd8-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="5ddd8-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
