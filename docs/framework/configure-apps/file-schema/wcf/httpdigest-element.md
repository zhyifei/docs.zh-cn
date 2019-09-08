---
title: <httpDigest> 元素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 121df39c7e4ce4de5c1f0ef87921f6269d7cc1c0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785825"
---
# <a name="httpdigest-element"></a><span data-ttu-id="6dede-102">\<httpDigest > 元素</span><span class="sxs-lookup"><span data-stu-id="6dede-102">\<httpDigest> Element</span></span>
<span data-ttu-id="6dede-103">指定一个在向服务证明客户端身份时使用的摘要类型凭据。</span><span class="sxs-lookup"><span data-stu-id="6dede-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="6dede-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6dede-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6dede-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6dede-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6dede-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6dede-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="6dede-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="6dede-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpDigest >**</span><span class="sxs-lookup"><span data-stu-id="6dede-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dede-111">语法</span><span class="sxs-lookup"><span data-stu-id="6dede-111">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6dede-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6dede-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6dede-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6dede-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6dede-114">特性</span><span class="sxs-lookup"><span data-stu-id="6dede-114">Attributes</span></span>  
  
|<span data-ttu-id="6dede-115">特性</span><span class="sxs-lookup"><span data-stu-id="6dede-115">Attribute</span></span>|<span data-ttu-id="6dede-116">描述</span><span class="sxs-lookup"><span data-stu-id="6dede-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="6dede-117">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="6dede-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="6dede-118">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="6dede-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="6dede-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="6dede-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6dede-120">标识服务器可以获取客户端的标识和特权，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="6dede-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="6dede-121">模仿服务器可以在本地系统上模拟客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="6dede-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="6dede-122">委托服务器可以模拟客户端在远程系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="6dede-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="6dede-123">匿名服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="6dede-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="6dede-124">内容未分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="6dede-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="6dede-125">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="6dede-125">The default is Identification.</span></span> <span data-ttu-id="6dede-126">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="6dede-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6dede-127">子元素</span><span class="sxs-lookup"><span data-stu-id="6dede-127">Child Elements</span></span>  
 <span data-ttu-id="6dede-128">无</span><span class="sxs-lookup"><span data-stu-id="6dede-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6dede-129">父元素</span><span class="sxs-lookup"><span data-stu-id="6dede-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6dede-130">元素</span><span class="sxs-lookup"><span data-stu-id="6dede-130">Element</span></span>|<span data-ttu-id="6dede-131">描述</span><span class="sxs-lookup"><span data-stu-id="6dede-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dede-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="6dede-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="6dede-133">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="6dede-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dede-134">备注</span><span class="sxs-lookup"><span data-stu-id="6dede-134">Remarks</span></span>  
 <span data-ttu-id="6dede-135">摘要是使用算法和一组输入确定的哈希。</span><span class="sxs-lookup"><span data-stu-id="6dede-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="6dede-136">身份验证器和被验证方一致同意某种算法并交换用作输入的数据。</span><span class="sxs-lookup"><span data-stu-id="6dede-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="6dede-137">客户端可以计算哈希并将其发送给服务。</span><span class="sxs-lookup"><span data-stu-id="6dede-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="6dede-138">服务也可以计算哈希并比较值。</span><span class="sxs-lookup"><span data-stu-id="6dede-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="6dede-139">如果匹配，则客户端将通过验证。</span><span class="sxs-lookup"><span data-stu-id="6dede-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="6dede-140">必须使用 Windows 上的 Active Directory 和 Internet 信息服务 (IIS) 启用此功能。</span><span class="sxs-lookup"><span data-stu-id="6dede-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="6dede-141">有关详细信息，请参阅[IIS 6.0 中的摘要式身份验证](https://go.microsoft.com/fwlink/?LinkId=88443)。</span><span class="sxs-lookup"><span data-stu-id="6dede-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dede-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dede-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="6dede-143">安全行为</span><span class="sxs-lookup"><span data-stu-id="6dede-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6dede-144">保护客户端</span><span class="sxs-lookup"><span data-stu-id="6dede-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="6dede-145">使用证书</span><span class="sxs-lookup"><span data-stu-id="6dede-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6dede-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="6dede-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
