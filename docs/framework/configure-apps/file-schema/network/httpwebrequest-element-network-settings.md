---
title: <httpWebRequest> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: de5672e5c6762b1e0742e717a3d499a4f93ee8ec
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659344"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="4f210-102">\<httpWebRequest > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="4f210-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="4f210-103">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="4f210-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="4f210-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f210-104">\<configuration></span></span>  
<span data-ttu-id="4f210-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4f210-105">\<system.net></span></span>  
<span data-ttu-id="4f210-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="4f210-106">\<settings></span></span>  
<span data-ttu-id="4f210-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="4f210-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f210-108">语法</span><span class="sxs-lookup"><span data-stu-id="4f210-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f210-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4f210-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4f210-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4f210-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f210-111">特性</span><span class="sxs-lookup"><span data-stu-id="4f210-111">Attributes</span></span>  
  
|<span data-ttu-id="4f210-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="4f210-112">**Attribute**</span></span>|<span data-ttu-id="4f210-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f210-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="4f210-114">指定响应标头的最大长度 (以 kb 为单位)。</span><span class="sxs-lookup"><span data-stu-id="4f210-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="4f210-115">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="4f210-115">The default is 64.</span></span> <span data-ttu-id="4f210-116">如果值为-1, 则指示不会对响应标头施加大小限制。</span><span class="sxs-lookup"><span data-stu-id="4f210-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="4f210-117">指定错误响应的最大长度 (以 kb 为单位)。</span><span class="sxs-lookup"><span data-stu-id="4f210-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="4f210-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="4f210-118">The default is 64.</span></span> <span data-ttu-id="4f210-119">如果值为-1, 则表示不对错误响应施加大小限制。</span><span class="sxs-lookup"><span data-stu-id="4f210-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="4f210-120">指定用于响应未经授权的错误代码的上载的最大长度 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="4f210-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="4f210-121">默认值为 -1。</span><span class="sxs-lookup"><span data-stu-id="4f210-121">The default is -1.</span></span> <span data-ttu-id="4f210-122">如果值为-1, 则表示上传不会施加大小限制。</span><span class="sxs-lookup"><span data-stu-id="4f210-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="4f210-123">指定是否启用安全标头分析。</span><span class="sxs-lookup"><span data-stu-id="4f210-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="4f210-124">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4f210-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f210-125">子元素</span><span class="sxs-lookup"><span data-stu-id="4f210-125">Child Elements</span></span>  
 <span data-ttu-id="4f210-126">无。</span><span class="sxs-lookup"><span data-stu-id="4f210-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f210-127">父元素</span><span class="sxs-lookup"><span data-stu-id="4f210-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4f210-128">**元素**</span><span class="sxs-lookup"><span data-stu-id="4f210-128">**Element**</span></span>|<span data-ttu-id="4f210-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f210-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4f210-130">设置</span><span class="sxs-lookup"><span data-stu-id="4f210-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4f210-131">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="4f210-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f210-132">备注</span><span class="sxs-lookup"><span data-stu-id="4f210-132">Remarks</span></span>  
 <span data-ttu-id="4f210-133">默认情况下, .NET Framework 严格地强制执行 RFC 2616, 以便进行 URI 分析。</span><span class="sxs-lookup"><span data-stu-id="4f210-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="4f210-134">某些服务器响应可能在禁止字段中包含控制字符, 这将导致<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>方法<xref:System.Net.WebException>引发。</span><span class="sxs-lookup"><span data-stu-id="4f210-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="4f210-135">如果**useUnsafeHeaderParsing**设置为**true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>则在这种情况下将不会引发; 但是, 你的应用程序将容易受到多种形式的 URI 分析攻击的攻击。</span><span class="sxs-lookup"><span data-stu-id="4f210-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="4f210-136">最佳解决方案是更改服务器, 使响应不包含控制字符。</span><span class="sxs-lookup"><span data-stu-id="4f210-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4f210-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="4f210-137">Configuration Files</span></span>  
 <span data-ttu-id="4f210-138">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4f210-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f210-139">示例</span><span class="sxs-lookup"><span data-stu-id="4f210-139">Example</span></span>  
 <span data-ttu-id="4f210-140">下面的示例演示如何指定大于标准最大标头长度。</span><span class="sxs-lookup"><span data-stu-id="4f210-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f210-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f210-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="4f210-142">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4f210-142">Network Settings Schema</span></span>](index.md)
