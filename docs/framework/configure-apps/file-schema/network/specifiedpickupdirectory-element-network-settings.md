---
title: '&lt;specifiedPickupDirectory&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 50ab7387fc5e2cac65cac1a6dba0e563225beec9
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874697"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="e69dc-102">&lt;specifiedPickupDirectory&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="e69dc-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e69dc-103">配置简单邮件传输协议 (SMTP) 服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="e69dc-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="e69dc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e69dc-104">\<configuration></span></span>  
<span data-ttu-id="e69dc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e69dc-105">\<system.net></span></span>  
<span data-ttu-id="e69dc-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="e69dc-106">\<mailSettings></span></span>  
<span data-ttu-id="e69dc-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="e69dc-107">\<smtp></span></span>  
<span data-ttu-id="e69dc-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="e69dc-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e69dc-109">语法</span><span class="sxs-lookup"><span data-stu-id="e69dc-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e69dc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e69dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e69dc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e69dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e69dc-112">特性</span><span class="sxs-lookup"><span data-stu-id="e69dc-112">Attributes</span></span>  
  
|<span data-ttu-id="e69dc-113">特性</span><span class="sxs-lookup"><span data-stu-id="e69dc-113">Attribute</span></span>|<span data-ttu-id="e69dc-114">描述</span><span class="sxs-lookup"><span data-stu-id="e69dc-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="e69dc-115">在应用程序在其中保存以供以后处理的 SMTP 服务器的电子邮件的目录。</span><span class="sxs-lookup"><span data-stu-id="e69dc-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e69dc-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e69dc-116">Child Elements</span></span>  
 <span data-ttu-id="e69dc-117">无。</span><span class="sxs-lookup"><span data-stu-id="e69dc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e69dc-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e69dc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e69dc-119">元素</span><span class="sxs-lookup"><span data-stu-id="e69dc-119">Element</span></span>|<span data-ttu-id="e69dc-120">描述</span><span class="sxs-lookup"><span data-stu-id="e69dc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e69dc-121">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="e69dc-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="e69dc-122">配置简单邮件传输协议 (SMTP) 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="e69dc-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e69dc-123">备注</span><span class="sxs-lookup"><span data-stu-id="e69dc-123">Remarks</span></span>  
 <span data-ttu-id="e69dc-124">`specifiedPickupDirectory` 特性设置应用程序保存邮件以供 SMTP 服务器处理的目录。</span><span class="sxs-lookup"><span data-stu-id="e69dc-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e69dc-125">示例</span><span class="sxs-lookup"><span data-stu-id="e69dc-125">Example</span></span>  
 <span data-ttu-id="e69dc-126">下面的示例指定 c:\maildrop 作为邮件的拾取目录。</span><span class="sxs-lookup"><span data-stu-id="e69dc-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e69dc-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e69dc-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="e69dc-128">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e69dc-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
