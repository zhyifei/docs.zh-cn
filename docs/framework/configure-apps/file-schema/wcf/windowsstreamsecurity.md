---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113628"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="5901d-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="5901d-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="5901d-102">指定自定义绑定的 Windows 流安全设置。</span><span class="sxs-lookup"><span data-stu-id="5901d-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="5901d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5901d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5901d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5901d-104">\<bindings></span></span>  
<span data-ttu-id="5901d-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5901d-105">\<customBinding></span></span>  
<span data-ttu-id="5901d-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5901d-106">\<binding></span></span>  
<span data-ttu-id="5901d-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="5901d-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5901d-108">语法</span><span class="sxs-lookup"><span data-stu-id="5901d-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5901d-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5901d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5901d-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5901d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5901d-111">特性</span><span class="sxs-lookup"><span data-stu-id="5901d-111">Attributes</span></span>  
  
|<span data-ttu-id="5901d-112">特性</span><span class="sxs-lookup"><span data-stu-id="5901d-112">Attribute</span></span>|<span data-ttu-id="5901d-113">描述</span><span class="sxs-lookup"><span data-stu-id="5901d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5901d-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5901d-114">protectionLevel</span></span>|<span data-ttu-id="5901d-115">定义消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="5901d-115">Defines message-level security.</span></span> <span data-ttu-id="5901d-116">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="5901d-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5901d-117">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="5901d-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="5901d-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="5901d-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5901d-119">-None:无保护。</span><span class="sxs-lookup"><span data-stu-id="5901d-119">-   None: No protection.</span></span><br /><span data-ttu-id="5901d-120">登录：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="5901d-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5901d-121">-EncryptAndSign:消息签名并加密。</span><span class="sxs-lookup"><span data-stu-id="5901d-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="5901d-122">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="5901d-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="5901d-123">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="5901d-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5901d-124">子元素</span><span class="sxs-lookup"><span data-stu-id="5901d-124">Child Elements</span></span>  
 <span data-ttu-id="5901d-125">None</span><span class="sxs-lookup"><span data-stu-id="5901d-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5901d-126">父元素</span><span class="sxs-lookup"><span data-stu-id="5901d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5901d-127">元素</span><span class="sxs-lookup"><span data-stu-id="5901d-127">Element</span></span>|<span data-ttu-id="5901d-128">描述</span><span class="sxs-lookup"><span data-stu-id="5901d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5901d-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="5901d-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5901d-130">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="5901d-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5901d-131">备注</span><span class="sxs-lookup"><span data-stu-id="5901d-131">Remarks</span></span>  
 <span data-ttu-id="5901d-132">使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。</span><span class="sxs-lookup"><span data-stu-id="5901d-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="5901d-133">特别是 WCF 提供了安全升级。</span><span class="sxs-lookup"><span data-stu-id="5901d-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="5901d-134">此传输安全的配置以及通过封装此配置元素[ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)，其中可以配置，并添加到自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5901d-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5901d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5901d-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="5901d-136">绑定</span><span class="sxs-lookup"><span data-stu-id="5901d-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5901d-137">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="5901d-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5901d-138">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5901d-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5901d-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5901d-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
