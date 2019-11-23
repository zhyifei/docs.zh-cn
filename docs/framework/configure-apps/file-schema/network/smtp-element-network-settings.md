---
title: <smtp> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089099"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="c41c2-102">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c41c2-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="c41c2-103">配置发送电子邮件的传递格式、传递方法和发件人地址。</span><span class="sxs-lookup"><span data-stu-id="c41c2-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
<span data-ttu-id="c41c2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c41c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c41c2-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c41c2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c41c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c41c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="c41c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**smtp** ></span><span class="sxs-lookup"><span data-stu-id="c41c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c41c2-108">语法</span><span class="sxs-lookup"><span data-stu-id="c41c2-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c41c2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c41c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c41c2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c41c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c41c2-111">特性</span><span class="sxs-lookup"><span data-stu-id="c41c2-111">Attributes</span></span>  
  
|<span data-ttu-id="c41c2-112">特性</span><span class="sxs-lookup"><span data-stu-id="c41c2-112">Attribute</span></span>|<span data-ttu-id="c41c2-113">描述</span><span class="sxs-lookup"><span data-stu-id="c41c2-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="c41c2-114">指定传出电子邮件的传递格式。</span><span class="sxs-lookup"><span data-stu-id="c41c2-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="c41c2-115">可接受的值为 SevenBit 和 International。</span><span class="sxs-lookup"><span data-stu-id="c41c2-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="c41c2-116">指定电子邮件的传递方法。</span><span class="sxs-lookup"><span data-stu-id="c41c2-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="c41c2-117">可接受的值为 Network、PickupDirectoryFromIis 和 SpecifiedPickupDirectory。</span><span class="sxs-lookup"><span data-stu-id="c41c2-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="c41c2-118">指定传出电子邮件的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="c41c2-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c41c2-119">子元素</span><span class="sxs-lookup"><span data-stu-id="c41c2-119">Child Elements</span></span>  
  
|<span data-ttu-id="c41c2-120">特性</span><span class="sxs-lookup"><span data-stu-id="c41c2-120">Attribute</span></span>|<span data-ttu-id="c41c2-121">描述</span><span class="sxs-lookup"><span data-stu-id="c41c2-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="c41c2-122">配置简单邮件传输协议（SMTP）服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="c41c2-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="c41c2-123">配置外部 SMTP 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="c41c2-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c41c2-124">父元素</span><span class="sxs-lookup"><span data-stu-id="c41c2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c41c2-125">**元素**</span><span class="sxs-lookup"><span data-stu-id="c41c2-125">**Element**</span></span>|<span data-ttu-id="c41c2-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="c41c2-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c41c2-127">\<mailSettings> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c41c2-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="c41c2-128">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="c41c2-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c41c2-129">示例</span><span class="sxs-lookup"><span data-stu-id="c41c2-129">Example</span></span>  
 <span data-ttu-id="c41c2-130">下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="c41c2-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="c41c2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c41c2-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="c41c2-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="c41c2-132">Network Settings Schema</span></span>](index.md)
