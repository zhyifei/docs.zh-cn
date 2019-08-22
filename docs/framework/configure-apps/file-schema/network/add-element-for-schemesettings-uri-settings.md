---
title: schemeSettings 的 <add> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 027c7aaffea7950739f532309255d77afa031ada
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659545"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="9603f-102">\<为 schemeSettings 添加 > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="9603f-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="9603f-103">为方案名称添加方案设置。</span><span class="sxs-lookup"><span data-stu-id="9603f-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="9603f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9603f-104">\<configuration></span></span>  
<span data-ttu-id="9603f-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="9603f-105">\<uri></span></span>  
<span data-ttu-id="9603f-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="9603f-106">\<schemeSettings></span></span>  
<span data-ttu-id="9603f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9603f-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9603f-108">语法</span><span class="sxs-lookup"><span data-stu-id="9603f-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9603f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9603f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9603f-110">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9603f-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9603f-111">特性</span><span class="sxs-lookup"><span data-stu-id="9603f-111">Attributes</span></span>  
  
|<span data-ttu-id="9603f-112">特性</span><span class="sxs-lookup"><span data-stu-id="9603f-112">Attribute</span></span>|<span data-ttu-id="9603f-113">描述</span><span class="sxs-lookup"><span data-stu-id="9603f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9603f-114">NAME</span><span class="sxs-lookup"><span data-stu-id="9603f-114">name</span></span>|<span data-ttu-id="9603f-115">应用此设置的方案名称。</span><span class="sxs-lookup"><span data-stu-id="9603f-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="9603f-116">唯一受支持的值为 name = "http" 和 name = "https"。</span><span class="sxs-lookup"><span data-stu-id="9603f-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="9603f-117">{Attribute name}Attribute</span><span class="sxs-lookup"><span data-stu-id="9603f-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="9603f-118">值</span><span class="sxs-lookup"><span data-stu-id="9603f-118">Value</span></span>|<span data-ttu-id="9603f-119">描述</span><span class="sxs-lookup"><span data-stu-id="9603f-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9603f-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="9603f-120">genericUriParserOptions</span></span>|<span data-ttu-id="9603f-121">此方案的分析器选项。</span><span class="sxs-lookup"><span data-stu-id="9603f-121">The parser options for this scheme.</span></span> <span data-ttu-id="9603f-122">唯一受支持的值为 genericUriParserOptions = "DontUnescapePathDotsAndSlashes"。</span><span class="sxs-lookup"><span data-stu-id="9603f-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9603f-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9603f-123">Child Elements</span></span>  
 <span data-ttu-id="9603f-124">无</span><span class="sxs-lookup"><span data-stu-id="9603f-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9603f-125">父元素</span><span class="sxs-lookup"><span data-stu-id="9603f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9603f-126">元素</span><span class="sxs-lookup"><span data-stu-id="9603f-126">Element</span></span>|<span data-ttu-id="9603f-127">描述</span><span class="sxs-lookup"><span data-stu-id="9603f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9603f-128">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="9603f-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="9603f-129">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="9603f-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9603f-130">备注</span><span class="sxs-lookup"><span data-stu-id="9603f-130">Remarks</span></span>  
 <span data-ttu-id="9603f-131">默认情况下, <xref:System.Uri?displayProperty=nameWithType>在执行路径压缩之前, 类会取消转义编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="9603f-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9603f-132">这是作为一种安全机制实现的, 针对以下攻击:</span><span class="sxs-lookup"><span data-stu-id="9603f-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9603f-133">如果将此 URI 向下传递到模块, 而不是正确处理百分号编码字符, 则可能会导致服务器执行以下命令:</span><span class="sxs-lookup"><span data-stu-id="9603f-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9603f-134">出于此原因, <xref:System.Uri?displayProperty=nameWithType>类首先取消转义路径分隔符, 然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="9603f-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9603f-135">将上述恶意 URL 传递到<xref:System.Uri?displayProperty=nameWithType>类构造函数的结果将生成以下 URI:</span><span class="sxs-lookup"><span data-stu-id="9603f-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9603f-136">使用特定方案的 schemeSettings 配置选项, 可以将此默认行为修改为不取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="9603f-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9603f-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="9603f-137">Configuration Files</span></span>  
 <span data-ttu-id="9603f-138">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="9603f-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9603f-139">示例</span><span class="sxs-lookup"><span data-stu-id="9603f-139">Example</span></span>  
 <span data-ttu-id="9603f-140">下面的示例演示<xref:System.Uri>类使用的配置, 以支持不转义 http 方案的百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="9603f-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9603f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="9603f-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9603f-142">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="9603f-142">Network Settings Schema</span></span>](index.md)
