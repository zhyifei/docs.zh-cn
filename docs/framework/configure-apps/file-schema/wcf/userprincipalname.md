---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188241"
---
# <a name="userprincipalname"></a><span data-ttu-id="79564-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="79564-101">\<userPrincipalName></span></span>
<span data-ttu-id="79564-102">指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="79564-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="79564-103">有关设置 UPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="79564-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="79564-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="79564-104">\<identity></span></span>  
<span data-ttu-id="79564-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="79564-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79564-106">语法</span><span class="sxs-lookup"><span data-stu-id="79564-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79564-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79564-107">Attributes and Elements</span></span>  
 <span data-ttu-id="79564-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79564-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79564-109">特性</span><span class="sxs-lookup"><span data-stu-id="79564-109">Attributes</span></span>  
  
|<span data-ttu-id="79564-110">特性</span><span class="sxs-lookup"><span data-stu-id="79564-110">Attribute</span></span>|<span data-ttu-id="79564-111">描述</span><span class="sxs-lookup"><span data-stu-id="79564-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79564-112">值</span><span class="sxs-lookup"><span data-stu-id="79564-112">value</span></span>|<span data-ttu-id="79564-113">一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。</span><span class="sxs-lookup"><span data-stu-id="79564-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="79564-114">这是登录到 Windows 域的标准用法。</span><span class="sxs-lookup"><span data-stu-id="79564-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="79564-115">格式是： someone@example.com （与电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="79564-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79564-116">子元素</span><span class="sxs-lookup"><span data-stu-id="79564-116">Child Elements</span></span>  
 <span data-ttu-id="79564-117">无。</span><span class="sxs-lookup"><span data-stu-id="79564-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79564-118">父元素</span><span class="sxs-lookup"><span data-stu-id="79564-118">Parent Elements</span></span>  
  
|<span data-ttu-id="79564-119">元素</span><span class="sxs-lookup"><span data-stu-id="79564-119">Element</span></span>|<span data-ttu-id="79564-120">描述</span><span class="sxs-lookup"><span data-stu-id="79564-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79564-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="79564-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="79564-122">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="79564-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79564-123">备注</span><span class="sxs-lookup"><span data-stu-id="79564-123">Remarks</span></span>  
 <span data-ttu-id="79564-124">执行使用该终结点进行 SSPI 身份验证时，连接到此标识的终结点的安全 Windows Communication Foundation (WCF) 客户端将使用该 UPN。</span><span class="sxs-lookup"><span data-stu-id="79564-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79564-125">示例</span><span class="sxs-lookup"><span data-stu-id="79564-125">Example</span></span>  
 <span data-ttu-id="79564-126">下面的配置代码指定要由客户端进行身份验证的服务的 UPN。</span><span class="sxs-lookup"><span data-stu-id="79564-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="79564-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="79564-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="79564-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="79564-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="79564-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="79564-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
