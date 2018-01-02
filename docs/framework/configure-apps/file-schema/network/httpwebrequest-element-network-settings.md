---
title: "&lt;httpWebRequest&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: dadb2d7635f132b44d6fca8c56f53b847ffb1ff9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="e21b4-102">&lt;httpWebRequest&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="e21b4-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e21b4-103">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="e21b4-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="e21b4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e21b4-104">\<configuration></span></span>  
<span data-ttu-id="e21b4-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="e21b4-105">\<system.net></span></span>  
<span data-ttu-id="e21b4-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="e21b4-106">\<settings></span></span>  
<span data-ttu-id="e21b4-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="e21b4-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e21b4-108">语法</span><span class="sxs-lookup"><span data-stu-id="e21b4-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e21b4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e21b4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e21b4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e21b4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e21b4-111">特性</span><span class="sxs-lookup"><span data-stu-id="e21b4-111">Attributes</span></span>  
  
|<span data-ttu-id="e21b4-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="e21b4-112">**Attribute**</span></span>|<span data-ttu-id="e21b4-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="e21b4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="e21b4-114">指定以千字节为单位的响应标头的最大长度。</span><span class="sxs-lookup"><span data-stu-id="e21b4-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="e21b4-115">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="e21b4-115">The default is 64.</span></span> <span data-ttu-id="e21b4-116">值-1 指示没有大小限制将施加的响应标头。</span><span class="sxs-lookup"><span data-stu-id="e21b4-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="e21b4-117">指定错误响应，最大的长度，以千字节为单位。</span><span class="sxs-lookup"><span data-stu-id="e21b4-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="e21b4-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="e21b4-118">The default is 64.</span></span> <span data-ttu-id="e21b4-119">值-1 指示没有大小限制将施加错误响应。</span><span class="sxs-lookup"><span data-stu-id="e21b4-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="e21b4-120">指定为未经授权的错误代码，以字节为单位的响应中上载的最大长度。</span><span class="sxs-lookup"><span data-stu-id="e21b4-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="e21b4-121">默认值为 -1。</span><span class="sxs-lookup"><span data-stu-id="e21b4-121">The default is -1.</span></span> <span data-ttu-id="e21b4-122">值-1 指示没有大小限制将施加上载。</span><span class="sxs-lookup"><span data-stu-id="e21b4-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="e21b4-123">指定是否启用不安全标头分析。</span><span class="sxs-lookup"><span data-stu-id="e21b4-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="e21b4-124">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="e21b4-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e21b4-125">子元素</span><span class="sxs-lookup"><span data-stu-id="e21b4-125">Child Elements</span></span>  
 <span data-ttu-id="e21b4-126">无。</span><span class="sxs-lookup"><span data-stu-id="e21b4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e21b4-127">父元素</span><span class="sxs-lookup"><span data-stu-id="e21b4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e21b4-128">**元素**</span><span class="sxs-lookup"><span data-stu-id="e21b4-128">**Element**</span></span>|<span data-ttu-id="e21b4-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="e21b4-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e21b4-130">设置</span><span class="sxs-lookup"><span data-stu-id="e21b4-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="e21b4-131">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="e21b4-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e21b4-132">备注</span><span class="sxs-lookup"><span data-stu-id="e21b4-132">Remarks</span></span>  
 <span data-ttu-id="e21b4-133">默认情况下，.NET Framework 严格强制 RFC 2616 实施 URI 分析。</span><span class="sxs-lookup"><span data-stu-id="e21b4-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="e21b4-134">某些服务器响应可能包括禁止字段，这将导致中的控制字符<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>方法会引发<xref:System.Net.WebException>。</span><span class="sxs-lookup"><span data-stu-id="e21b4-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e21b4-135">如果**useUnsafeHeaderParsing**设置为**true**，<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>将不会引发这种情况下; 但是，你的应用程序将很容易受到几种形式的 URI 分析攻击。</span><span class="sxs-lookup"><span data-stu-id="e21b4-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="e21b4-136">最佳解决方案是更改服务器，使响应不包含控制字符。</span><span class="sxs-lookup"><span data-stu-id="e21b4-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e21b4-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="e21b4-137">Configuration Files</span></span>  
 <span data-ttu-id="e21b4-138">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e21b4-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e21b4-139">示例</span><span class="sxs-lookup"><span data-stu-id="e21b4-139">Example</span></span>  
 <span data-ttu-id="e21b4-140">下面的示例演示如何指定更大超过正常的最大标头的长度。</span><span class="sxs-lookup"><span data-stu-id="e21b4-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e21b4-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e21b4-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="e21b4-142">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e21b4-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
