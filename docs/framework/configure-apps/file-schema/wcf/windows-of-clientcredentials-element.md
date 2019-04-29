---
title: <windows> <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: b5e92745b9e39534d2a0bc35504c2dbc8346d2ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769715"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="8b456-102">\<windows > 的\<clientCredentials > 元素</span><span class="sxs-lookup"><span data-stu-id="8b456-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="8b456-103">指定用于表示客户端的 Windows 凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="8b456-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="8b456-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8b456-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b456-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8b456-105">\<behaviors></span></span>  
<span data-ttu-id="8b456-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8b456-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8b456-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8b456-107">\<behavior></span></span>  
<span data-ttu-id="8b456-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8b456-108">\<clientCredentials></span></span>  
<span data-ttu-id="8b456-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="8b456-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b456-110">语法</span><span class="sxs-lookup"><span data-stu-id="8b456-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b456-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b456-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8b456-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8b456-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b456-113">特性</span><span class="sxs-lookup"><span data-stu-id="8b456-113">Attributes</span></span>  
  
|<span data-ttu-id="8b456-114">特性</span><span class="sxs-lookup"><span data-stu-id="8b456-114">Attribute</span></span>|<span data-ttu-id="8b456-115">描述</span><span class="sxs-lookup"><span data-stu-id="8b456-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="8b456-116">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="8b456-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="8b456-117">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="8b456-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="8b456-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="8b456-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8b456-119">-标识：服务器可以获取标识和权限的客户端，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="8b456-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="8b456-120">模拟：服务器可以模拟客户端的本地系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="8b456-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="8b456-121">-委托：服务器可以模拟远程系统上的客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="8b456-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="8b456-122">匿名：服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="8b456-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="8b456-123">-None:未分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="8b456-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="8b456-124">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="8b456-124">The default is Identification.</span></span> <span data-ttu-id="8b456-125">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="8b456-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="8b456-126">如果 Kerberos 不可用，则将此属性设置为 `true` 可令身份验证降级到 NTLM。</span><span class="sxs-lookup"><span data-stu-id="8b456-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="8b456-127">此属性设置为`false`会导致 Windows Communication Foundation (WCF) 以使最大努力引发异常，则一旦使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="8b456-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="8b456-128">请注意，将此属性设置为 `false` 可能不阻止通过网络发送 NTLM 凭据。</span><span class="sxs-lookup"><span data-stu-id="8b456-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b456-129">子元素</span><span class="sxs-lookup"><span data-stu-id="8b456-129">Child Elements</span></span>  
 <span data-ttu-id="8b456-130">无。</span><span class="sxs-lookup"><span data-stu-id="8b456-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b456-131">父元素</span><span class="sxs-lookup"><span data-stu-id="8b456-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8b456-132">元素</span><span class="sxs-lookup"><span data-stu-id="8b456-132">Element</span></span>|<span data-ttu-id="8b456-133">描述</span><span class="sxs-lookup"><span data-stu-id="8b456-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b456-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8b456-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="8b456-135">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="8b456-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b456-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b456-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="8b456-137">保护客户端</span><span class="sxs-lookup"><span data-stu-id="8b456-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="8b456-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="8b456-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8b456-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="8b456-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
