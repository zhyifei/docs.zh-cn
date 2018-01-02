---
title: "&lt;httpListener&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 8d880583016e6ccc0ae57fea10c35cb32726c93e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lthttplistenergt-element-network-settings"></a><span data-ttu-id="aaa6d-102">&lt;httpListener&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="aaa6d-102">&lt;httpListener&gt; Element (Network Settings)</span></span>
<span data-ttu-id="aaa6d-103">自定义所使用参数<xref:System.Net.HttpListener>类。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="aaa6d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="aaa6d-104">\<configuration></span></span>  
<span data-ttu-id="aaa6d-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="aaa6d-105">\<system.net></span></span>  
<span data-ttu-id="aaa6d-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="aaa6d-106">\<settings></span></span>  
<span data-ttu-id="aaa6d-107">\<httpListener ></span><span class="sxs-lookup"><span data-stu-id="aaa6d-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa6d-108">语法</span><span class="sxs-lookup"><span data-stu-id="aaa6d-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="aaa6d-109">类型</span><span class="sxs-lookup"><span data-stu-id="aaa6d-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaa6d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aaa6d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aaa6d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaa6d-112">特性</span><span class="sxs-lookup"><span data-stu-id="aaa6d-112">Attributes</span></span>  
  
|<span data-ttu-id="aaa6d-113">特性</span><span class="sxs-lookup"><span data-stu-id="aaa6d-113">Attribute</span></span>|<span data-ttu-id="aaa6d-114">描述</span><span class="sxs-lookup"><span data-stu-id="aaa6d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaa6d-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="aaa6d-115">unescapeRequestUrl</span></span>|<span data-ttu-id="aaa6d-116">一个布尔值，该值指示如果<xref:System.Net.HttpListener>实例使用的原始的未转义的 URI 而不是转换后的 URI。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaa6d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="aaa6d-117">Child Elements</span></span>  
 <span data-ttu-id="aaa6d-118">无。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aaa6d-119">父元素</span><span class="sxs-lookup"><span data-stu-id="aaa6d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="aaa6d-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="aaa6d-120">**Element**</span></span>|<span data-ttu-id="aaa6d-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="aaa6d-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aaa6d-122">设置</span><span class="sxs-lookup"><span data-stu-id="aaa6d-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="aaa6d-123">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa6d-124">备注</span><span class="sxs-lookup"><span data-stu-id="aaa6d-124">Remarks</span></span>  
 <span data-ttu-id="aaa6d-125">**UnescapeRequestUrl**属性指示如果<xref:System.Net.HttpListener>而不是转换后的 URI 其中百分比编码的任何值都会转换，并执行其他任何规范化步骤使用原始的未转义的 URI。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="aaa6d-126">当<xref:System.Net.HttpListener>实例收到的请求通过`http.sys`服务，它创建提供的 URI 字符串的实例`http.sys`，并将数据公开为<xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="aaa6d-127">`http.sys`服务公开两个请求 URI 字符串：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
-   <span data-ttu-id="aaa6d-128">原始 URI</span><span class="sxs-lookup"><span data-stu-id="aaa6d-128">Raw URI</span></span>  
  
-   <span data-ttu-id="aaa6d-129">转换后的 URI</span><span class="sxs-lookup"><span data-stu-id="aaa6d-129">Converted URI</span></span>  
  
 <span data-ttu-id="aaa6d-130">原始 URI 是<xref:System.Uri?displayProperty=nameWithType>HTTP 请求的请求行中提供：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="aaa6d-131">通过提供的原始 URI`http.sys`上述，请求为"/ 路径 /"。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="aaa6d-132">这表示在通过网络发送后面的 HTTP 谓词的字符串。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="aaa6d-133">`http.sys`服务从请求中提供通过使用 HTTP 请求行中提供的 URI 的信息创建一个转换后的 URI 和要确定源服务器请求的主机标头应转发到。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="aaa6d-134">这是通过比较中使用一组的已注册的 URI 前缀请求的信息。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="aaa6d-135">HTTP 服务器 SDK 文档的此转换后的 URI 指的是 HTTP_COOKED_URL 结构。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="aaa6d-136">为了能够比较该请求与已注册的 URI 前缀，需要进行一些规范化到请求。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="aaa6d-137">对于上面的转换后的 URI 的示例将为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="aaa6d-138">`http.sys`服务结合<xref:System.Uri.Host%2A?displayProperty=nameWithType>属性值和请求行来创建转换后的 URI 中的字符串。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="aaa6d-139">此外，`http.sys`和<xref:System.Uri?displayProperty=nameWithType>类也会执行以下：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
-   <span data-ttu-id="aaa6d-140">取消转义所有百分比编码值。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-140">Un-escapes all percent encoded values.</span></span>  
  
