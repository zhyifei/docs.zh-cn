---
title: '&lt;clientCredentials&gt; 的 &lt;windows&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 1331456f6defc24511064684181f615451be5b93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610742"
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="31170-102">&lt;clientCredentials&gt; 的 &lt;windows&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="31170-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="31170-103">指定用于表示客户端的 Windows 凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="31170-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="31170-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31170-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="31170-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="31170-105">\<behaviors></span></span>  
<span data-ttu-id="31170-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="31170-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="31170-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="31170-107">\<behavior></span></span>  
<span data-ttu-id="31170-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="31170-108">\<clientCredentials></span></span>  
<span data-ttu-id="31170-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="31170-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31170-110">语法</span><span class="sxs-lookup"><span data-stu-id="31170-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31170-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="31170-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31170-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="31170-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31170-113">特性</span><span class="sxs-lookup"><span data-stu-id="31170-113">Attributes</span></span>  
  
|<span data-ttu-id="31170-114">特性</span><span class="sxs-lookup"><span data-stu-id="31170-114">Attribute</span></span>|<span data-ttu-id="31170-115">描述</span><span class="sxs-lookup"><span data-stu-id="31170-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="31170-116">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="31170-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="31170-117">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="31170-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="31170-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="31170-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="31170-119">-标识：服务器可以获取标识和权限的客户端，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="31170-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="31170-120">模拟：服务器可以模拟客户端的本地系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="31170-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="31170-121">-委托：服务器可以模拟远程系统上的客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="31170-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="31170-122">匿名：服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="31170-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="31170-123">-None:未分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="31170-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="31170-124">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="31170-124">The default is Identification.</span></span> <span data-ttu-id="31170-125">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="31170-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="31170-126">如果 Kerberos 不可用，则将此属性设置为 `true` 可令身份验证降级到 NTLM。</span><span class="sxs-lookup"><span data-stu-id="31170-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="31170-127">此属性设置为`false`会导致 Windows Communication Foundation (WCF) 以使最大努力引发异常，则一旦使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="31170-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="31170-128">请注意，将此属性设置为 `false` 可能不阻止通过网络发送 NTLM 凭据。</span><span class="sxs-lookup"><span data-stu-id="31170-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31170-129">子元素</span><span class="sxs-lookup"><span data-stu-id="31170-129">Child Elements</span></span>  
 <span data-ttu-id="31170-130">无。</span><span class="sxs-lookup"><span data-stu-id="31170-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31170-131">父元素</span><span class="sxs-lookup"><span data-stu-id="31170-131">Parent Elements</span></span>  
  
|<span data-ttu-id="31170-132">元素</span><span class="sxs-lookup"><span data-stu-id="31170-132">Element</span></span>|<span data-ttu-id="31170-133">描述</span><span class="sxs-lookup"><span data-stu-id="31170-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31170-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="31170-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="31170-135">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="31170-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31170-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="31170-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="31170-137">保护客户端</span><span class="sxs-lookup"><span data-stu-id="31170-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="31170-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="31170-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="31170-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="31170-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
