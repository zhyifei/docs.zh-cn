---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="2a43f-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="2a43f-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="2a43f-103">配置<xref:System.IdentityModel.Services.ChunkedCookieHandler>。</span><span class="sxs-lookup"><span data-stu-id="2a43f-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="2a43f-104">此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"默认"块"。</span><span class="sxs-lookup"><span data-stu-id="2a43f-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="2a43f-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="2a43f-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="2a43f-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2a43f-106">\<federationConfiguration></span></span>  
<span data-ttu-id="2a43f-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2a43f-107">\<cookieHandler></span></span>  
<span data-ttu-id="2a43f-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2a43f-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a43f-109">语法</span><span class="sxs-lookup"><span data-stu-id="2a43f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a43f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2a43f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a43f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2a43f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a43f-112">特性</span><span class="sxs-lookup"><span data-stu-id="2a43f-112">Attributes</span></span>  
  
|<span data-ttu-id="2a43f-113">特性</span><span class="sxs-lookup"><span data-stu-id="2a43f-113">Attribute</span></span>|<span data-ttu-id="2a43f-114">描述</span><span class="sxs-lookup"><span data-stu-id="2a43f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a43f-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="2a43f-115">chunkSize</span></span>|<span data-ttu-id="2a43f-116">最大大小，以字符为单位的任何一个的 HTTP cookie 的 HTTP cookie 数据。</span><span class="sxs-lookup"><span data-stu-id="2a43f-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="2a43f-117">你必须调整块区大小时请小心。</span><span class="sxs-lookup"><span data-stu-id="2a43f-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="2a43f-118">Web 浏览器 cookie 和号允许每个域的大小具有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="2a43f-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="2a43f-119">例如，原始的 Netscape 规范规定这些限制： 总 300 cookie，每个 cookie 标头 （包括元数据，而不仅仅是 cookie 值），4096 个字节和每个域的 20 cookie。</span><span class="sxs-lookup"><span data-stu-id="2a43f-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="2a43f-120">默认值为 2000年。</span><span class="sxs-lookup"><span data-stu-id="2a43f-120">The default is 2000.</span></span> <span data-ttu-id="2a43f-121">必须的。</span><span class="sxs-lookup"><span data-stu-id="2a43f-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a43f-122">子元素</span><span class="sxs-lookup"><span data-stu-id="2a43f-122">Child Elements</span></span>  
 <span data-ttu-id="2a43f-123">无</span><span class="sxs-lookup"><span data-stu-id="2a43f-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a43f-124">父元素</span><span class="sxs-lookup"><span data-stu-id="2a43f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2a43f-125">元素</span><span class="sxs-lookup"><span data-stu-id="2a43f-125">Element</span></span>|<span data-ttu-id="2a43f-126">描述</span><span class="sxs-lookup"><span data-stu-id="2a43f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a43f-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2a43f-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="2a43f-128">配置<xref:System.IdentityModel.Services.CookieHandler>， <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="2a43f-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a43f-129">备注</span><span class="sxs-lookup"><span data-stu-id="2a43f-129">Remarks</span></span>  
 <span data-ttu-id="2a43f-130">当指定<xref:System.IdentityModel.Services.ChunkedCookieHandler>通过设置`mode`属性`<cookieHandler>`到"默认"或"Chunked"的元素，可以指定的 cookie 处理使用来读取和写入 cookie 包括块区大小`<chunkedCookieHandler>`子元素和设置其`chunkSize`属性。</span><span class="sxs-lookup"><span data-stu-id="2a43f-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="2a43f-131">如果`<chunkedCookieHandler>`元素不存在，则使用默认块区大小的 2000 个字节。</span><span class="sxs-lookup"><span data-stu-id="2a43f-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="2a43f-132">此元素不能为时指定`mode`属性设置为"Custom"。</span><span class="sxs-lookup"><span data-stu-id="2a43f-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="2a43f-133">`<chunkedCookieHandler>`元素表示由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类。</span><span class="sxs-lookup"><span data-stu-id="2a43f-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a43f-134">示例</span><span class="sxs-lookup"><span data-stu-id="2a43f-134">Example</span></span>  
 <span data-ttu-id="2a43f-135">下面的示例配置中的 3000 个字节块写入 cookie 分块的 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="2a43f-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a43f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a43f-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
