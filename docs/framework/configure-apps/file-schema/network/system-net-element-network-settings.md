---
title: <system.Net> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: febea73ddbc45276f97835eb4af7ee0d0d68dda5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674332"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="2cdd8-102">\<system.Net> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="2cdd8-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="2cdd8-103">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="2cdd8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2cdd8-104">\<configuration></span></span>  
<span data-ttu-id="2cdd8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2cdd8-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdd8-106">语法</span><span class="sxs-lookup"><span data-stu-id="2cdd8-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cdd8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2cdd8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2cdd8-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cdd8-109">特性</span><span class="sxs-lookup"><span data-stu-id="2cdd8-109">Attributes</span></span>  
 <span data-ttu-id="2cdd8-110">无。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2cdd8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="2cdd8-111">Child Elements</span></span>  
  
|<span data-ttu-id="2cdd8-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="2cdd8-112">**Element**</span></span>|<span data-ttu-id="2cdd8-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2cdd8-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2cdd8-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="2cdd8-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="2cdd8-115">指定用于对 Internet 请求进行身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="2cdd8-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2cdd8-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="2cdd8-117">指定的最大数与 Internet 主机的连接。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="2cdd8-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2cdd8-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="2cdd8-119">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="2cdd8-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="2cdd8-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="2cdd8-121">配置简单邮件传输协议 (SMTP) 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="2cdd8-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="2cdd8-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="2cdd8-123">控制网络请求的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="2cdd8-124">settings</span><span class="sxs-lookup"><span data-stu-id="2cdd8-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="2cdd8-125">配置中的类的基本网络选项<xref:System.Net>和相关子命名空间。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="2cdd8-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2cdd8-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="2cdd8-127">指定模块用于从 Internet 主机请求信息。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cdd8-128">父元素</span><span class="sxs-lookup"><span data-stu-id="2cdd8-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2cdd8-129">**元素**</span><span class="sxs-lookup"><span data-stu-id="2cdd8-129">**Element**</span></span>|<span data-ttu-id="2cdd8-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="2cdd8-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2cdd8-131">configuration</span><span class="sxs-lookup"><span data-stu-id="2cdd8-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="2cdd8-132">包含所有命名空间的设置。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cdd8-133">备注</span><span class="sxs-lookup"><span data-stu-id="2cdd8-133">Remarks</span></span>  
 <span data-ttu-id="2cdd8-134">[ \<System.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)元素包含设置中的类<xref:System.Net>和相关子命名空间。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="2cdd8-135">设置配置身份验证模块、 连接管理、 电子邮件设置、 代理服务器和 Internet 请求模块，用于接收来自 Internet 主机的信息。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cdd8-136">示例</span><span class="sxs-lookup"><span data-stu-id="2cdd8-136">Example</span></span>  
 <span data-ttu-id="2cdd8-137">下面的示例演示使用的典型配置<xref:System.Net>类。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cdd8-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cdd8-138">See also</span></span>

- [<span data-ttu-id="2cdd8-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="2cdd8-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
