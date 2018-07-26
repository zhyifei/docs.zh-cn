---
title: '&lt;mailSettings&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a9afd992a12392ae0ad1c27eea305cb7e367686d
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874411"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="167d3-102">&lt;mailSettings&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="167d3-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="167d3-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="167d3-103">Configures mail sending options.</span></span>  

<span data-ttu-id="167d3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="167d3-104">\<configuration></span></span>  
<span data-ttu-id="167d3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="167d3-105">\<system.net></span></span>  
<span data-ttu-id="167d3-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="167d3-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167d3-107">语法</span><span class="sxs-lookup"><span data-stu-id="167d3-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="167d3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="167d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="167d3-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="167d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="167d3-110">特性</span><span class="sxs-lookup"><span data-stu-id="167d3-110">Attributes</span></span>  
 <span data-ttu-id="167d3-111">无。</span><span class="sxs-lookup"><span data-stu-id="167d3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="167d3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="167d3-112">Child Elements</span></span>  
  
|<span data-ttu-id="167d3-113">特性</span><span class="sxs-lookup"><span data-stu-id="167d3-113">Attribute</span></span>|<span data-ttu-id="167d3-114">描述</span><span class="sxs-lookup"><span data-stu-id="167d3-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="167d3-115">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="167d3-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="167d3-116">配置简单邮件传输协议的选项。</span><span class="sxs-lookup"><span data-stu-id="167d3-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="167d3-117">父元素</span><span class="sxs-lookup"><span data-stu-id="167d3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="167d3-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="167d3-118">**Element**</span></span>|<span data-ttu-id="167d3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="167d3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="167d3-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="167d3-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="167d3-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="167d3-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="167d3-122">示例</span><span class="sxs-lookup"><span data-stu-id="167d3-122">Example</span></span>  
 <span data-ttu-id="167d3-123">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="167d3-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="167d3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="167d3-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="167d3-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="167d3-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
