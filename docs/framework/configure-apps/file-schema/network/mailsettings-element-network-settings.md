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
ms.openlocfilehash: 0e71284e914dac2d28448f3d8bd4bdc7a9f6b325
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277610"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="fb492-102">\<mailSettings > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="fb492-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="fb492-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="fb492-103">Configures mail sending options.</span></span>  

<span data-ttu-id="fb492-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fb492-104">\<configuration></span></span>  
<span data-ttu-id="fb492-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fb492-105">\<system.net></span></span>  
<span data-ttu-id="fb492-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="fb492-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb492-107">语法</span><span class="sxs-lookup"><span data-stu-id="fb492-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb492-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fb492-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fb492-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fb492-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb492-110">特性</span><span class="sxs-lookup"><span data-stu-id="fb492-110">Attributes</span></span>  
 <span data-ttu-id="fb492-111">无。</span><span class="sxs-lookup"><span data-stu-id="fb492-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb492-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fb492-112">Child Elements</span></span>  
  
|<span data-ttu-id="fb492-113">特性</span><span class="sxs-lookup"><span data-stu-id="fb492-113">Attribute</span></span>|<span data-ttu-id="fb492-114">描述</span><span class="sxs-lookup"><span data-stu-id="fb492-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="fb492-115">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="fb492-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="fb492-116">配置简单邮件传输协议的选项。</span><span class="sxs-lookup"><span data-stu-id="fb492-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb492-117">父元素</span><span class="sxs-lookup"><span data-stu-id="fb492-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fb492-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="fb492-118">**Element**</span></span>|<span data-ttu-id="fb492-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb492-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fb492-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="fb492-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="fb492-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="fb492-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fb492-122">示例</span><span class="sxs-lookup"><span data-stu-id="fb492-122">Example</span></span>  
 <span data-ttu-id="fb492-123">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fb492-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb492-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb492-124">See also</span></span>
- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="fb492-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="fb492-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
