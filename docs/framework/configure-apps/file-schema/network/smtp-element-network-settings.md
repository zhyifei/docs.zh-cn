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
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697613"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="d0466-102">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d0466-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="d0466-103">配置发送电子邮件的传递格式、传递方法和发件人地址。</span><span class="sxs-lookup"><span data-stu-id="d0466-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="d0466-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d0466-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d0466-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d0466-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d0466-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d0466-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="d0466-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="d0466-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0466-108">语法</span><span class="sxs-lookup"><span data-stu-id="d0466-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0466-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d0466-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d0466-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d0466-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0466-111">特性</span><span class="sxs-lookup"><span data-stu-id="d0466-111">Attributes</span></span>  
  
|<span data-ttu-id="d0466-112">特性</span><span class="sxs-lookup"><span data-stu-id="d0466-112">Attribute</span></span>|<span data-ttu-id="d0466-113">描述</span><span class="sxs-lookup"><span data-stu-id="d0466-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="d0466-114">指定传出电子邮件的传递格式。</span><span class="sxs-lookup"><span data-stu-id="d0466-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="d0466-115">可接受的值为 SevenBit 和 International。</span><span class="sxs-lookup"><span data-stu-id="d0466-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="d0466-116">指定电子邮件的传递方法。</span><span class="sxs-lookup"><span data-stu-id="d0466-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="d0466-117">可接受的值为 Network、PickupDirectoryFromIis 和 SpecifiedPickupDirectory。</span><span class="sxs-lookup"><span data-stu-id="d0466-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="d0466-118">指定传出电子邮件的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="d0466-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0466-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d0466-119">Child Elements</span></span>  
  
|<span data-ttu-id="d0466-120">特性</span><span class="sxs-lookup"><span data-stu-id="d0466-120">Attribute</span></span>|<span data-ttu-id="d0466-121">描述</span><span class="sxs-lookup"><span data-stu-id="d0466-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="d0466-122">配置简单邮件传输协议（SMTP）服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="d0466-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="d0466-123">配置外部 SMTP 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="d0466-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0466-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d0466-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d0466-125">**元素**</span><span class="sxs-lookup"><span data-stu-id="d0466-125">**Element**</span></span>|<span data-ttu-id="d0466-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0466-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0466-127">\<mailSettings> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d0466-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="d0466-128">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="d0466-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0466-129">示例</span><span class="sxs-lookup"><span data-stu-id="d0466-129">Example</span></span>  
 <span data-ttu-id="d0466-130">下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="d0466-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0466-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0466-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="d0466-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d0466-132">Network Settings Schema</span></span>](index.md)
