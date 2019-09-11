---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854821"
---
# <a name="userprincipalname"></a><span data-ttu-id="dc285-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="dc285-101">\<userPrincipalName></span></span>
<span data-ttu-id="dc285-102">指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="dc285-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="dc285-103">有关设置 UPN 的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="dc285-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="dc285-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc285-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc285-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dc285-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dc285-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="dc285-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="dc285-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="dc285-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="dc285-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<身份 >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="dc285-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="dc285-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="dc285-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc285-110">语法</span><span class="sxs-lookup"><span data-stu-id="dc285-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc285-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dc285-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc285-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dc285-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc285-113">特性</span><span class="sxs-lookup"><span data-stu-id="dc285-113">Attributes</span></span>  
  
|<span data-ttu-id="dc285-114">特性</span><span class="sxs-lookup"><span data-stu-id="dc285-114">Attribute</span></span>|<span data-ttu-id="dc285-115">描述</span><span class="sxs-lookup"><span data-stu-id="dc285-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc285-116">value</span><span class="sxs-lookup"><span data-stu-id="dc285-116">value</span></span>|<span data-ttu-id="dc285-117">一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。</span><span class="sxs-lookup"><span data-stu-id="dc285-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="dc285-118">这是登录到 Windows 域的标准用法。</span><span class="sxs-lookup"><span data-stu-id="dc285-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="dc285-119">格式为： someone@example.com （用于电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="dc285-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc285-120">子元素</span><span class="sxs-lookup"><span data-stu-id="dc285-120">Child Elements</span></span>  
 <span data-ttu-id="dc285-121">无。</span><span class="sxs-lookup"><span data-stu-id="dc285-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc285-122">父元素</span><span class="sxs-lookup"><span data-stu-id="dc285-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dc285-123">元素</span><span class="sxs-lookup"><span data-stu-id="dc285-123">Element</span></span>|<span data-ttu-id="dc285-124">描述</span><span class="sxs-lookup"><span data-stu-id="dc285-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc285-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="dc285-125">\<identity></span></span>](identity.md)|<span data-ttu-id="dc285-126">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="dc285-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc285-127">备注</span><span class="sxs-lookup"><span data-stu-id="dc285-127">Remarks</span></span>  
 <span data-ttu-id="dc285-128">使用此标识连接到终结点的安全 Windows Communication Foundation （WCF）客户端在使用该终结点执行 SSPI 身份验证时将使用 UPN。</span><span class="sxs-lookup"><span data-stu-id="dc285-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc285-129">示例</span><span class="sxs-lookup"><span data-stu-id="dc285-129">Example</span></span>  
 <span data-ttu-id="dc285-130">下面的配置代码指定要由客户端进行身份验证的服务的 UPN。</span><span class="sxs-lookup"><span data-stu-id="dc285-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="dc285-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc285-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="dc285-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="dc285-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="dc285-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="dc285-133">\<identity></span></span>](identity.md)
