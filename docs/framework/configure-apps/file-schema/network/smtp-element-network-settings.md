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
ms.openlocfilehash: 1b5f7406f995a86f0a192dbf3249c067dff570ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140369"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="6b5dd-102">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="6b5dd-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="6b5dd-103">配置传递格式、 传递方法和发件人发送电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="6b5dd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6b5dd-104">\<configuration></span></span>  
<span data-ttu-id="6b5dd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6b5dd-105">\<system.net></span></span>  
<span data-ttu-id="6b5dd-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="6b5dd-106">\<mailSettings></span></span>  
<span data-ttu-id="6b5dd-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="6b5dd-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b5dd-108">语法</span><span class="sxs-lookup"><span data-stu-id="6b5dd-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b5dd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b5dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b5dd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b5dd-111">特性</span><span class="sxs-lookup"><span data-stu-id="6b5dd-111">Attributes</span></span>  
  
|<span data-ttu-id="6b5dd-112">特性</span><span class="sxs-lookup"><span data-stu-id="6b5dd-112">Attribute</span></span>|<span data-ttu-id="6b5dd-113">描述</span><span class="sxs-lookup"><span data-stu-id="6b5dd-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="6b5dd-114">指定传出电子邮件的传递格式。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="6b5dd-115">可接受的值为 SevenBit 和 International。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="6b5dd-116">指定电子邮件的传递方法。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="6b5dd-117">可接受的值是网络、 PickupDirectoryFromIis 和 SpecifiedPickupDirectory。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="6b5dd-118">指定发件人的传出电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b5dd-119">子元素</span><span class="sxs-lookup"><span data-stu-id="6b5dd-119">Child Elements</span></span>  
  
|<span data-ttu-id="6b5dd-120">特性</span><span class="sxs-lookup"><span data-stu-id="6b5dd-120">Attribute</span></span>|<span data-ttu-id="6b5dd-121">描述</span><span class="sxs-lookup"><span data-stu-id="6b5dd-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="6b5dd-122">配置简单邮件传输协议 (SMTP) 服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="6b5dd-123">配置外部 SMTP 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b5dd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="6b5dd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6b5dd-125">**元素**</span><span class="sxs-lookup"><span data-stu-id="6b5dd-125">**Element**</span></span>|<span data-ttu-id="6b5dd-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b5dd-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6b5dd-127">\<mailSettings> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="6b5dd-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="6b5dd-128">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b5dd-129">示例</span><span class="sxs-lookup"><span data-stu-id="6b5dd-129">Example</span></span>  
 <span data-ttu-id="6b5dd-130">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6b5dd-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b5dd-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b5dd-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="6b5dd-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="6b5dd-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
