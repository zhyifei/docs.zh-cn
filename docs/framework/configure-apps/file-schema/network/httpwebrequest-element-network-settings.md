---
title: '&lt;httpWebRequest&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e83f12d849f6f6a587bccc85fbf6fe8fe24026f0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108099"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="82e5f-102">&lt;httpWebRequest&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="82e5f-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="82e5f-103">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="82e5f-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="82e5f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="82e5f-104">\<configuration></span></span>  
<span data-ttu-id="82e5f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="82e5f-105">\<system.net></span></span>  
<span data-ttu-id="82e5f-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="82e5f-106">\<settings></span></span>  
<span data-ttu-id="82e5f-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="82e5f-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e5f-108">语法</span><span class="sxs-lookup"><span data-stu-id="82e5f-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82e5f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82e5f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="82e5f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="82e5f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82e5f-111">特性</span><span class="sxs-lookup"><span data-stu-id="82e5f-111">Attributes</span></span>  
  
|<span data-ttu-id="82e5f-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="82e5f-112">**Attribute**</span></span>|<span data-ttu-id="82e5f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="82e5f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="82e5f-114">指定以千字节为单位的响应标头的最大长度。</span><span class="sxs-lookup"><span data-stu-id="82e5f-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="82e5f-115">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="82e5f-115">The default is 64.</span></span> <span data-ttu-id="82e5f-116">值为-1 指示没有大小限制将施加的响应标头。</span><span class="sxs-lookup"><span data-stu-id="82e5f-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="82e5f-117">指定的最大长度的错误响应，以千字节为单位。</span><span class="sxs-lookup"><span data-stu-id="82e5f-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="82e5f-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="82e5f-118">The default is 64.</span></span> <span data-ttu-id="82e5f-119">值为-1 指示没有大小限制将施加的错误响应。</span><span class="sxs-lookup"><span data-stu-id="82e5f-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="82e5f-120">在响应未经授权的错误代码，以字节为单位指定上传的最大长度。</span><span class="sxs-lookup"><span data-stu-id="82e5f-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="82e5f-121">默认值为 -1。</span><span class="sxs-lookup"><span data-stu-id="82e5f-121">The default is -1.</span></span> <span data-ttu-id="82e5f-122">值为-1 指示，将对上载施加没有大小限制。</span><span class="sxs-lookup"><span data-stu-id="82e5f-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="82e5f-123">指定是否启用不安全标题解析。</span><span class="sxs-lookup"><span data-stu-id="82e5f-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="82e5f-124">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="82e5f-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82e5f-125">子元素</span><span class="sxs-lookup"><span data-stu-id="82e5f-125">Child Elements</span></span>  
 <span data-ttu-id="82e5f-126">无。</span><span class="sxs-lookup"><span data-stu-id="82e5f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82e5f-127">父元素</span><span class="sxs-lookup"><span data-stu-id="82e5f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="82e5f-128">**元素**</span><span class="sxs-lookup"><span data-stu-id="82e5f-128">**Element**</span></span>|<span data-ttu-id="82e5f-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="82e5f-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82e5f-130">设置</span><span class="sxs-lookup"><span data-stu-id="82e5f-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="82e5f-131">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="82e5f-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82e5f-132">备注</span><span class="sxs-lookup"><span data-stu-id="82e5f-132">Remarks</span></span>  
 <span data-ttu-id="82e5f-133">默认情况下，.NET Framework 将严格强制执行 RFC 2616 的 URI 分析。</span><span class="sxs-lookup"><span data-stu-id="82e5f-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="82e5f-134">某些服务器响应可能包含控制字符，在被禁止字段中，这将导致<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>方法会引发<xref:System.Net.WebException>。</span><span class="sxs-lookup"><span data-stu-id="82e5f-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="82e5f-135">如果**useUnsafeHeaderParsing**设置为**true**，<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>不会引发这种情况下; 但是，你的应用程序将很容易受到几种形式的 URI 分析攻击。</span><span class="sxs-lookup"><span data-stu-id="82e5f-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="82e5f-136">最佳解决方案是更改的服务器，以便响应不包含控制字符。</span><span class="sxs-lookup"><span data-stu-id="82e5f-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="82e5f-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="82e5f-137">Configuration Files</span></span>  
 <span data-ttu-id="82e5f-138">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="82e5f-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82e5f-139">示例</span><span class="sxs-lookup"><span data-stu-id="82e5f-139">Example</span></span>  
 <span data-ttu-id="82e5f-140">下面的示例演示如何指定一个较大比正常的最大标头长度。</span><span class="sxs-lookup"><span data-stu-id="82e5f-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82e5f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="82e5f-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="82e5f-142">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="82e5f-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
