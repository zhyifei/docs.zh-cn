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
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697594"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="1fd47-102">\<specifiedPickupDirectory > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="1fd47-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="1fd47-103">配置简单邮件传输协议（SMTP）服务器的本地目录。</span><span class="sxs-lookup"><span data-stu-id="1fd47-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="1fd47-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1fd47-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1fd47-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1fd47-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="1fd47-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1fd47-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="1fd47-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1fd47-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="1fd47-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="1fd47-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd47-109">语法</span><span class="sxs-lookup"><span data-stu-id="1fd47-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fd47-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1fd47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1fd47-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1fd47-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fd47-112">特性</span><span class="sxs-lookup"><span data-stu-id="1fd47-112">Attributes</span></span>  
  
|<span data-ttu-id="1fd47-113">特性</span><span class="sxs-lookup"><span data-stu-id="1fd47-113">Attribute</span></span>|<span data-ttu-id="1fd47-114">描述</span><span class="sxs-lookup"><span data-stu-id="1fd47-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="1fd47-115">应用程序在其中保存电子邮件以供 SMTP 服务器稍后处理的目录。</span><span class="sxs-lookup"><span data-stu-id="1fd47-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fd47-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1fd47-116">Child Elements</span></span>  
 <span data-ttu-id="1fd47-117">无。</span><span class="sxs-lookup"><span data-stu-id="1fd47-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fd47-118">父元素</span><span class="sxs-lookup"><span data-stu-id="1fd47-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1fd47-119">元素</span><span class="sxs-lookup"><span data-stu-id="1fd47-119">Element</span></span>|<span data-ttu-id="1fd47-120">描述</span><span class="sxs-lookup"><span data-stu-id="1fd47-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fd47-121">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="1fd47-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="1fd47-122">配置简单邮件传输协议（SMTP）邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="1fd47-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fd47-123">备注</span><span class="sxs-lookup"><span data-stu-id="1fd47-123">Remarks</span></span>  
 <span data-ttu-id="1fd47-124">`specifiedPickupDirectory` 特性设置应用程序保存邮件以供 SMTP 服务器处理的目录。</span><span class="sxs-lookup"><span data-stu-id="1fd47-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fd47-125">示例</span><span class="sxs-lookup"><span data-stu-id="1fd47-125">Example</span></span>  
 <span data-ttu-id="1fd47-126">下面的示例将 c:\maildrop 指定为邮件分拣目录。</span><span class="sxs-lookup"><span data-stu-id="1fd47-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fd47-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fd47-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="1fd47-128">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="1fd47-128">Network Settings Schema</span></span>](index.md)
