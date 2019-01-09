---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: ff38a6975d1ec73c1a3014b94198ba630c3fec31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149975"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="58397-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="58397-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="58397-103">指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="58397-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="58397-104">有关设置 UPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="58397-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="58397-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="58397-105">\<identity></span></span>  
<span data-ttu-id="58397-106">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="58397-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58397-107">语法</span><span class="sxs-lookup"><span data-stu-id="58397-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58397-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="58397-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58397-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="58397-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58397-110">特性</span><span class="sxs-lookup"><span data-stu-id="58397-110">Attributes</span></span>  
  
|<span data-ttu-id="58397-111">特性</span><span class="sxs-lookup"><span data-stu-id="58397-111">Attribute</span></span>|<span data-ttu-id="58397-112">描述</span><span class="sxs-lookup"><span data-stu-id="58397-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58397-113">值</span><span class="sxs-lookup"><span data-stu-id="58397-113">value</span></span>|<span data-ttu-id="58397-114">一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。</span><span class="sxs-lookup"><span data-stu-id="58397-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="58397-115">这是登录到 Windows 域的标准用法。</span><span class="sxs-lookup"><span data-stu-id="58397-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="58397-116">格式是： someone@example.com （与电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="58397-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58397-117">子元素</span><span class="sxs-lookup"><span data-stu-id="58397-117">Child Elements</span></span>  
 <span data-ttu-id="58397-118">无。</span><span class="sxs-lookup"><span data-stu-id="58397-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58397-119">父元素</span><span class="sxs-lookup"><span data-stu-id="58397-119">Parent Elements</span></span>  
  
|<span data-ttu-id="58397-120">元素</span><span class="sxs-lookup"><span data-stu-id="58397-120">Element</span></span>|<span data-ttu-id="58397-121">描述</span><span class="sxs-lookup"><span data-stu-id="58397-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58397-122">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="58397-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="58397-123">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="58397-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58397-124">备注</span><span class="sxs-lookup"><span data-stu-id="58397-124">Remarks</span></span>  
 <span data-ttu-id="58397-125">执行使用该终结点进行 SSPI 身份验证时，连接到此标识的终结点的安全 Windows Communication Foundation (WCF) 客户端将使用该 UPN。</span><span class="sxs-lookup"><span data-stu-id="58397-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58397-126">示例</span><span class="sxs-lookup"><span data-stu-id="58397-126">Example</span></span>  
 <span data-ttu-id="58397-127">下面的配置代码指定要由客户端进行身份验证的服务的 UPN。</span><span class="sxs-lookup"><span data-stu-id="58397-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="58397-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="58397-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="58397-129">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="58397-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="58397-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="58397-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
