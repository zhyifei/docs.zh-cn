---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252111"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="d4521-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="d4521-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="d4521-102"><xref:System.IdentityModel.Services.ChunkedCookieHandler>配置。</span><span class="sxs-lookup"><span data-stu-id="d4521-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="d4521-103">仅当`mode` `<cookieHandler>`元素的属性为 "默认值" 或 "分块" 时，此元素才能存在。</span><span class="sxs-lookup"><span data-stu-id="d4521-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="d4521-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4521-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4521-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="d4521-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="d4521-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d4521-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="d4521-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="d4521-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="d4521-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<chunkedCookieHandler >**</span><span class="sxs-lookup"><span data-stu-id="d4521-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4521-109">语法</span><span class="sxs-lookup"><span data-stu-id="d4521-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4521-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4521-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d4521-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d4521-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4521-112">特性</span><span class="sxs-lookup"><span data-stu-id="d4521-112">Attributes</span></span>  
  
|<span data-ttu-id="d4521-113">特性</span><span class="sxs-lookup"><span data-stu-id="d4521-113">Attribute</span></span>|<span data-ttu-id="d4521-114">描述</span><span class="sxs-lookup"><span data-stu-id="d4521-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4521-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="d4521-115">chunkSize</span></span>|<span data-ttu-id="d4521-116">任何一个 HTTP cookie 的 HTTP cookie 数据的最大大小（字符数）。</span><span class="sxs-lookup"><span data-stu-id="d4521-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="d4521-117">调整块区大小时必须小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="d4521-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="d4521-118">Web 浏览器对 cookie 和每个域允许的数量有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="d4521-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="d4521-119">例如，原 Netscape 规范规定这些限制：300 cookie 总数、每个 cookie 标头4096个字节（包括元数据，而不仅仅是 cookie 值）和每个域20个 cookie。</span><span class="sxs-lookup"><span data-stu-id="d4521-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="d4521-120">默认值为2000。</span><span class="sxs-lookup"><span data-stu-id="d4521-120">The default is 2000.</span></span> <span data-ttu-id="d4521-121">必需。</span><span class="sxs-lookup"><span data-stu-id="d4521-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4521-122">子元素</span><span class="sxs-lookup"><span data-stu-id="d4521-122">Child Elements</span></span>  
 <span data-ttu-id="d4521-123">无</span><span class="sxs-lookup"><span data-stu-id="d4521-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4521-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d4521-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d4521-125">元素</span><span class="sxs-lookup"><span data-stu-id="d4521-125">Element</span></span>|<span data-ttu-id="d4521-126">描述</span><span class="sxs-lookup"><span data-stu-id="d4521-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4521-127">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="d4521-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="d4521-128"><xref:System.IdentityModel.Services.CookieHandler> 配置（SAM）用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。</span><span class="sxs-lookup"><span data-stu-id="d4521-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4521-129">备注</span><span class="sxs-lookup"><span data-stu-id="d4521-129">Remarks</span></span>  
 <span data-ttu-id="d4521-130"><xref:System.IdentityModel.Services.ChunkedCookieHandler>通过`<cookieHandler>` `<chunkedCookieHandler>`将元素的属性设置为"默认值"或"分块"来指定时，可以指定cookie处理程序用于通过包括子元素来读取和写入cookie的块区大小，`mode`设置其`chunkSize`属性。</span><span class="sxs-lookup"><span data-stu-id="d4521-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="d4521-131">如果该`<chunkedCookieHandler>`元素不存在，则使用默认的块区大小（2000字节）。</span><span class="sxs-lookup"><span data-stu-id="d4521-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="d4521-132">当特性设置为 "Custom" `mode`时，不能指定此元素。</span><span class="sxs-lookup"><span data-stu-id="d4521-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="d4521-133">元素由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类表示。 `<chunkedCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="d4521-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4521-134">示例</span><span class="sxs-lookup"><span data-stu-id="d4521-134">Example</span></span>  
 <span data-ttu-id="d4521-135">下面的示例配置一个分块 cookie 处理程序，该处理程序以3000字节的块写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="d4521-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4521-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4521-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
