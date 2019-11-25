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
ms.openlocfilehash: 1acc724bb14c3610f14d06452c30b3d5dac42e13
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089079"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="73404-102">\<specifiedPickupDirectory > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="73404-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="73404-103">配置简单邮件传输协议（SMTP）服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="73404-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="73404-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73404-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73404-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73404-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="73404-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73404-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="73404-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73404-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="73404-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="73404-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73404-109">语法</span><span class="sxs-lookup"><span data-stu-id="73404-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73404-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73404-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73404-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73404-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73404-112">特性</span><span class="sxs-lookup"><span data-stu-id="73404-112">Attributes</span></span>  
  
|<span data-ttu-id="73404-113">特性</span><span class="sxs-lookup"><span data-stu-id="73404-113">Attribute</span></span>|<span data-ttu-id="73404-114">描述</span><span class="sxs-lookup"><span data-stu-id="73404-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="73404-115">应用程序在其中保存电子邮件以供 SMTP 服务器稍后处理的目录。</span><span class="sxs-lookup"><span data-stu-id="73404-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73404-116">子元素</span><span class="sxs-lookup"><span data-stu-id="73404-116">Child Elements</span></span>  
 <span data-ttu-id="73404-117">无。</span><span class="sxs-lookup"><span data-stu-id="73404-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73404-118">父元素</span><span class="sxs-lookup"><span data-stu-id="73404-118">Parent Elements</span></span>  
  
|<span data-ttu-id="73404-119">元素</span><span class="sxs-lookup"><span data-stu-id="73404-119">Element</span></span>|<span data-ttu-id="73404-120">描述</span><span class="sxs-lookup"><span data-stu-id="73404-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73404-121">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="73404-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="73404-122">配置简单邮件传输协议（SMTP）邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="73404-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73404-123">备注</span><span class="sxs-lookup"><span data-stu-id="73404-123">Remarks</span></span>  
 <span data-ttu-id="73404-124">`specifiedPickupDirectory` 特性设置应用程序保存邮件以供 SMTP 服务器处理的目录。</span><span class="sxs-lookup"><span data-stu-id="73404-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73404-125">示例</span><span class="sxs-lookup"><span data-stu-id="73404-125">Example</span></span>  
 <span data-ttu-id="73404-126">下面的示例将 c:\maildrop 指定为邮件分拣目录。</span><span class="sxs-lookup"><span data-stu-id="73404-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73404-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="73404-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="73404-128">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="73404-128">Network Settings Schema</span></span>](index.md)
