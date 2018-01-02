---
title: "&lt;smtp&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 598fe3dc2a49187e923cd689f863d0a3327e735f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="058ac-102">&lt;smtp&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="058ac-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="058ac-103">配置用于发送电子邮件的传送方法、传送格式和发件人地址。</span><span class="sxs-lookup"><span data-stu-id="058ac-103">Configures the delivery format, delivery method, and from address for sending e-mails.</span></span>  
  
 <span data-ttu-id="058ac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="058ac-104">\<configuration></span></span>  
<span data-ttu-id="058ac-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="058ac-105">\<system.net></span></span>  
<span data-ttu-id="058ac-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="058ac-106">\<mailSettings></span></span>  
<span data-ttu-id="058ac-107">\<smtp ></span><span class="sxs-lookup"><span data-stu-id="058ac-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="058ac-108">语法</span><span class="sxs-lookup"><span data-stu-id="058ac-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="058ac-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="058ac-109">Attributes and Elements</span></span>  
 <span data-ttu-id="058ac-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="058ac-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="058ac-111">特性</span><span class="sxs-lookup"><span data-stu-id="058ac-111">Attributes</span></span>  
  
|<span data-ttu-id="058ac-112">特性</span><span class="sxs-lookup"><span data-stu-id="058ac-112">Attribute</span></span>|<span data-ttu-id="058ac-113">描述</span><span class="sxs-lookup"><span data-stu-id="058ac-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="058ac-114">为传出的电子邮件指定传送格式。</span><span class="sxs-lookup"><span data-stu-id="058ac-114">Specifies the delivery format for outgoing e-mails.</span></span> <span data-ttu-id="058ac-115">可接受的值为 SevenBit 和 International。</span><span class="sxs-lookup"><span data-stu-id="058ac-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="058ac-116">指定电子邮件的传递方法。</span><span class="sxs-lookup"><span data-stu-id="058ac-116">Specifies the delivery method for e-mails.</span></span> <span data-ttu-id="058ac-117">可接受的值是网络、 pickupDirectoryFromIis 和 specifiedPickupDirectory。</span><span class="sxs-lookup"><span data-stu-id="058ac-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="058ac-118">为传出的电子邮件指定发件人地址。</span><span class="sxs-lookup"><span data-stu-id="058ac-118">Specifies the from address for outgoing e-mails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="058ac-119">子元素</span><span class="sxs-lookup"><span data-stu-id="058ac-119">Child Elements</span></span>  
  
|<span data-ttu-id="058ac-120">特性</span><span class="sxs-lookup"><span data-stu-id="058ac-120">Attribute</span></span>|<span data-ttu-id="058ac-121">描述</span><span class="sxs-lookup"><span data-stu-id="058ac-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="058ac-122">配置简单邮件传输协议 (SMTP) 服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="058ac-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="058ac-123">配置外部的 SMTP 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="058ac-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="058ac-124">父元素</span><span class="sxs-lookup"><span data-stu-id="058ac-124">Parent Elements</span></span>  
  
|<span data-ttu-id="058ac-125">**元素**</span><span class="sxs-lookup"><span data-stu-id="058ac-125">**Element**</span></span>|<span data-ttu-id="058ac-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="058ac-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="058ac-127">\<mailSettings> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="058ac-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="058ac-128">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="058ac-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="058ac-129">示例</span><span class="sxs-lookup"><span data-stu-id="058ac-129">Example</span></span>  
 <span data-ttu-id="058ac-130">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="058ac-130">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="058ac-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="058ac-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="058ac-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="058ac-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
