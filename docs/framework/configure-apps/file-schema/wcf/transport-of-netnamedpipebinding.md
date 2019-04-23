---
title: <transport> 的 <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a6d3dd2c24e90bdcdc6520e62dcc1dbe7ce797f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199818"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="c6f12-102">\<transport> of \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c6f12-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="c6f12-103">定义命名管道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6f12-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="c6f12-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c6f12-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6f12-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c6f12-105">\<bindings></span></span>  
<span data-ttu-id="c6f12-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c6f12-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="c6f12-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c6f12-107">\<binding></span></span>  
<span data-ttu-id="c6f12-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="c6f12-108">\<security></span></span>  
<span data-ttu-id="c6f12-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="c6f12-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f12-110">语法</span><span class="sxs-lookup"><span data-stu-id="c6f12-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6f12-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6f12-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c6f12-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c6f12-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6f12-113">特性</span><span class="sxs-lookup"><span data-stu-id="c6f12-113">Attributes</span></span>  
  
|<span data-ttu-id="c6f12-114">特性</span><span class="sxs-lookup"><span data-stu-id="c6f12-114">Attribute</span></span>|<span data-ttu-id="c6f12-115">描述</span><span class="sxs-lookup"><span data-stu-id="c6f12-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6f12-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c6f12-116">protectionLevel</span></span>|<span data-ttu-id="c6f12-117">定义命名管道的保护级别。</span><span class="sxs-lookup"><span data-stu-id="c6f12-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="c6f12-118">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="c6f12-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c6f12-119">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="c6f12-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c6f12-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c6f12-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c6f12-121">-None:无保护。</span><span class="sxs-lookup"><span data-stu-id="c6f12-121">-   None: No protection.</span></span><br /><span data-ttu-id="c6f12-122">登录：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="c6f12-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c6f12-123">-EncryptAndSign:对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="c6f12-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c6f12-124">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="c6f12-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6f12-125">子元素</span><span class="sxs-lookup"><span data-stu-id="c6f12-125">Child Elements</span></span>  
 <span data-ttu-id="c6f12-126">None</span><span class="sxs-lookup"><span data-stu-id="c6f12-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6f12-127">父元素</span><span class="sxs-lookup"><span data-stu-id="c6f12-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c6f12-128">元素</span><span class="sxs-lookup"><span data-stu-id="c6f12-128">Element</span></span>|<span data-ttu-id="c6f12-129">描述</span><span class="sxs-lookup"><span data-stu-id="c6f12-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6f12-130">\<security></span><span class="sxs-lookup"><span data-stu-id="c6f12-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="c6f12-131">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6f12-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6f12-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6f12-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="c6f12-133">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="c6f12-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c6f12-134">绑定</span><span class="sxs-lookup"><span data-stu-id="c6f12-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c6f12-135">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="c6f12-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c6f12-136">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="c6f12-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c6f12-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="c6f12-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
