---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940512"
---
# <a name="userprincipalname"></a><span data-ttu-id="fdb4a-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="fdb4a-101">\<userPrincipalName></span></span>
<span data-ttu-id="fdb4a-102">指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="fdb4a-103">有关设置 UPN 的详细信息, 请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="fdb4a-104">\<身份 ></span><span class="sxs-lookup"><span data-stu-id="fdb4a-104">\<identity></span></span>  
<span data-ttu-id="fdb4a-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="fdb4a-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb4a-106">语法</span><span class="sxs-lookup"><span data-stu-id="fdb4a-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdb4a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fdb4a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fdb4a-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdb4a-109">特性</span><span class="sxs-lookup"><span data-stu-id="fdb4a-109">Attributes</span></span>  
  
|<span data-ttu-id="fdb4a-110">特性</span><span class="sxs-lookup"><span data-stu-id="fdb4a-110">Attribute</span></span>|<span data-ttu-id="fdb4a-111">描述</span><span class="sxs-lookup"><span data-stu-id="fdb4a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdb4a-112">值</span><span class="sxs-lookup"><span data-stu-id="fdb4a-112">value</span></span>|<span data-ttu-id="fdb4a-113">一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="fdb4a-114">这是登录到 Windows 域的标准用法。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="fdb4a-115">格式为: someone@example.com (用于电子邮件地址)。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdb4a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="fdb4a-116">Child Elements</span></span>  
 <span data-ttu-id="fdb4a-117">无。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdb4a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="fdb4a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fdb4a-119">元素</span><span class="sxs-lookup"><span data-stu-id="fdb4a-119">Element</span></span>|<span data-ttu-id="fdb4a-120">描述</span><span class="sxs-lookup"><span data-stu-id="fdb4a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdb4a-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="fdb4a-121">\<identity></span></span>](identity.md)|<span data-ttu-id="fdb4a-122">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdb4a-123">备注</span><span class="sxs-lookup"><span data-stu-id="fdb4a-123">Remarks</span></span>  
 <span data-ttu-id="fdb4a-124">使用此标识连接到终结点的安全 Windows Communication Foundation (WCF) 客户端在使用该终结点执行 SSPI 身份验证时将使用 UPN。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb4a-125">示例</span><span class="sxs-lookup"><span data-stu-id="fdb4a-125">Example</span></span>  
 <span data-ttu-id="fdb4a-126">下面的配置代码指定要由客户端进行身份验证的服务的 UPN。</span><span class="sxs-lookup"><span data-stu-id="fdb4a-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="fdb4a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb4a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="fdb4a-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="fdb4a-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fdb4a-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="fdb4a-129">\<identity></span></span>](identity.md)
