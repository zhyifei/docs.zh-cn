---
title: '&lt;windowsstreamsecurity 正在&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: e117c30ba2583158ee21fd11ff4a38b094c18fd9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197625"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="38889-102">&lt;windowsstreamsecurity 正在&gt;</span><span class="sxs-lookup"><span data-stu-id="38889-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="38889-103">指定自定义绑定的 Windows 流安全设置。</span><span class="sxs-lookup"><span data-stu-id="38889-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="38889-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="38889-104">\<system.serviceModel></span></span>  
<span data-ttu-id="38889-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="38889-105">\<bindings></span></span>  
<span data-ttu-id="38889-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="38889-106">\<customBinding></span></span>  
<span data-ttu-id="38889-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="38889-107">\<binding></span></span>  
<span data-ttu-id="38889-108">\<windowsstreamsecurity 正在 ></span><span class="sxs-lookup"><span data-stu-id="38889-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38889-109">语法</span><span class="sxs-lookup"><span data-stu-id="38889-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38889-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="38889-110">Attributes and Elements</span></span>  
 <span data-ttu-id="38889-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="38889-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38889-112">特性</span><span class="sxs-lookup"><span data-stu-id="38889-112">Attributes</span></span>  
  
|<span data-ttu-id="38889-113">特性</span><span class="sxs-lookup"><span data-stu-id="38889-113">Attribute</span></span>|<span data-ttu-id="38889-114">描述</span><span class="sxs-lookup"><span data-stu-id="38889-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38889-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="38889-115">protectionLevel</span></span>|<span data-ttu-id="38889-116">定义消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="38889-116">Defines message-level security.</span></span> <span data-ttu-id="38889-117">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="38889-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="38889-118">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="38889-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="38889-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="38889-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="38889-120">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="38889-120">-   None: No protection.</span></span><br /><span data-ttu-id="38889-121">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="38889-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="38889-122">-EncryptAndSign： 消息签名并加密。</span><span class="sxs-lookup"><span data-stu-id="38889-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="38889-123">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="38889-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="38889-124">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="38889-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38889-125">子元素</span><span class="sxs-lookup"><span data-stu-id="38889-125">Child Elements</span></span>  
 <span data-ttu-id="38889-126">无</span><span class="sxs-lookup"><span data-stu-id="38889-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38889-127">父元素</span><span class="sxs-lookup"><span data-stu-id="38889-127">Parent Elements</span></span>  
  
|<span data-ttu-id="38889-128">元素</span><span class="sxs-lookup"><span data-stu-id="38889-128">Element</span></span>|<span data-ttu-id="38889-129">描述</span><span class="sxs-lookup"><span data-stu-id="38889-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38889-130">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="38889-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="38889-131">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="38889-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38889-132">备注</span><span class="sxs-lookup"><span data-stu-id="38889-132">Remarks</span></span>  
 <span data-ttu-id="38889-133">使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。</span><span class="sxs-lookup"><span data-stu-id="38889-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="38889-134">特别是 WCF 提供了安全升级。</span><span class="sxs-lookup"><span data-stu-id="38889-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="38889-135">此传输安全的配置以及通过封装此配置元素[ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)，其中可以配置，并添加到自定义绑定</span><span class="sxs-lookup"><span data-stu-id="38889-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38889-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="38889-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="38889-137">绑定</span><span class="sxs-lookup"><span data-stu-id="38889-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="38889-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="38889-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="38889-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="38889-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="38889-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="38889-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
