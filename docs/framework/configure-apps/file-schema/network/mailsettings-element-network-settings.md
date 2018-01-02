---
title: "&lt;mailSettings&gt;元素 （网络设置）"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 5ae9ecdfa9cccb7c70c153153b921151aad50e7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="b1156-102">&lt;mailSettings&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b1156-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b1156-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="b1156-103">Configures mail sending options.</span></span>  

<span data-ttu-id="b1156-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b1156-104">\<configuration></span></span>  
<span data-ttu-id="b1156-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="b1156-105">\<system.net></span></span>  
<span data-ttu-id="b1156-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="b1156-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1156-107">语法</span><span class="sxs-lookup"><span data-stu-id="b1156-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1156-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b1156-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b1156-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b1156-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1156-110">特性</span><span class="sxs-lookup"><span data-stu-id="b1156-110">Attributes</span></span>  
 <span data-ttu-id="b1156-111">无。</span><span class="sxs-lookup"><span data-stu-id="b1156-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1156-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b1156-112">Child Elements</span></span>  
  
|<span data-ttu-id="b1156-113">特性</span><span class="sxs-lookup"><span data-stu-id="b1156-113">Attribute</span></span>|<span data-ttu-id="b1156-114">描述</span><span class="sxs-lookup"><span data-stu-id="b1156-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b1156-115">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b1156-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="b1156-116">配置简单邮件传输协议选项。</span><span class="sxs-lookup"><span data-stu-id="b1156-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1156-117">父元素</span><span class="sxs-lookup"><span data-stu-id="b1156-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b1156-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="b1156-118">**Element**</span></span>|<span data-ttu-id="b1156-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b1156-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b1156-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="b1156-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b1156-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="b1156-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b1156-122">示例</span><span class="sxs-lookup"><span data-stu-id="b1156-122">Example</span></span>  
 <span data-ttu-id="b1156-123">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b1156-123">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
  
## <a name="see-also"></a><span data-ttu-id="b1156-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1156-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="b1156-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b1156-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