-   <span data-ttu-id="aaa6d-141">将转换百分比编码为 utf-16 字符表示形式的非 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="aaa6d-142">请注意，以及 Unicode 字符 （Unicode 编码使用 %uxxxx 格式） 支持 utf-8 和 ANSI/DBCS 字符。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
-   <span data-ttu-id="aaa6d-143">执行其他规范化步骤，如路径压缩。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="aaa6d-144">请求不包含有关用于百分比编码值的编码的任何信息，因为它可能不能以确定正确的编码只是通过分析百分比编码值。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="aaa6d-145">因此`http.sys`提供用于修改进程的两个注册表项：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="aaa6d-146">注册表项</span><span class="sxs-lookup"><span data-stu-id="aaa6d-146">Registry Key</span></span>|<span data-ttu-id="aaa6d-147">默认值</span><span class="sxs-lookup"><span data-stu-id="aaa6d-147">Default Value</span></span>|<span data-ttu-id="aaa6d-148">描述</span><span class="sxs-lookup"><span data-stu-id="aaa6d-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="aaa6d-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="aaa6d-149">EnableNonUTF8</span></span>|<span data-ttu-id="aaa6d-150">1</span><span class="sxs-lookup"><span data-stu-id="aaa6d-150">1</span></span>|<span data-ttu-id="aaa6d-151">如果为零，`http.sys`接受仅 UTF 8 编码的 Url。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="aaa6d-152">如果非零，`http.sys`还接受在请求中的 ANSI 编码或 DBCS 编码的 Url。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="aaa6d-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="aaa6d-153">FavorUTF8</span></span>|<span data-ttu-id="aaa6d-154">1</span><span class="sxs-lookup"><span data-stu-id="aaa6d-154">1</span></span>|<span data-ttu-id="aaa6d-155">如果非零，`http.sys`始终尝试解码 URL 为 utf-8 首先; 如果转换失败和 EnableNonUTF8 为非零，Http.sys 然后尝试对其进行解码为 ANSI 或 DBCS。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="aaa6d-156">如果为零 （和 EnableNonUTF8 为非零），`http.sys`尝试对其进行解码为 ANSI 或 DBCS; 如果该操作不成功，它会尝试 utf-8 转换。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="aaa6d-157">当<xref:System.Net.HttpListener>收到请求时，它使用转换后的 URI 从`http.sys`作为输入到<xref:System.Net.HttpListenerRequest.Url%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="aaa6d-158">没有需要在 Uri 中支持除了字符和数字的字符。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="aaa6d-159">一个示例是下面的 URI，用于检索客户的客户信息数字"1/3812":</span><span class="sxs-lookup"><span data-stu-id="aaa6d-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="aaa6d-160">请注意 Uri (%2f) 中的百分号编码斜杠。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="aaa6d-161">因为在这种情况下包含斜杠字符表示数据而不是路径分隔符，这是必需的。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="aaa6d-162">将字符串传递给 Uri 构造函数将导致以下 URI:</span><span class="sxs-lookup"><span data-stu-id="aaa6d-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="aaa6d-163">将路径拆分为其段将导致以下元素：</span><span class="sxs-lookup"><span data-stu-id="aaa6d-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="aaa6d-164">这不是请求的发送方的意图。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="aaa6d-165">如果**unescapeRequestUrl**属性设置为**false**，然后当<xref:System.Net.HttpListener>收到请求时，它使用的原始 URI 而不是转换后 URI`http.sys`作为的输入<xref:System.Net.HttpListenerRequest.Url%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="aaa6d-166">默认值为**unescapeRequestUrl**属性是**true**。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="aaa6d-167"><xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A>属性可以用于获取的当前值**unescapeRequestUrl**从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa6d-168">示例</span><span class="sxs-lookup"><span data-stu-id="aaa6d-168">Example</span></span>  
 <span data-ttu-id="aaa6d-169">下面的示例演示如何配置<xref:System.Net.HttpListener>类在接收的请求而不是从转换后的 URI 中使用的原始 URI 时`http.sys`作为输入到<xref:System.Net.HttpListenerRequest.Url%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aaa6d-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="aaa6d-170">元素信息</span><span class="sxs-lookup"><span data-stu-id="aaa6d-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="aaa6d-171">命名空间</span><span class="sxs-lookup"><span data-stu-id="aaa6d-171">Namespace</span></span>|<span data-ttu-id="aaa6d-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="aaa6d-172">System.Net</span></span>|  
|<span data-ttu-id="aaa6d-173">架构名称</span><span class="sxs-lookup"><span data-stu-id="aaa6d-173">Schema Name</span></span>||  
|<span data-ttu-id="aaa6d-174">验证文件</span><span class="sxs-lookup"><span data-stu-id="aaa6d-174">Validation File</span></span>||  
|<span data-ttu-id="aaa6d-175">可以为空</span><span class="sxs-lookup"><span data-stu-id="aaa6d-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="aaa6d-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa6d-176">See Also</span></span>  
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [<span data-ttu-id="aaa6d-177">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="aaa6d-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
