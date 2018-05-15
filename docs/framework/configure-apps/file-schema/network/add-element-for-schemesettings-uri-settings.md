---
title: '&lt;添加&gt;schemeSettings （Uri 设置） 的元素'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bd8033b07b29066633e5217645f3ee06937179da
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="035b1-102">&lt;添加&gt;schemeSettings （Uri 设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="035b1-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="035b1-103">添加方案名称方案设置。</span><span class="sxs-lookup"><span data-stu-id="035b1-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="035b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="035b1-104">\<configuration></span></span>  
<span data-ttu-id="035b1-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="035b1-105">\<uri></span></span>  
<span data-ttu-id="035b1-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="035b1-106">\<schemeSettings></span></span>  
<span data-ttu-id="035b1-107">\<add></span><span class="sxs-lookup"><span data-stu-id="035b1-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="035b1-108">语法</span><span class="sxs-lookup"><span data-stu-id="035b1-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="035b1-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="035b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="035b1-110">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="035b1-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="035b1-111">特性</span><span class="sxs-lookup"><span data-stu-id="035b1-111">Attributes</span></span>  
  
|<span data-ttu-id="035b1-112">特性</span><span class="sxs-lookup"><span data-stu-id="035b1-112">Attribute</span></span>|<span data-ttu-id="035b1-113">描述</span><span class="sxs-lookup"><span data-stu-id="035b1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="035b1-114">name</span><span class="sxs-lookup"><span data-stu-id="035b1-114">name</span></span>|<span data-ttu-id="035b1-115">此设置适用于方案名称。</span><span class="sxs-lookup"><span data-stu-id="035b1-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="035b1-116">只有受支持的值名称 ="http"和名称 ="https"。</span><span class="sxs-lookup"><span data-stu-id="035b1-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="035b1-117">{属性名称}属性</span><span class="sxs-lookup"><span data-stu-id="035b1-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="035b1-118">值</span><span class="sxs-lookup"><span data-stu-id="035b1-118">Value</span></span>|<span data-ttu-id="035b1-119">描述</span><span class="sxs-lookup"><span data-stu-id="035b1-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="035b1-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="035b1-120">genericUriParserOptions</span></span>|<span data-ttu-id="035b1-121">有关此方案的分析器选项。</span><span class="sxs-lookup"><span data-stu-id="035b1-121">The parser options for this scheme.</span></span> <span data-ttu-id="035b1-122">仅支持的值是 genericUriParserOptions ="DontUnescapePathDotsAndSlashes"。</span><span class="sxs-lookup"><span data-stu-id="035b1-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="035b1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="035b1-123">Child Elements</span></span>  
 <span data-ttu-id="035b1-124">无</span><span class="sxs-lookup"><span data-stu-id="035b1-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="035b1-125">父元素</span><span class="sxs-lookup"><span data-stu-id="035b1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="035b1-126">元素</span><span class="sxs-lookup"><span data-stu-id="035b1-126">Element</span></span>|<span data-ttu-id="035b1-127">描述</span><span class="sxs-lookup"><span data-stu-id="035b1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="035b1-128">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="035b1-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="035b1-129">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="035b1-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="035b1-130">备注</span><span class="sxs-lookup"><span data-stu-id="035b1-130">Remarks</span></span>  
 <span data-ttu-id="035b1-131">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码在执行路径压缩前的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="035b1-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="035b1-132">这实现为一种安全机制免受攻击如下所示：</span><span class="sxs-lookup"><span data-stu-id="035b1-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="035b1-133">如果此 URI 获取传递给模块不处理百分号编码字符正确，则可能导致服务器正在执行的以下命令：</span><span class="sxs-lookup"><span data-stu-id="035b1-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="035b1-134">为此，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义路径分隔符，然后将应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="035b1-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="035b1-135">将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数会产生以下 URI:</span><span class="sxs-lookup"><span data-stu-id="035b1-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="035b1-136">SchemeSettings 配置选项用于特定方案的不取消转义百分比编码的路径分隔符，可以修改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="035b1-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="035b1-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="035b1-137">Configuration Files</span></span>  
 <span data-ttu-id="035b1-138">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="035b1-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="035b1-139">示例</span><span class="sxs-lookup"><span data-stu-id="035b1-139">Example</span></span>  
 <span data-ttu-id="035b1-140">下面的示例演示使用的配置<xref:System.Uri>类，以支持非转义 http 方案的百分比编码路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="035b1-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="035b1-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="035b1-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="035b1-142">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="035b1-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
