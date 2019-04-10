---
title: <httpDigest> 元素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 914711e4d6c3dbb1ccc741af1b3abd6b8de716a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165316"
---
# <a name="httpdigest-element"></a><span data-ttu-id="9450f-102">\<httpDigest > 元素</span><span class="sxs-lookup"><span data-stu-id="9450f-102">\<httpDigest> Element</span></span>
<span data-ttu-id="9450f-103">指定一个在向服务证明客户端身份时使用的摘要类型凭据。</span><span class="sxs-lookup"><span data-stu-id="9450f-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="9450f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9450f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9450f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9450f-105">\<behaviors></span></span>  
<span data-ttu-id="9450f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9450f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9450f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9450f-107">\<behavior></span></span>  
<span data-ttu-id="9450f-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9450f-108">\<clientCredentials></span></span>  
<span data-ttu-id="9450f-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="9450f-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9450f-110">语法</span><span class="sxs-lookup"><span data-stu-id="9450f-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9450f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9450f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9450f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9450f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9450f-113">特性</span><span class="sxs-lookup"><span data-stu-id="9450f-113">Attributes</span></span>  
  
|<span data-ttu-id="9450f-114">特性</span><span class="sxs-lookup"><span data-stu-id="9450f-114">Attribute</span></span>|<span data-ttu-id="9450f-115">描述</span><span class="sxs-lookup"><span data-stu-id="9450f-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="9450f-116">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="9450f-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="9450f-117">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="9450f-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="9450f-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="9450f-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9450f-119">-标识：服务器可以获取标识和权限的客户端，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="9450f-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="9450f-120">模拟：服务器可以模拟客户端的本地系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="9450f-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="9450f-121">-委托：服务器可以模拟远程系统上的客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="9450f-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="9450f-122">匿名：服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="9450f-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="9450f-123">-None:未分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="9450f-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="9450f-124">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="9450f-124">The default is Identification.</span></span> <span data-ttu-id="9450f-125">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="9450f-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9450f-126">子元素</span><span class="sxs-lookup"><span data-stu-id="9450f-126">Child Elements</span></span>  
 <span data-ttu-id="9450f-127">None</span><span class="sxs-lookup"><span data-stu-id="9450f-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9450f-128">父元素</span><span class="sxs-lookup"><span data-stu-id="9450f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9450f-129">元素</span><span class="sxs-lookup"><span data-stu-id="9450f-129">Element</span></span>|<span data-ttu-id="9450f-130">描述</span><span class="sxs-lookup"><span data-stu-id="9450f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9450f-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9450f-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="9450f-132">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9450f-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9450f-133">备注</span><span class="sxs-lookup"><span data-stu-id="9450f-133">Remarks</span></span>  
 <span data-ttu-id="9450f-134">摘要是使用算法和一组输入确定的哈希。</span><span class="sxs-lookup"><span data-stu-id="9450f-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="9450f-135">身份验证器和被验证方一致同意某种算法并交换用作输入的数据。</span><span class="sxs-lookup"><span data-stu-id="9450f-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="9450f-136">客户端可以计算哈希并将其发送给服务。</span><span class="sxs-lookup"><span data-stu-id="9450f-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="9450f-137">服务也可以计算哈希并比较值。</span><span class="sxs-lookup"><span data-stu-id="9450f-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="9450f-138">如果匹配，则客户端将通过验证。</span><span class="sxs-lookup"><span data-stu-id="9450f-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="9450f-139">必须使用 Windows 上的 Active Directory 和 Internet 信息服务 (IIS) 启用此功能。</span><span class="sxs-lookup"><span data-stu-id="9450f-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="9450f-140">有关详细信息，请参阅[摘要式身份验证在 IIS 6.0 中](https://go.microsoft.com/fwlink/?LinkId=88443)。</span><span class="sxs-lookup"><span data-stu-id="9450f-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9450f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="9450f-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="9450f-142">安全行为</span><span class="sxs-lookup"><span data-stu-id="9450f-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9450f-143">保证客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9450f-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="9450f-144">使用证书</span><span class="sxs-lookup"><span data-stu-id="9450f-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9450f-145">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9450f-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
