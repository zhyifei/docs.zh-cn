---
title: <transport> 的 <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735958"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="ad3a1-102">\<netNamedPipeBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="ad3a1-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="ad3a1-103">定义命名管道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="ad3a1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ad3a1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ad3a1-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ad3a1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ad3a1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ad3a1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ad3a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="ad3a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="ad3a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="ad3a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ad3a1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="ad3a1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="ad3a1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="ad3a1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3a1-111">语法</span><span class="sxs-lookup"><span data-stu-id="ad3a1-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad3a1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ad3a1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ad3a1-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad3a1-114">特性</span><span class="sxs-lookup"><span data-stu-id="ad3a1-114">Attributes</span></span>  
  
|<span data-ttu-id="ad3a1-115">特性</span><span class="sxs-lookup"><span data-stu-id="ad3a1-115">Attribute</span></span>|<span data-ttu-id="ad3a1-116">描述</span><span class="sxs-lookup"><span data-stu-id="ad3a1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad3a1-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="ad3a1-117">protectionLevel</span></span>|<span data-ttu-id="ad3a1-118">定义命名管道的保护级别。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="ad3a1-119">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="ad3a1-120">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="ad3a1-121">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="ad3a1-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ad3a1-122">-None：无保护。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-122">-   None: No protection.</span></span><br /><span data-ttu-id="ad3a1-123">-Sign：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ad3a1-124">-EncryptAndSign：对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="ad3a1-125">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad3a1-126">子元素</span><span class="sxs-lookup"><span data-stu-id="ad3a1-126">Child Elements</span></span>  
 <span data-ttu-id="ad3a1-127">None</span><span class="sxs-lookup"><span data-stu-id="ad3a1-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad3a1-128">父元素</span><span class="sxs-lookup"><span data-stu-id="ad3a1-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ad3a1-129">元素</span><span class="sxs-lookup"><span data-stu-id="ad3a1-129">Element</span></span>|<span data-ttu-id="ad3a1-130">描述</span><span class="sxs-lookup"><span data-stu-id="ad3a1-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad3a1-131">\<security ></span><span class="sxs-lookup"><span data-stu-id="ad3a1-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="ad3a1-132">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="ad3a1-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad3a1-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad3a1-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="ad3a1-134">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="ad3a1-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ad3a1-135">绑定</span><span class="sxs-lookup"><span data-stu-id="ad3a1-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ad3a1-136">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ad3a1-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ad3a1-137">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ad3a1-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ad3a1-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ad3a1-138">\<binding></span></span>](bindings.md)
