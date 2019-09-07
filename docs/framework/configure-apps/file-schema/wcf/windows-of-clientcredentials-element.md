---
title: <windows>of <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399119"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="a500b-102">\<clientCredentials > 元素\<的 windows ></span><span class="sxs-lookup"><span data-stu-id="a500b-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="a500b-103">指定用于表示客户端的 Windows 凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="a500b-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="a500b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a500b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a500b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a500b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="a500b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="a500b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="a500b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="a500b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windows >**</span><span class="sxs-lookup"><span data-stu-id="a500b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a500b-111">语法</span><span class="sxs-lookup"><span data-stu-id="a500b-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a500b-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a500b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a500b-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a500b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a500b-114">特性</span><span class="sxs-lookup"><span data-stu-id="a500b-114">Attributes</span></span>  
  
|<span data-ttu-id="a500b-115">特性</span><span class="sxs-lookup"><span data-stu-id="a500b-115">Attribute</span></span>|<span data-ttu-id="a500b-116">描述</span><span class="sxs-lookup"><span data-stu-id="a500b-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="a500b-117">设置客户端用于与服务器进行通信的模拟首选项。</span><span class="sxs-lookup"><span data-stu-id="a500b-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="a500b-118">服务器上不强制使用客户端所选择的模拟模式。</span><span class="sxs-lookup"><span data-stu-id="a500b-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="a500b-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="a500b-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a500b-120">标识服务器可以获取客户端的标识和特权，但不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="a500b-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="a500b-121">模仿服务器可以在本地系统上模拟客户端的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="a500b-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="a500b-122">委托服务器可以模拟客户端在远程系统上的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="a500b-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="a500b-123">匿名服务器无法模拟或标识客户端。</span><span class="sxs-lookup"><span data-stu-id="a500b-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="a500b-124">内容未分配模拟级别。</span><span class="sxs-lookup"><span data-stu-id="a500b-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="a500b-125">默认值为 Identification。</span><span class="sxs-lookup"><span data-stu-id="a500b-125">The default is Identification.</span></span> <span data-ttu-id="a500b-126">此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。</span><span class="sxs-lookup"><span data-stu-id="a500b-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="a500b-127">如果 Kerberos 不可用，则将此属性设置为 `true` 可令身份验证降级到 NTLM。</span><span class="sxs-lookup"><span data-stu-id="a500b-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="a500b-128">如果将此属性`false`设置为，则会导致 Windows Communication Foundation （WCF）在使用 NTLM 时尽力引发异常。</span><span class="sxs-lookup"><span data-stu-id="a500b-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="a500b-129">请注意，将此属性设置为 `false` 可能不阻止通过网络发送 NTLM 凭据。</span><span class="sxs-lookup"><span data-stu-id="a500b-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a500b-130">子元素</span><span class="sxs-lookup"><span data-stu-id="a500b-130">Child Elements</span></span>  
 <span data-ttu-id="a500b-131">无。</span><span class="sxs-lookup"><span data-stu-id="a500b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a500b-132">父元素</span><span class="sxs-lookup"><span data-stu-id="a500b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a500b-133">元素</span><span class="sxs-lookup"><span data-stu-id="a500b-133">Element</span></span>|<span data-ttu-id="a500b-134">描述</span><span class="sxs-lookup"><span data-stu-id="a500b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a500b-135">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a500b-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="a500b-136">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="a500b-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a500b-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="a500b-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="a500b-138">保护客户端</span><span class="sxs-lookup"><span data-stu-id="a500b-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="a500b-139">使用证书</span><span class="sxs-lookup"><span data-stu-id="a500b-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a500b-140">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a500b-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
