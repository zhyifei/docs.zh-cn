---
title: '&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: c42132f774257589b9020248188ee8d972eb92ba
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837045"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="3071c-102">&lt;netNamedPipeBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="3071c-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="3071c-103">定义命名管道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="3071c-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="3071c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3071c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3071c-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3071c-105">\<bindings></span></span>  
<span data-ttu-id="3071c-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="3071c-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="3071c-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3071c-107">\<binding></span></span>  
<span data-ttu-id="3071c-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="3071c-108">\<security></span></span>  
<span data-ttu-id="3071c-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="3071c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3071c-110">语法</span><span class="sxs-lookup"><span data-stu-id="3071c-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3071c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3071c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3071c-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3071c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3071c-113">特性</span><span class="sxs-lookup"><span data-stu-id="3071c-113">Attributes</span></span>  
  
|<span data-ttu-id="3071c-114">特性</span><span class="sxs-lookup"><span data-stu-id="3071c-114">Attribute</span></span>|<span data-ttu-id="3071c-115">描述</span><span class="sxs-lookup"><span data-stu-id="3071c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3071c-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="3071c-116">protectionLevel</span></span>|<span data-ttu-id="3071c-117">定义命名管道的保护级别。</span><span class="sxs-lookup"><span data-stu-id="3071c-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="3071c-118">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="3071c-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="3071c-119">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="3071c-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="3071c-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="3071c-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3071c-121">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="3071c-121">-   None: No protection.</span></span><br /><span data-ttu-id="3071c-122">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="3071c-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="3071c-123">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="3071c-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="3071c-124">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="3071c-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3071c-125">子元素</span><span class="sxs-lookup"><span data-stu-id="3071c-125">Child Elements</span></span>  
 <span data-ttu-id="3071c-126">无</span><span class="sxs-lookup"><span data-stu-id="3071c-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3071c-127">父元素</span><span class="sxs-lookup"><span data-stu-id="3071c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3071c-128">元素</span><span class="sxs-lookup"><span data-stu-id="3071c-128">Element</span></span>|<span data-ttu-id="3071c-129">描述</span><span class="sxs-lookup"><span data-stu-id="3071c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3071c-130">\<security></span><span class="sxs-lookup"><span data-stu-id="3071c-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="3071c-131">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="3071c-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3071c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="3071c-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="3071c-133">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3071c-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3071c-134">绑定</span><span class="sxs-lookup"><span data-stu-id="3071c-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3071c-135">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3071c-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3071c-136">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3071c-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="3071c-137">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3071c-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
