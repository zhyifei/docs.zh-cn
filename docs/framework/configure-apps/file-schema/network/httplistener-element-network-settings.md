---
title: <httpListener> 元素（网络设置）
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3f75096681ab07dd6d4788fbded5ca5c4a024aef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698196"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="5163e-102">\<httpListener > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="5163e-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="5163e-103">自定义 <xref:System.Net.HttpListener> 类使用的参数。</span><span class="sxs-lookup"><span data-stu-id="5163e-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
[<span data-ttu-id="5163e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5163e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5163e-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5163e-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="5163e-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5163e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="5163e-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpListener >**</span><span class="sxs-lookup"><span data-stu-id="5163e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5163e-108">语法</span><span class="sxs-lookup"><span data-stu-id="5163e-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="5163e-109">type</span><span class="sxs-lookup"><span data-stu-id="5163e-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5163e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5163e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5163e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5163e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5163e-112">特性</span><span class="sxs-lookup"><span data-stu-id="5163e-112">Attributes</span></span>  
  
|<span data-ttu-id="5163e-113">特性</span><span class="sxs-lookup"><span data-stu-id="5163e-113">Attribute</span></span>|<span data-ttu-id="5163e-114">描述</span><span class="sxs-lookup"><span data-stu-id="5163e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5163e-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="5163e-115">unescapeRequestUrl</span></span>|<span data-ttu-id="5163e-116">一个布尔值，该值指示 <xref:System.Net.HttpListener> 实例是否使用原始未转义 URI 而不是已转换的 URI。</span><span class="sxs-lookup"><span data-stu-id="5163e-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5163e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="5163e-117">Child Elements</span></span>  
 <span data-ttu-id="5163e-118">无。</span><span class="sxs-lookup"><span data-stu-id="5163e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5163e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5163e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5163e-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="5163e-120">**Element**</span></span>|<span data-ttu-id="5163e-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="5163e-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5163e-122">设置</span><span class="sxs-lookup"><span data-stu-id="5163e-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="5163e-123">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="5163e-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5163e-124">备注</span><span class="sxs-lookup"><span data-stu-id="5163e-124">Remarks</span></span>  
 <span data-ttu-id="5163e-125">**UnescapeRequestUrl**特性指示 <xref:System.Net.HttpListener> 是否使用原始非转义 uri 而不是转换的 uri （其中任何百分比编码值都已转换）并执行其他规范化步骤。</span><span class="sxs-lookup"><span data-stu-id="5163e-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="5163e-126">当 <xref:System.Net.HttpListener> 实例通过 @no__t 服务收到请求时，它会创建 `http.sys` 提供的 URI 字符串的实例，并将其公开为 @no__t 属性。</span><span class="sxs-lookup"><span data-stu-id="5163e-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="5163e-127">@No__t-0 服务公开两个请求 URI 字符串：</span><span class="sxs-lookup"><span data-stu-id="5163e-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="5163e-128">原始 URI</span><span class="sxs-lookup"><span data-stu-id="5163e-128">Raw URI</span></span>  
  
- <span data-ttu-id="5163e-129">转换的 URI</span><span class="sxs-lookup"><span data-stu-id="5163e-129">Converted URI</span></span>  
  
 <span data-ttu-id="5163e-130">原始 URI 是 HTTP 请求的请求行中提供的 <xref:System.Uri?displayProperty=nameWithType>：</span><span class="sxs-lookup"><span data-stu-id="5163e-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="5163e-131">为上面提到的请求 @no__t 提供的原始 URI 为 "/path/"。</span><span class="sxs-lookup"><span data-stu-id="5163e-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="5163e-132">这表示 HTTP 谓词后的字符串，因为它是通过网络发送的。</span><span class="sxs-lookup"><span data-stu-id="5163e-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="5163e-133">@No__t-0 服务通过使用 HTTP 请求行中提供的 URI 和主机标头确定请求应转发到的源服务器，从请求中提供的信息创建转换的 URI。</span><span class="sxs-lookup"><span data-stu-id="5163e-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="5163e-134">这是通过将请求中的信息与一组已注册的 URI 前缀进行比较来完成的。</span><span class="sxs-lookup"><span data-stu-id="5163e-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="5163e-135">HTTP 服务器 SDK 文档将此转换的 URI 称为 HTTP_COOKED_URL 结构。</span><span class="sxs-lookup"><span data-stu-id="5163e-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="5163e-136">为了能够将请求与已注册的 URI 前缀进行比较，需要对请求进行一些规范化。</span><span class="sxs-lookup"><span data-stu-id="5163e-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="5163e-137">对于上面的示例，转换后的 URI 如下所示：</span><span class="sxs-lookup"><span data-stu-id="5163e-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="5163e-138">@No__t-0 服务将 @no__t 属性值与请求行中的字符串结合起来，以创建转换的 URI。</span><span class="sxs-lookup"><span data-stu-id="5163e-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="5163e-139">此外，`http.sys` 和 @no__t 类还会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5163e-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="5163e-140">取消转义所有百分比编码值。</span><span class="sxs-lookup"><span data-stu-id="5163e-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="5163e-141">将百分号编码的非 ASCII 字符转换为 UTF-16 字符表示形式。</span><span class="sxs-lookup"><span data-stu-id="5163e-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="5163e-142">请注意，支持 UTF-8 和 ANSI/DBCS 字符以及 Unicode 字符（使用% uXXXX 格式的 Unicode 编码）。</span><span class="sxs-lookup"><span data-stu-id="5163e-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="5163e-143">执行其他规范化步骤，如路径压缩。</span><span class="sxs-lookup"><span data-stu-id="5163e-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="5163e-144">由于请求不包含任何有关用于百分比编码值的编码的信息，因此只需分析百分比编码的值就不能确定正确的编码。</span><span class="sxs-lookup"><span data-stu-id="5163e-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="5163e-145">因此 `http.sys` 提供了两个注册表项用于修改进程：</span><span class="sxs-lookup"><span data-stu-id="5163e-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="5163e-146">注册表项</span><span class="sxs-lookup"><span data-stu-id="5163e-146">Registry Key</span></span>|<span data-ttu-id="5163e-147">Default Value</span><span class="sxs-lookup"><span data-stu-id="5163e-147">Default Value</span></span>|<span data-ttu-id="5163e-148">描述</span><span class="sxs-lookup"><span data-stu-id="5163e-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="5163e-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="5163e-149">EnableNonUTF8</span></span>|<span data-ttu-id="5163e-150">1</span><span class="sxs-lookup"><span data-stu-id="5163e-150">1</span></span>|<span data-ttu-id="5163e-151">如果为零，则 `http.sys` 只接受 UTF-8 编码的 Url。</span><span class="sxs-lookup"><span data-stu-id="5163e-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="5163e-152">如果非零，则 @no__t 还在请求中接受 ANSI 编码或 DBCS 编码的 Url。</span><span class="sxs-lookup"><span data-stu-id="5163e-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="5163e-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="5163e-153">FavorUTF8</span></span>|<span data-ttu-id="5163e-154">1</span><span class="sxs-lookup"><span data-stu-id="5163e-154">1</span></span>|<span data-ttu-id="5163e-155">如果非零，则 @no__t 始终首先尝试将 URL 解码为 UTF-8;如果该转换失败并且 EnableNonUTF8 为非零，则 Http.sys 会尝试将其解码为 ANSI 或 DBCS。</span><span class="sxs-lookup"><span data-stu-id="5163e-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="5163e-156">如果为零（并且 EnableNonUTF8 为非零），`http.sys` 会尝试将其解码为 ANSI 或 DBCS;如果未成功，则它将尝试 UTF-8 转换。</span><span class="sxs-lookup"><span data-stu-id="5163e-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="5163e-157">当 <xref:System.Net.HttpListener> 收到请求时，它将使用从 `http.sys` 转换为 <xref:System.Net.HttpListenerRequest.Url%2A> 属性的输入的 URI。</span><span class="sxs-lookup"><span data-stu-id="5163e-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="5163e-158">除了 Uri 中的字符和数字以外，还需要支持字符。</span><span class="sxs-lookup"><span data-stu-id="5163e-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="5163e-159">例如，以下 URI 用于检索客户编号 "1/3812" 的客户信息：</span><span class="sxs-lookup"><span data-stu-id="5163e-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="5163e-160">请注意 Uri （% 2F）中的百分号编码的斜杠。</span><span class="sxs-lookup"><span data-stu-id="5163e-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="5163e-161">这是必需的，因为在这种情况下，斜杠字符表示数据而不是路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="5163e-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="5163e-162">将字符串传递到 Uri 构造函数将导致以下 URI：</span><span class="sxs-lookup"><span data-stu-id="5163e-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="5163e-163">将路径拆分为其段将导致以下元素：</span><span class="sxs-lookup"><span data-stu-id="5163e-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="5163e-164">这不是请求发送方的意图。</span><span class="sxs-lookup"><span data-stu-id="5163e-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="5163e-165">如果将**unescapeRequestUrl**特性设置为**false**，则当 <xref:System.Net.HttpListener> 接收请求时，它将使用原始 URI，而不是 `http.sys` 中的已转换 uri 作为 @no__t 属性的输入。</span><span class="sxs-lookup"><span data-stu-id="5163e-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="5163e-166">**UnescapeRequestUrl**属性的默认值为**true**。</span><span class="sxs-lookup"><span data-stu-id="5163e-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="5163e-167">@No__t-0 属性可用于从适用的配置文件中获取**unescapeRequestUrl**属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="5163e-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5163e-168">示例</span><span class="sxs-lookup"><span data-stu-id="5163e-168">Example</span></span>  
 <span data-ttu-id="5163e-169">下面的示例演示如何在 <xref:System.Net.HttpListener> 类接收到使用原始 URI 的请求而不是 `http.sys` 中转换的 URI 作为 <xref:System.Net.HttpListenerRequest.Url%2A> 属性的输入时，对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="5163e-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="5163e-170">元素信息</span><span class="sxs-lookup"><span data-stu-id="5163e-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="5163e-171">命名空间</span><span class="sxs-lookup"><span data-stu-id="5163e-171">Namespace</span></span>|<span data-ttu-id="5163e-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="5163e-172">System.Net</span></span>|  
|<span data-ttu-id="5163e-173">架构名称</span><span class="sxs-lookup"><span data-stu-id="5163e-173">Schema Name</span></span>||  
|<span data-ttu-id="5163e-174">验证文件</span><span class="sxs-lookup"><span data-stu-id="5163e-174">Validation File</span></span>||  
|<span data-ttu-id="5163e-175">可以为空</span><span class="sxs-lookup"><span data-stu-id="5163e-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="5163e-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="5163e-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="5163e-177">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="5163e-177">Network Settings Schema</span></span>](index.md)
