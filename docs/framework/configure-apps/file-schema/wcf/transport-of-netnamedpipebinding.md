---
title: "&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84811c70f2f3608c10d8886900169f804a8c9b62
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="1852b-102">&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="1852b-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="1852b-103">定义命名管道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="1852b-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="1852b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1852b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1852b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1852b-105">\<bindings></span></span>  
<span data-ttu-id="1852b-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="1852b-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="1852b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1852b-107">\<binding></span></span>  
<span data-ttu-id="1852b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1852b-108">\<security></span></span>  
<span data-ttu-id="1852b-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="1852b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1852b-110">语法</span><span class="sxs-lookup"><span data-stu-id="1852b-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1852b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1852b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1852b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1852b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1852b-113">特性</span><span class="sxs-lookup"><span data-stu-id="1852b-113">Attributes</span></span>  
  
|<span data-ttu-id="1852b-114">特性</span><span class="sxs-lookup"><span data-stu-id="1852b-114">Attribute</span></span>|<span data-ttu-id="1852b-115">描述</span><span class="sxs-lookup"><span data-stu-id="1852b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1852b-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="1852b-116">protectionLevel</span></span>|<span data-ttu-id="1852b-117">定义命名管道的保护级别。</span><span class="sxs-lookup"><span data-stu-id="1852b-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="1852b-118">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="1852b-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1852b-119">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="1852b-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="1852b-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="1852b-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1852b-121">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="1852b-121">-   None: No protection.</span></span><br /><span data-ttu-id="1852b-122">-Sign： 消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="1852b-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1852b-123">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="1852b-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1852b-124">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="1852b-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1852b-125">子元素</span><span class="sxs-lookup"><span data-stu-id="1852b-125">Child Elements</span></span>  
 <span data-ttu-id="1852b-126">无</span><span class="sxs-lookup"><span data-stu-id="1852b-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1852b-127">父元素</span><span class="sxs-lookup"><span data-stu-id="1852b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1852b-128">元素</span><span class="sxs-lookup"><span data-stu-id="1852b-128">Element</span></span>|<span data-ttu-id="1852b-129">描述</span><span class="sxs-lookup"><span data-stu-id="1852b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1852b-130">\<security></span><span class="sxs-lookup"><span data-stu-id="1852b-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="1852b-131">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1852b-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1852b-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1852b-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="1852b-133">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="1852b-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1852b-134">绑定</span><span class="sxs-lookup"><span data-stu-id="1852b-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1852b-135">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="1852b-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1852b-136">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="1852b-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1852b-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="1852b-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
