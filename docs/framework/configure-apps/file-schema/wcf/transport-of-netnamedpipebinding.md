---
title: '&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: c42132f774257589b9020248188ee8d972eb92ba
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48779239"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="5bbde-102">&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="5bbde-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="5bbde-103">定义命名管道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="5bbde-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="5bbde-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5bbde-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5bbde-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="5bbde-105">\<bindings></span></span>  
<span data-ttu-id="5bbde-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5bbde-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="5bbde-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="5bbde-107">\<binding></span></span>  
<span data-ttu-id="5bbde-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="5bbde-108">\<security></span></span>  
<span data-ttu-id="5bbde-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="5bbde-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bbde-110">语法</span><span class="sxs-lookup"><span data-stu-id="5bbde-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bbde-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5bbde-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5bbde-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5bbde-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bbde-113">特性</span><span class="sxs-lookup"><span data-stu-id="5bbde-113">Attributes</span></span>  
  
|<span data-ttu-id="5bbde-114">特性</span><span class="sxs-lookup"><span data-stu-id="5bbde-114">Attribute</span></span>|<span data-ttu-id="5bbde-115">描述</span><span class="sxs-lookup"><span data-stu-id="5bbde-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bbde-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5bbde-116">protectionLevel</span></span>|<span data-ttu-id="5bbde-117">定义命名管道的保护级别。</span><span class="sxs-lookup"><span data-stu-id="5bbde-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="5bbde-118">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="5bbde-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5bbde-119">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="5bbde-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="5bbde-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="5bbde-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5bbde-121">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="5bbde-121">-   None: No protection.</span></span><br /><span data-ttu-id="5bbde-122">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="5bbde-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5bbde-123">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="5bbde-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="5bbde-124">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="5bbde-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bbde-125">子元素</span><span class="sxs-lookup"><span data-stu-id="5bbde-125">Child Elements</span></span>  
 <span data-ttu-id="5bbde-126">无</span><span class="sxs-lookup"><span data-stu-id="5bbde-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5bbde-127">父元素</span><span class="sxs-lookup"><span data-stu-id="5bbde-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5bbde-128">元素</span><span class="sxs-lookup"><span data-stu-id="5bbde-128">Element</span></span>|<span data-ttu-id="5bbde-129">描述</span><span class="sxs-lookup"><span data-stu-id="5bbde-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bbde-130">\<security></span><span class="sxs-lookup"><span data-stu-id="5bbde-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="5bbde-131">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="5bbde-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bbde-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bbde-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="5bbde-133">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="5bbde-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5bbde-134">绑定</span><span class="sxs-lookup"><span data-stu-id="5bbde-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5bbde-135">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="5bbde-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5bbde-136">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="5bbde-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="5bbde-137">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="5bbde-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
