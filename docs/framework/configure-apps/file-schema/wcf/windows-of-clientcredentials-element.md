---
title: '&lt;clientCredentials&gt; 的 &lt;windows&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 9badcfafff4bc09a16b0b9a565a9ea5c01e26bb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="2e544-102">&lt;clientCredentials&gt; 的 &lt;windows&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="2e544-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="2e544-103">指定用于表示客户端的 Windows 凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="2e544-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="2e544-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2e544-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e544-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2e544-105">\<behaviors></span></span>  
<span data-ttu-id="2e544-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2e544-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2e544-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2e544-107">\<behavior></span></span>  
<span data-ttu-id="2e544-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2e544-108">\<clientCredentials></span></span>  
<span data-ttu-id="2e544-109">\<windows ></span><span class="sxs-lookup"><span data-stu-id="2e544-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e544-110">语法</span><span class="sxs-lookup"><span data-stu-id="2e544-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e544-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2e544-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2e544-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2e544-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e544-113">特性</span><span class="sxs-lookup"><span data-stu-id="2e544-113">Attributes</span></span>  
  
|<span data-ttu-id="2e544-114">特性</span><span class="sxs-lookup"><span data-stu-id="2e544-114">Attribute</span></span>|<span data-ttu-id="2e544-115">描述</span><span class="sxs-lookup"><span data-stu-id="2e544-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="2e544-116">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="2e544-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="2e544-117">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="2e544-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="2e544-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="2e544-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2e544-119">-Identification： 服务器可以获取的标识和权限的客户端，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="2e544-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="2e544-120">-模拟： 服务器可以模拟客户端的本地系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="2e544-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="2e544-121">-Delegation： 服务器可以模拟在远程系统上的客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="2e544-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="2e544-122">-Anonymous： 服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="2e544-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="2e544-123">-None： 模拟级别未分配。</span><span class="sxs-lookup"><span data-stu-id="2e544-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="2e544-124">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="2e544-124">The default is Identification.</span></span> <span data-ttu-id="2e544-125">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="2e544-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="2e544-126">如果 Kerberos 不可用，则将此属性设置为 `true` 可令身份验证降级到 NTLM。</span><span class="sxs-lookup"><span data-stu-id="2e544-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="2e544-127">此属性设置为`false`会导致 Windows Communication Foundation (WCF) 以使最大努力引发异常，如果使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="2e544-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="2e544-128">请注意，将此属性设置为 `false` 可能不阻止通过网络发送 NTLM 凭据。</span><span class="sxs-lookup"><span data-stu-id="2e544-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e544-129">子元素</span><span class="sxs-lookup"><span data-stu-id="2e544-129">Child Elements</span></span>  
 <span data-ttu-id="2e544-130">无。</span><span class="sxs-lookup"><span data-stu-id="2e544-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e544-131">父元素</span><span class="sxs-lookup"><span data-stu-id="2e544-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2e544-132">元素</span><span class="sxs-lookup"><span data-stu-id="2e544-132">Element</span></span>|<span data-ttu-id="2e544-133">描述</span><span class="sxs-lookup"><span data-stu-id="2e544-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e544-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2e544-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="2e544-135">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="2e544-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e544-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e544-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="2e544-137">保护客户端</span><span class="sxs-lookup"><span data-stu-id="2e544-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="2e544-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="2e544-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="2e544-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="2e544-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
