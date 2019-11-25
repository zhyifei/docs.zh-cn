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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089236"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="fd868-102">\<mailSettings > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="fd868-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="fd868-103">配置邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="fd868-103">Configures mail sending options.</span></span>  

<span data-ttu-id="fd868-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd868-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd868-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd868-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="fd868-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<mailSettings >**</span><span class="sxs-lookup"><span data-stu-id="fd868-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fd868-107">语法</span><span class="sxs-lookup"><span data-stu-id="fd868-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd868-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fd868-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fd868-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fd868-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd868-110">特性</span><span class="sxs-lookup"><span data-stu-id="fd868-110">Attributes</span></span>  
 <span data-ttu-id="fd868-111">无。</span><span class="sxs-lookup"><span data-stu-id="fd868-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd868-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fd868-112">Child Elements</span></span>  
  
|<span data-ttu-id="fd868-113">特性</span><span class="sxs-lookup"><span data-stu-id="fd868-113">Attribute</span></span>|<span data-ttu-id="fd868-114">描述</span><span class="sxs-lookup"><span data-stu-id="fd868-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="fd868-115">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="fd868-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="fd868-116">配置简单邮件传输协议选项。</span><span class="sxs-lookup"><span data-stu-id="fd868-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd868-117">父元素</span><span class="sxs-lookup"><span data-stu-id="fd868-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fd868-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="fd868-118">**Element**</span></span>|<span data-ttu-id="fd868-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="fd868-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fd868-120">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="fd868-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="fd868-121">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="fd868-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd868-122">示例</span><span class="sxs-lookup"><span data-stu-id="fd868-122">Example</span></span>  
 <span data-ttu-id="fd868-123">下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="fd868-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd868-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd868-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="fd868-125">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="fd868-125">Network Settings Schema</span></span>](index.md)
