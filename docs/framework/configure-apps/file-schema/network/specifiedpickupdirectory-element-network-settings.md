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
ms.openlocfilehash: b62dc1a9118f7d4f1f693ade36626deaecd23999
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47459732"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="64ae7-102">&lt;specifiedPickupDirectory&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="64ae7-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="64ae7-103">配置简单邮件传输协议 (SMTP) 服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="64ae7-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="64ae7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64ae7-104">\<configuration></span></span>  
<span data-ttu-id="64ae7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="64ae7-105">\<system.net></span></span>  
<span data-ttu-id="64ae7-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="64ae7-106">\<mailSettings></span></span>  
<span data-ttu-id="64ae7-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="64ae7-107">\<smtp></span></span>  
<span data-ttu-id="64ae7-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="64ae7-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ae7-109">语法</span><span class="sxs-lookup"><span data-stu-id="64ae7-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64ae7-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="64ae7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64ae7-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="64ae7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64ae7-112">特性</span><span class="sxs-lookup"><span data-stu-id="64ae7-112">Attributes</span></span>  
  
|<span data-ttu-id="64ae7-113">特性</span><span class="sxs-lookup"><span data-stu-id="64ae7-113">Attribute</span></span>|<span data-ttu-id="64ae7-114">描述</span><span class="sxs-lookup"><span data-stu-id="64ae7-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="64ae7-115">在应用程序在其中保存以供以后处理的 SMTP 服务器的电子邮件的目录。</span><span class="sxs-lookup"><span data-stu-id="64ae7-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64ae7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="64ae7-116">Child Elements</span></span>  
 <span data-ttu-id="64ae7-117">无。</span><span class="sxs-lookup"><span data-stu-id="64ae7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64ae7-118">父元素</span><span class="sxs-lookup"><span data-stu-id="64ae7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="64ae7-119">元素</span><span class="sxs-lookup"><span data-stu-id="64ae7-119">Element</span></span>|<span data-ttu-id="64ae7-120">描述</span><span class="sxs-lookup"><span data-stu-id="64ae7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64ae7-121">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="64ae7-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="64ae7-122">配置简单邮件传输协议 (SMTP) 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="64ae7-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64ae7-123">备注</span><span class="sxs-lookup"><span data-stu-id="64ae7-123">Remarks</span></span>  
 <span data-ttu-id="64ae7-124">`specifiedPickupDirectory` 特性设置应用程序保存邮件以供 SMTP 服务器处理的目录。</span><span class="sxs-lookup"><span data-stu-id="64ae7-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64ae7-125">示例</span><span class="sxs-lookup"><span data-stu-id="64ae7-125">Example</span></span>  
 <span data-ttu-id="64ae7-126">下面的示例指定 c:\maildrop 作为邮件的拾取目录。</span><span class="sxs-lookup"><span data-stu-id="64ae7-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64ae7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="64ae7-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="64ae7-128">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="64ae7-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
