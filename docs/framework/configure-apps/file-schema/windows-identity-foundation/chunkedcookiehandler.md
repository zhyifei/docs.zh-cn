---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: f5592e0fd02d34b2882182196e0aa9425672a8fe
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792832"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="ddcfd-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="ddcfd-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="ddcfd-103">配置<xref:System.IdentityModel.Services.ChunkedCookieHandler>。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="ddcfd-104">此元素仅可能存在如果`mode`属性的`<cookieHandler>`元素是"Default"块"。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="ddcfd-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="ddcfd-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="ddcfd-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ddcfd-106">\<federationConfiguration></span></span>  
<span data-ttu-id="ddcfd-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="ddcfd-107">\<cookieHandler></span></span>  
<span data-ttu-id="ddcfd-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="ddcfd-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcfd-109">语法</span><span class="sxs-lookup"><span data-stu-id="ddcfd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddcfd-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ddcfd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ddcfd-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddcfd-112">特性</span><span class="sxs-lookup"><span data-stu-id="ddcfd-112">Attributes</span></span>  
  
|<span data-ttu-id="ddcfd-113">特性</span><span class="sxs-lookup"><span data-stu-id="ddcfd-113">Attribute</span></span>|<span data-ttu-id="ddcfd-114">描述</span><span class="sxs-lookup"><span data-stu-id="ddcfd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddcfd-115">块区大小</span><span class="sxs-lookup"><span data-stu-id="ddcfd-115">chunkSize</span></span>|<span data-ttu-id="ddcfd-116">最大大小，以字符为单位的任何一个 HTTP cookie 的 HTTP cookie 数据。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="ddcfd-117">您必须是块区大小调整时请小心。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="ddcfd-118">Web 浏览器 cookie 和每个域允许数量的大小具有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="ddcfd-119">例如，原始 Netscape 规范规定这些限制： 总 300 cookie，cookie 标头 （包括元数据，而不仅仅是 cookie 值），每 4096 字节数和每个域的 20 cookie。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="ddcfd-120">默认值为 2000年。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-120">The default is 2000.</span></span> <span data-ttu-id="ddcfd-121">必须的。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddcfd-122">子元素</span><span class="sxs-lookup"><span data-stu-id="ddcfd-122">Child Elements</span></span>  
 <span data-ttu-id="ddcfd-123">无</span><span class="sxs-lookup"><span data-stu-id="ddcfd-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddcfd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ddcfd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ddcfd-125">元素</span><span class="sxs-lookup"><span data-stu-id="ddcfd-125">Element</span></span>|<span data-ttu-id="ddcfd-126">描述</span><span class="sxs-lookup"><span data-stu-id="ddcfd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddcfd-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="ddcfd-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="ddcfd-128">配置<xref:System.IdentityModel.Services.CookieHandler>的<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) 用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddcfd-129">备注</span><span class="sxs-lookup"><span data-stu-id="ddcfd-129">Remarks</span></span>  
 <span data-ttu-id="ddcfd-130">当指定<xref:System.IdentityModel.Services.ChunkedCookieHandler>通过设置`mode`的属性`<cookieHandler>`为"Default"或"Chunked"元素，可以指定块的大小的 cookie 处理程序用来读取和写入 cookie 包括`<chunkedCookieHandler>`子元素和设置其`chunkSize`属性。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="ddcfd-131">如果`<chunkedCookieHandler>`元素不存在，则使用默认区块大小的 2000 个字节。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="ddcfd-132">不能为此元素时指定`mode`属性设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="ddcfd-133">`<chunkedCookieHandler>`元素表示由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddcfd-134">示例</span><span class="sxs-lookup"><span data-stu-id="ddcfd-134">Example</span></span>  
 <span data-ttu-id="ddcfd-135">下面的示例配置中的 3000 个字节块写入 cookie chunked 的 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="ddcfd-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddcfd-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddcfd-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
