---
title: <httpDigest> 元素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 328411a429cd42927a190c6805a1f5e2b3555ea1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448447"
---
# <a name="httpdigest-element"></a><span data-ttu-id="00200-102">\<httpDigest > 元素</span><span class="sxs-lookup"><span data-stu-id="00200-102">\<httpDigest> Element</span></span>
<span data-ttu-id="00200-103">指定一个在向服务证明客户端身份时使用的摘要类型凭据。</span><span class="sxs-lookup"><span data-stu-id="00200-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="00200-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00200-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00200-105">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00200-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00200-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为**](behaviors.md)></span><span class="sxs-lookup"><span data-stu-id="00200-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="00200-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="00200-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="00200-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](behavior-of-endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="00200-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="00200-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="00200-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="00200-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpDigest >**</span><span class="sxs-lookup"><span data-stu-id="00200-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00200-111">语法</span><span class="sxs-lookup"><span data-stu-id="00200-111">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00200-112">属性和元素</span><span class="sxs-lookup"><span data-stu-id="00200-112">Attributes and Elements</span></span>  
 <span data-ttu-id="00200-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="00200-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00200-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="00200-114">Attributes</span></span>  
  
|<span data-ttu-id="00200-115">属性</span><span class="sxs-lookup"><span data-stu-id="00200-115">Attribute</span></span>|<span data-ttu-id="00200-116">说明</span><span class="sxs-lookup"><span data-stu-id="00200-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="00200-117">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="00200-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="00200-118">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="00200-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="00200-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="00200-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="00200-120">-标识：服务器可以获取客户端的标识和特权，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="00200-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="00200-121">-模拟：服务器可以在本地系统上模拟客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="00200-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="00200-122">-委派：服务器可以在远程系统上模拟客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="00200-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="00200-123">-Anonymous：服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="00200-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="00200-124">-None：不分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="00200-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="00200-125">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="00200-125">The default is Identification.</span></span> <span data-ttu-id="00200-126">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="00200-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00200-127">子元素</span><span class="sxs-lookup"><span data-stu-id="00200-127">Child Elements</span></span>  
 <span data-ttu-id="00200-128">无</span><span class="sxs-lookup"><span data-stu-id="00200-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00200-129">父元素</span><span class="sxs-lookup"><span data-stu-id="00200-129">Parent Elements</span></span>  
  
|<span data-ttu-id="00200-130">元素</span><span class="sxs-lookup"><span data-stu-id="00200-130">Element</span></span>|<span data-ttu-id="00200-131">说明</span><span class="sxs-lookup"><span data-stu-id="00200-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00200-132">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="00200-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="00200-133">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="00200-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00200-134">备注</span><span class="sxs-lookup"><span data-stu-id="00200-134">Remarks</span></span>  
 <span data-ttu-id="00200-135">摘要是使用算法和一组输入确定的哈希。</span><span class="sxs-lookup"><span data-stu-id="00200-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="00200-136">身份验证器和被验证方一致同意某种算法并交换用作输入的数据。</span><span class="sxs-lookup"><span data-stu-id="00200-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="00200-137">客户端可以计算哈希并将其发送给服务。</span><span class="sxs-lookup"><span data-stu-id="00200-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="00200-138">服务也可以计算哈希并比较值。</span><span class="sxs-lookup"><span data-stu-id="00200-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="00200-139">如果匹配，则客户端将通过验证。</span><span class="sxs-lookup"><span data-stu-id="00200-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="00200-140">必须使用 Windows 上的 Active Directory 和 Internet 信息服务 (IIS) 启用此功能。</span><span class="sxs-lookup"><span data-stu-id="00200-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="00200-141">有关详细信息，请参阅[IIS 6.0 中的摘要式身份验证](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="00200-141">For more information, see [Digest Authentication in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00200-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00200-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="00200-143">安全行为</span><span class="sxs-lookup"><span data-stu-id="00200-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="00200-144">保护客户端</span><span class="sxs-lookup"><span data-stu-id="00200-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="00200-145">使用证书</span><span class="sxs-lookup"><span data-stu-id="00200-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="00200-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="00200-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
