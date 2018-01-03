---
title: '&lt;cookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 302ccb3d95fc982ec7950dc7808dce61b263c481
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcookiehandlergt"></a><span data-ttu-id="407ab-102">&lt;cookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="407ab-102">&lt;cookieHandler&gt;</span></span>
<span data-ttu-id="407ab-103">配置<xref:System.IdentityModel.Services.CookieHandler>， <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="407ab-103">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>  
  
 <span data-ttu-id="407ab-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="407ab-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="407ab-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="407ab-105">\<federationConfiguration></span></span>  
<span data-ttu-id="407ab-106">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="407ab-106">\<cookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="407ab-107">语法</span><span class="sxs-lookup"><span data-stu-id="407ab-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="407ab-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="407ab-108">Attributes and Elements</span></span>  
 <span data-ttu-id="407ab-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="407ab-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="407ab-110">特性</span><span class="sxs-lookup"><span data-stu-id="407ab-110">Attributes</span></span>  
  
|<span data-ttu-id="407ab-111">特性</span><span class="sxs-lookup"><span data-stu-id="407ab-111">Attribute</span></span>|<span data-ttu-id="407ab-112">描述</span><span class="sxs-lookup"><span data-stu-id="407ab-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="407ab-113">name</span><span class="sxs-lookup"><span data-stu-id="407ab-113">name</span></span>|<span data-ttu-id="407ab-114">指定任何已编写 cookie 的基名称。</span><span class="sxs-lookup"><span data-stu-id="407ab-114">Specifies the base name for any cookies written.</span></span> <span data-ttu-id="407ab-115">默认值为"FedAuth"。</span><span class="sxs-lookup"><span data-stu-id="407ab-115">The default is "FedAuth".</span></span>|  
|<span data-ttu-id="407ab-116">path</span><span class="sxs-lookup"><span data-stu-id="407ab-116">path</span></span>|<span data-ttu-id="407ab-117">指定任何已编写 cookie 的路径值。</span><span class="sxs-lookup"><span data-stu-id="407ab-117">Specifies the path value for any cookies written.</span></span> <span data-ttu-id="407ab-118">默认值为"HttpRuntime.AppDomainAppVirtualPath"。</span><span class="sxs-lookup"><span data-stu-id="407ab-118">The default is "HttpRuntime.AppDomainAppVirtualPath".</span></span>|  
|<span data-ttu-id="407ab-119">mode</span><span class="sxs-lookup"><span data-stu-id="407ab-119">mode</span></span>|<span data-ttu-id="407ab-120">之一<xref:System.IdentityModel.Services.CookieHandlerMode>指定 SAM 所用的 cookie 处理程序的类型的值。</span><span class="sxs-lookup"><span data-stu-id="407ab-120">One of the <xref:System.IdentityModel.Services.CookieHandlerMode> values that specifies the kind of cookie handler used by the SAM.</span></span> <span data-ttu-id="407ab-121">可以使用以下值：</span><span class="sxs-lookup"><span data-stu-id="407ab-121">The following values may be used:</span></span><br /><br /> <span data-ttu-id="407ab-122">-"默认"-"Chunked"相同。</span><span class="sxs-lookup"><span data-stu-id="407ab-122">-   "Default" — The same as "Chunked".</span></span><br /><span data-ttu-id="407ab-123">-"分块"-使用的是实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="407ab-123">-   "Chunked" — Uses an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="407ab-124">此 cookie 处理程序可确保各个 cookie 不能超过集的最大大小。</span><span class="sxs-lookup"><span data-stu-id="407ab-124">This cookie handler ensures that individual cookies do not exceed a set maximum size.</span></span> <span data-ttu-id="407ab-125">通过可能"分块"一个逻辑 cookie，为多个 cookie 上在线完成此操作。</span><span class="sxs-lookup"><span data-stu-id="407ab-125">It accomplishes this by potentially "chunking" one logical cookie into a number of cookies on-the-wire.</span></span><br /><span data-ttu-id="407ab-126">-"Custom"-使用派生自的自定义类的实例<xref:System.IdentityModel.Services.CookieHandler>。</span><span class="sxs-lookup"><span data-stu-id="407ab-126">-   "Custom" — Uses an instance of a custom class derived from <xref:System.IdentityModel.Services.CookieHandler>.</span></span> <span data-ttu-id="407ab-127">派生的类引用的`<customCookieHandler>`子元素。</span><span class="sxs-lookup"><span data-stu-id="407ab-127">The derived class is referenced by the `<customCookieHandler>` child element.</span></span><br /><br /> <span data-ttu-id="407ab-128">默认值为"Default"。</span><span class="sxs-lookup"><span data-stu-id="407ab-128">The default is "Default".</span></span>|  
|<span data-ttu-id="407ab-129">persistentSessionLifetime</span><span class="sxs-lookup"><span data-stu-id="407ab-129">persistentSessionLifetime</span></span>|<span data-ttu-id="407ab-130">指定持久性会话的生存期。</span><span class="sxs-lookup"><span data-stu-id="407ab-130">Specifies the lifetime of persistent sessions.</span></span> <span data-ttu-id="407ab-131">如果为零，始终使用临时会话。</span><span class="sxs-lookup"><span data-stu-id="407ab-131">If zero, transient sessions are always used.</span></span> <span data-ttu-id="407ab-132">默认值为"0:0:0"，指定的临时会话。</span><span class="sxs-lookup"><span data-stu-id="407ab-132">The default value is "0:0:0", which specifies a transient session.</span></span> <span data-ttu-id="407ab-133">最大值为"365:0:0"，指定的 365 天内的会话。</span><span class="sxs-lookup"><span data-stu-id="407ab-133">The maximum value is "365:0:0", which specifies a session of 365 days.</span></span> <span data-ttu-id="407ab-134">应根据以下限制指定的值： `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`，其中最左侧的值指定天数、 中间值 （如果有） 指定小时数，并最右侧的值 （如果有） 指定的分钟数。</span><span class="sxs-lookup"><span data-stu-id="407ab-134">The value should be specified according to the following restriction: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, where the leftmost value specifies days, the middle value (if present) specifies hours, and the rightmost value (if present) specifies minutes.</span></span>|  
|<span data-ttu-id="407ab-135">RequireSsl</span><span class="sxs-lookup"><span data-stu-id="407ab-135">requireSsl</span></span>|<span data-ttu-id="407ab-136">指定是否有任何已编写 cookie 发出"安全"标志。</span><span class="sxs-lookup"><span data-stu-id="407ab-136">Specifies whether the "Secure" flag is emitted for any cookies written.</span></span> <span data-ttu-id="407ab-137">如果设置此值，在登录会话 cookie 将仅可通过 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="407ab-137">If this value is set, the sign-in session cookies will only be available over HTTPS.</span></span> <span data-ttu-id="407ab-138">默认值为“true”。</span><span class="sxs-lookup"><span data-stu-id="407ab-138">The default is "true".</span></span>|  
|<span data-ttu-id="407ab-139">hideFromScript</span><span class="sxs-lookup"><span data-stu-id="407ab-139">hideFromScript</span></span>|<span data-ttu-id="407ab-140">控制是否有任何已编写 cookie 发出"HttpOnly"标志。</span><span class="sxs-lookup"><span data-stu-id="407ab-140">Controls whether the "HttpOnly" flag is emitted for any cookies written.</span></span> <span data-ttu-id="407ab-141">某些 web 浏览器通过阻止客户端脚本访问的 cookie 值接受此标志。</span><span class="sxs-lookup"><span data-stu-id="407ab-141">Certain web browsers honor this flag by keeping client-side script from accessing the cookie value.</span></span> <span data-ttu-id="407ab-142">默认值为“true”。</span><span class="sxs-lookup"><span data-stu-id="407ab-142">The default is "true".</span></span>|  
|<span data-ttu-id="407ab-143">域</span><span class="sxs-lookup"><span data-stu-id="407ab-143">domain</span></span>|<span data-ttu-id="407ab-144">任何已编写 cookie 域值。</span><span class="sxs-lookup"><span data-stu-id="407ab-144">The domain value for any cookies written.</span></span> <span data-ttu-id="407ab-145">默认值为 ""。</span><span class="sxs-lookup"><span data-stu-id="407ab-145">The default is "".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="407ab-146">子元素</span><span class="sxs-lookup"><span data-stu-id="407ab-146">Child Elements</span></span>  
  
