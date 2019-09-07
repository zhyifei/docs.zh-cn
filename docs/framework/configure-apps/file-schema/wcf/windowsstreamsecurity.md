---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: cddd9f0c1dda982c1795500723c21546bd58c92b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399099"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="f528b-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f528b-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="f528b-102">指定自定义绑定的 Windows 流安全设置。</span><span class="sxs-lookup"><span data-stu-id="f528b-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="f528b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f528b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f528b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f528b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f528b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f528b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f528b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="f528b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="f528b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="f528b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f528b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Windowsstreamsecurity 正在 >**</span><span class="sxs-lookup"><span data-stu-id="f528b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f528b-109">语法</span><span class="sxs-lookup"><span data-stu-id="f528b-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f528b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f528b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f528b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f528b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f528b-112">特性</span><span class="sxs-lookup"><span data-stu-id="f528b-112">Attributes</span></span>  
  
|<span data-ttu-id="f528b-113">特性</span><span class="sxs-lookup"><span data-stu-id="f528b-113">Attribute</span></span>|<span data-ttu-id="f528b-114">描述</span><span class="sxs-lookup"><span data-stu-id="f528b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f528b-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f528b-115">protectionLevel</span></span>|<span data-ttu-id="f528b-116">定义消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="f528b-116">Defines message-level security.</span></span> <span data-ttu-id="f528b-117">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="f528b-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="f528b-118">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="f528b-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="f528b-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="f528b-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f528b-120">内容无保护。</span><span class="sxs-lookup"><span data-stu-id="f528b-120">-   None: No protection.</span></span><br /><span data-ttu-id="f528b-121">表明对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="f528b-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="f528b-122">EncryptAndSign对消息进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="f528b-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="f528b-123">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="f528b-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="f528b-124">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="f528b-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f528b-125">子元素</span><span class="sxs-lookup"><span data-stu-id="f528b-125">Child Elements</span></span>  
 <span data-ttu-id="f528b-126">无</span><span class="sxs-lookup"><span data-stu-id="f528b-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f528b-127">父元素</span><span class="sxs-lookup"><span data-stu-id="f528b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f528b-128">元素</span><span class="sxs-lookup"><span data-stu-id="f528b-128">Element</span></span>|<span data-ttu-id="f528b-129">描述</span><span class="sxs-lookup"><span data-stu-id="f528b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f528b-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="f528b-130">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="f528b-131">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f528b-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f528b-132">备注</span><span class="sxs-lookup"><span data-stu-id="f528b-132">Remarks</span></span>  
 <span data-ttu-id="f528b-133">使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。</span><span class="sxs-lookup"><span data-stu-id="f528b-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="f528b-134">特别是 WCF 提供了安全升级。</span><span class="sxs-lookup"><span data-stu-id="f528b-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="f528b-135">此传输安全的配置由此配置元素[ \<以及 custombinding> sslstreamsecurity> >](sslstreamsecurity.md)（可配置并添加到自定义绑定中）封装</span><span class="sxs-lookup"><span data-stu-id="f528b-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f528b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f528b-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="f528b-137">绑定</span><span class="sxs-lookup"><span data-stu-id="f528b-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f528b-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f528b-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f528b-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f528b-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f528b-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f528b-140">\<customBinding></span></span>](custombinding.md)
