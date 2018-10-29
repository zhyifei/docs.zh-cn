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
ms.openlocfilehash: 5c7b4d8fae2774fe8e52718fbce91e4bc193c124
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198427"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="98f12-102">&lt;mailSettings&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="98f12-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="98f12-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="98f12-103">Configures mail sending options.</span></span>  

<span data-ttu-id="98f12-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="98f12-104">\<configuration></span></span>  
<span data-ttu-id="98f12-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="98f12-105">\<system.net></span></span>  
<span data-ttu-id="98f12-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="98f12-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f12-107">语法</span><span class="sxs-lookup"><span data-stu-id="98f12-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98f12-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="98f12-108">Attributes and Elements</span></span>  
 <span data-ttu-id="98f12-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="98f12-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98f12-110">特性</span><span class="sxs-lookup"><span data-stu-id="98f12-110">Attributes</span></span>  
 <span data-ttu-id="98f12-111">无。</span><span class="sxs-lookup"><span data-stu-id="98f12-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98f12-112">子元素</span><span class="sxs-lookup"><span data-stu-id="98f12-112">Child Elements</span></span>  
  
|<span data-ttu-id="98f12-113">特性</span><span class="sxs-lookup"><span data-stu-id="98f12-113">Attribute</span></span>|<span data-ttu-id="98f12-114">描述</span><span class="sxs-lookup"><span data-stu-id="98f12-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="98f12-115">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="98f12-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="98f12-116">配置简单邮件传输协议的选项。</span><span class="sxs-lookup"><span data-stu-id="98f12-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98f12-117">父元素</span><span class="sxs-lookup"><span data-stu-id="98f12-117">Parent Elements</span></span>  
  
|<span data-ttu-id="98f12-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="98f12-118">**Element**</span></span>|<span data-ttu-id="98f12-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="98f12-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="98f12-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="98f12-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="98f12-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="98f12-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98f12-122">示例</span><span class="sxs-lookup"><span data-stu-id="98f12-122">Example</span></span>  
 <span data-ttu-id="98f12-123">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="98f12-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98f12-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="98f12-124">See Also</span></span>  
- <xref:System.Net.Mail.SmtpClient>  
- [<span data-ttu-id="98f12-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="98f12-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