|<span data-ttu-id="407ab-147">元素</span><span class="sxs-lookup"><span data-stu-id="407ab-147">Element</span></span>|<span data-ttu-id="407ab-148">描述</span><span class="sxs-lookup"><span data-stu-id="407ab-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="407ab-149">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="407ab-149">\<chunkedCookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|<span data-ttu-id="407ab-150">配置<xref:System.IdentityModel.Services.ChunkedCookieHandler>。</span><span class="sxs-lookup"><span data-stu-id="407ab-150">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="407ab-151">此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"默认"块"。</span><span class="sxs-lookup"><span data-stu-id="407ab-151">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>|  
|[<span data-ttu-id="407ab-152">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="407ab-152">\<customCookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|<span data-ttu-id="407ab-153">设置自定义 cookie 处理程序类型。</span><span class="sxs-lookup"><span data-stu-id="407ab-153">Sets the custom cookie handler type.</span></span> <span data-ttu-id="407ab-154">此元素必须存在如果`mode`属性`<cookieHandler>`元素是"自定义"。</span><span class="sxs-lookup"><span data-stu-id="407ab-154">This element must be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="407ab-155">它不能出现的任何其他值`mode`属性。</span><span class="sxs-lookup"><span data-stu-id="407ab-155">It cannot be present for any other values of the `mode` attribute.</span></span> <span data-ttu-id="407ab-156">自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="407ab-156">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="407ab-157">父元素</span><span class="sxs-lookup"><span data-stu-id="407ab-157">Parent Elements</span></span>  
  
|<span data-ttu-id="407ab-158">元素</span><span class="sxs-lookup"><span data-stu-id="407ab-158">Element</span></span>|<span data-ttu-id="407ab-159">描述</span><span class="sxs-lookup"><span data-stu-id="407ab-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="407ab-160">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="407ab-160">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="407ab-161">包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="407ab-161">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="407ab-162">备注</span><span class="sxs-lookup"><span data-stu-id="407ab-162">Remarks</span></span>  
 <span data-ttu-id="407ab-163"><xref:System.IdentityModel.Services.CookieHandler>负责读取和写入原始 cookie 在 HTTP 协议级别。</span><span class="sxs-lookup"><span data-stu-id="407ab-163">The <xref:System.IdentityModel.Services.CookieHandler> is responsible for reading and writing raw cookies at the HTTP protocol level.</span></span> <span data-ttu-id="407ab-164">你可以配置任一<xref:System.IdentityModel.Services.ChunkedCookieHandler>或从派生自定义 cookie 处理程序<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="407ab-164">You can configure either a <xref:System.IdentityModel.Services.ChunkedCookieHandler> or a custom cookie handler derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="407ab-165">若要配置分块的 cookie 处理程序，将模式特性设置为"Chunked"或"默认"。</span><span class="sxs-lookup"><span data-stu-id="407ab-165">To configure a chunked cookie handler, set the mode attribute to "Chunked" or "Default".</span></span> <span data-ttu-id="407ab-166">默认块区大小为 2000 个字节，但您可以通过包括 （可选） 指定的不同区块大小`<chunkedCookieHandler>`子元素。</span><span class="sxs-lookup"><span data-stu-id="407ab-166">The default chunk size is 2000 bytes, but you may optionally specify a different chunk size by including a `<chunkedCookieHandler>` child element.</span></span>  
  
 <span data-ttu-id="407ab-167">若要配置自定义 cookie 处理程序，将模式特性设置为"Custom"。</span><span class="sxs-lookup"><span data-stu-id="407ab-167">To configure a custom cookie handler, set the mode attribute to "Custom".</span></span> <span data-ttu-id="407ab-168">你还必须指定`<customCookieHandler>`引用自定义处理程序的类型的子元素。</span><span class="sxs-lookup"><span data-stu-id="407ab-168">You must also specify a `<customCookieHandler>` child element that references the type of your custom handler.</span></span>  
  
 <span data-ttu-id="407ab-169">`<cookieHandler>`元素表示由<xref:System.IdentityModel.Services.CookieHandlerElement>类。</span><span class="sxs-lookup"><span data-stu-id="407ab-169">The `<cookieHandler>` element is represented by the <xref:System.IdentityModel.Services.CookieHandlerElement> class.</span></span> <span data-ttu-id="407ab-170">已在配置中指定该 cookie 处理程序可从<xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A>属性<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象上设置<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="407ab-170">The cookie handler that was specified in configuration is available from the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> property of the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="407ab-171">示例</span><span class="sxs-lookup"><span data-stu-id="407ab-171">Example</span></span>  
 <span data-ttu-id="407ab-172">下面的 XML 演示`<cookieHandler>`元素。</span><span class="sxs-lookup"><span data-stu-id="407ab-172">The following XML shows a `<cookieHandler>` element.</span></span> <span data-ttu-id="407ab-173">在此示例中，因为`mode`未指定属性时，将通过 SAM 使用默认 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="407ab-173">In this example, because the `mode` attribute is not specified, the default cookie handler will be used by the SAM.</span></span> <span data-ttu-id="407ab-174">这是实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="407ab-174">This is an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="407ab-175">因为`<chunkedCookieHandler>`未指定子元素时，将使用默认块区大小。</span><span class="sxs-lookup"><span data-stu-id="407ab-175">Because the `<chunkedCookieHandler>` child element is not specified, the default chunk size will be used.</span></span> <span data-ttu-id="407ab-176">HTTPS 不是所需因为`requireSsl`特性设置`false`。</span><span class="sxs-lookup"><span data-stu-id="407ab-176">HTTPS will not be required because the `requireSsl` attribute is set `false`.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="407ab-177">在此示例中，不需要 HTTPS 编写会话 cookie。</span><span class="sxs-lookup"><span data-stu-id="407ab-177">In this example, HTTPS is not required to write session cookies.</span></span> <span data-ttu-id="407ab-178">这是因为`requireSsl`属性`<cookieHandler>`元素设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="407ab-178">This is because the `requireSsl` attribute on the `<cookieHandler>` element is set to `false`.</span></span> <span data-ttu-id="407ab-179">对于大多数生产环境不被建议此设置，因为它可能存在安全风险。</span><span class="sxs-lookup"><span data-stu-id="407ab-179">This setting is not recommended for most production environments as it may present a security risk.</span></span>  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="407ab-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="407ab-180">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
