---
title: '&lt;httpDigest&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 8ea4597dbfc704f669a514b0d6c5976c80c5c3a6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="fd7b8-102">&lt;httpDigest&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="fd7b8-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="fd7b8-103">指定一个在向服务证明客户端身份时使用的摘要类型凭据。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="fd7b8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd7b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd7b8-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="fd7b8-105">\<behaviors></span></span>  
<span data-ttu-id="fd7b8-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fd7b8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="fd7b8-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="fd7b8-107">\<behavior></span></span>  
<span data-ttu-id="fd7b8-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fd7b8-108">\<clientCredentials></span></span>  
<span data-ttu-id="fd7b8-109">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="fd7b8-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7b8-110">语法</span><span class="sxs-lookup"><span data-stu-id="fd7b8-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd7b8-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fd7b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fd7b8-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd7b8-113">特性</span><span class="sxs-lookup"><span data-stu-id="fd7b8-113">Attributes</span></span>  
  
|<span data-ttu-id="fd7b8-114">特性</span><span class="sxs-lookup"><span data-stu-id="fd7b8-114">Attribute</span></span>|<span data-ttu-id="fd7b8-115">描述</span><span class="sxs-lookup"><span data-stu-id="fd7b8-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="fd7b8-116">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="fd7b8-117">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="fd7b8-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="fd7b8-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fd7b8-119">-Identification： 服务器可以获取的标识和权限的客户端，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="fd7b8-120">-模拟： 服务器可以模拟客户端的本地系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="fd7b8-121">-Delegation： 服务器可以模拟在远程系统上的客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="fd7b8-122">-Anonymous： 服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="fd7b8-123">-None： 模拟级别未分配。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="fd7b8-124">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-124">The default is Identification.</span></span> <span data-ttu-id="fd7b8-125">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd7b8-126">子元素</span><span class="sxs-lookup"><span data-stu-id="fd7b8-126">Child Elements</span></span>  
 <span data-ttu-id="fd7b8-127">无</span><span class="sxs-lookup"><span data-stu-id="fd7b8-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd7b8-128">父元素</span><span class="sxs-lookup"><span data-stu-id="fd7b8-128">Parent Elements</span></span>  
  
|<span data-ttu-id="fd7b8-129">元素</span><span class="sxs-lookup"><span data-stu-id="fd7b8-129">Element</span></span>|<span data-ttu-id="fd7b8-130">描述</span><span class="sxs-lookup"><span data-stu-id="fd7b8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd7b8-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fd7b8-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="fd7b8-132">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd7b8-133">备注</span><span class="sxs-lookup"><span data-stu-id="fd7b8-133">Remarks</span></span>  
 <span data-ttu-id="fd7b8-134">摘要是使用算法和一组输入确定的哈希。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="fd7b8-135">身份验证器和被验证方一致同意某种算法并交换用作输入的数据。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="fd7b8-136">客户端可以计算哈希并将其发送给服务。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="fd7b8-137">服务也可以计算哈希并比较值。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="fd7b8-138">如果匹配，则客户端将通过验证。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="fd7b8-139">必须使用 Windows 上的 Active Directory 和 Internet 信息服务 (IIS) 启用此功能。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="fd7b8-140">有关详细信息，请参阅[摘要式身份验证在 IIS 6.0 中](http://go.microsoft.com/fwlink/?LinkId=88443)。</span><span class="sxs-lookup"><span data-stu-id="fd7b8-140">For more information, see [Digest Authentication in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7b8-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd7b8-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="fd7b8-142">安全行为</span><span class="sxs-lookup"><span data-stu-id="fd7b8-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="fd7b8-143">保护客户端</span><span class="sxs-lookup"><span data-stu-id="fd7b8-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="fd7b8-144">使用证书</span><span class="sxs-lookup"><span data-stu-id="fd7b8-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="fd7b8-145">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="fd7b8-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
