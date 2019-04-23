---
title: <specifiedPickupDirectory> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: a459fee557285935c383dcfaf512c8a8a9aea570
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099269"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="ae958-102">\<specifiedPickupDirectory > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="ae958-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="ae958-103">配置简单邮件传输协议 (SMTP) 服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="ae958-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="ae958-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ae958-104">\<configuration></span></span>  
<span data-ttu-id="ae958-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ae958-105">\<system.net></span></span>  
<span data-ttu-id="ae958-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="ae958-106">\<mailSettings></span></span>  
<span data-ttu-id="ae958-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="ae958-107">\<smtp></span></span>  
<span data-ttu-id="ae958-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="ae958-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae958-109">语法</span><span class="sxs-lookup"><span data-stu-id="ae958-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae958-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ae958-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ae958-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ae958-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae958-112">特性</span><span class="sxs-lookup"><span data-stu-id="ae958-112">Attributes</span></span>  
  
|<span data-ttu-id="ae958-113">特性</span><span class="sxs-lookup"><span data-stu-id="ae958-113">Attribute</span></span>|<span data-ttu-id="ae958-114">描述</span><span class="sxs-lookup"><span data-stu-id="ae958-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="ae958-115">在应用程序在其中保存以供以后处理的 SMTP 服务器的电子邮件的目录。</span><span class="sxs-lookup"><span data-stu-id="ae958-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae958-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ae958-116">Child Elements</span></span>  
 <span data-ttu-id="ae958-117">无。</span><span class="sxs-lookup"><span data-stu-id="ae958-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae958-118">父元素</span><span class="sxs-lookup"><span data-stu-id="ae958-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ae958-119">元素</span><span class="sxs-lookup"><span data-stu-id="ae958-119">Element</span></span>|<span data-ttu-id="ae958-120">描述</span><span class="sxs-lookup"><span data-stu-id="ae958-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae958-121">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="ae958-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="ae958-122">配置简单邮件传输协议 (SMTP) 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="ae958-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae958-123">备注</span><span class="sxs-lookup"><span data-stu-id="ae958-123">Remarks</span></span>  
 <span data-ttu-id="ae958-124">`specifiedPickupDirectory` 特性设置应用程序保存邮件以供 SMTP 服务器处理的目录。</span><span class="sxs-lookup"><span data-stu-id="ae958-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae958-125">示例</span><span class="sxs-lookup"><span data-stu-id="ae958-125">Example</span></span>  
 <span data-ttu-id="ae958-126">下面的示例指定 c:\maildrop 作为邮件的拾取目录。</span><span class="sxs-lookup"><span data-stu-id="ae958-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae958-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae958-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="ae958-128">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ae958-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
