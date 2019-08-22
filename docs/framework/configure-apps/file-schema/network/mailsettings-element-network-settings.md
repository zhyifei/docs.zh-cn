---
title: <mailSettings> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: b8ea08cbd76e60a3665703bc50924dd94500cd87
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659323"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="d0696-102">\<mailSettings > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="d0696-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="d0696-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="d0696-103">Configures mail sending options.</span></span>  

<span data-ttu-id="d0696-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d0696-104">\<configuration></span></span>  
<span data-ttu-id="d0696-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d0696-105">\<system.net></span></span>  
<span data-ttu-id="d0696-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="d0696-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0696-107">语法</span><span class="sxs-lookup"><span data-stu-id="d0696-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0696-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d0696-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d0696-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d0696-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0696-110">特性</span><span class="sxs-lookup"><span data-stu-id="d0696-110">Attributes</span></span>  
 <span data-ttu-id="d0696-111">无。</span><span class="sxs-lookup"><span data-stu-id="d0696-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0696-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d0696-112">Child Elements</span></span>  
  
|<span data-ttu-id="d0696-113">特性</span><span class="sxs-lookup"><span data-stu-id="d0696-113">Attribute</span></span>|<span data-ttu-id="d0696-114">描述</span><span class="sxs-lookup"><span data-stu-id="d0696-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d0696-115">\<smtp > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="d0696-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="d0696-116">配置简单邮件传输协议选项。</span><span class="sxs-lookup"><span data-stu-id="d0696-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0696-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d0696-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d0696-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="d0696-118">**Element**</span></span>|<span data-ttu-id="d0696-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0696-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0696-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d0696-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d0696-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="d0696-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0696-122">示例</span><span class="sxs-lookup"><span data-stu-id="d0696-122">Example</span></span>  
 <span data-ttu-id="d0696-123">下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="d0696-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0696-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0696-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="d0696-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d0696-125">Network Settings Schema</span></span>](index.md)
