---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941893"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="f50b1-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="f50b1-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="f50b1-102"><xref:System.IdentityModel.Services.ChunkedCookieHandler>配置。</span><span class="sxs-lookup"><span data-stu-id="f50b1-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="f50b1-103">仅当`mode` `<cookieHandler>`元素的属性为 "默认值" 或 "分块" 时, 此元素才能存在。</span><span class="sxs-lookup"><span data-stu-id="f50b1-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="f50b1-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="f50b1-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="f50b1-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f50b1-105">\<federationConfiguration></span></span>  
<span data-ttu-id="f50b1-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="f50b1-106">\<cookieHandler></span></span>  
<span data-ttu-id="f50b1-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="f50b1-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50b1-108">语法</span><span class="sxs-lookup"><span data-stu-id="f50b1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f50b1-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f50b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f50b1-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f50b1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f50b1-111">特性</span><span class="sxs-lookup"><span data-stu-id="f50b1-111">Attributes</span></span>  
  
|<span data-ttu-id="f50b1-112">特性</span><span class="sxs-lookup"><span data-stu-id="f50b1-112">Attribute</span></span>|<span data-ttu-id="f50b1-113">描述</span><span class="sxs-lookup"><span data-stu-id="f50b1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f50b1-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="f50b1-114">chunkSize</span></span>|<span data-ttu-id="f50b1-115">任何一个 HTTP cookie 的 HTTP cookie 数据的最大大小 (字符数)。</span><span class="sxs-lookup"><span data-stu-id="f50b1-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="f50b1-116">调整块区大小时必须小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="f50b1-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="f50b1-117">Web 浏览器对 cookie 和每个域允许的数量有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="f50b1-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="f50b1-118">例如, 原 Netscape 规范规定这些限制:300 cookie 总数、每个 cookie 标头4096个字节 (包括元数据, 而不仅仅是 cookie 值) 和每个域20个 cookie。</span><span class="sxs-lookup"><span data-stu-id="f50b1-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="f50b1-119">默认值为2000。</span><span class="sxs-lookup"><span data-stu-id="f50b1-119">The default is 2000.</span></span> <span data-ttu-id="f50b1-120">必需。</span><span class="sxs-lookup"><span data-stu-id="f50b1-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f50b1-121">子元素</span><span class="sxs-lookup"><span data-stu-id="f50b1-121">Child Elements</span></span>  
 <span data-ttu-id="f50b1-122">无</span><span class="sxs-lookup"><span data-stu-id="f50b1-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f50b1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="f50b1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f50b1-124">元素</span><span class="sxs-lookup"><span data-stu-id="f50b1-124">Element</span></span>|<span data-ttu-id="f50b1-125">描述</span><span class="sxs-lookup"><span data-stu-id="f50b1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f50b1-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="f50b1-126">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="f50b1-127"><xref:System.IdentityModel.Services.CookieHandler> 配置(SAM)用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。</span><span class="sxs-lookup"><span data-stu-id="f50b1-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f50b1-128">备注</span><span class="sxs-lookup"><span data-stu-id="f50b1-128">Remarks</span></span>  
 <span data-ttu-id="f50b1-129"><xref:System.IdentityModel.Services.ChunkedCookieHandler>通过`<cookieHandler>` `<chunkedCookieHandler>`将元素的属性设置为"默认值"或"分块"来指定时,可以指定cookie处理程序用于通过包括子元素来读取和写入cookie的块区大小,`mode`设置其`chunkSize`属性。</span><span class="sxs-lookup"><span data-stu-id="f50b1-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="f50b1-130">如果该`<chunkedCookieHandler>`元素不存在, 则使用默认的块区大小 (2000 字节)。</span><span class="sxs-lookup"><span data-stu-id="f50b1-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="f50b1-131">当特性设置为 "Custom" `mode`时, 不能指定此元素。</span><span class="sxs-lookup"><span data-stu-id="f50b1-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="f50b1-132">元素由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类表示。 `<chunkedCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="f50b1-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f50b1-133">示例</span><span class="sxs-lookup"><span data-stu-id="f50b1-133">Example</span></span>  
 <span data-ttu-id="f50b1-134">下面的示例配置一个分块 cookie 处理程序, 该处理程序以3000字节的块写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="f50b1-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f50b1-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f50b1-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
