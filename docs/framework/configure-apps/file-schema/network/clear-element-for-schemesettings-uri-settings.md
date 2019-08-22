---
title: schemeSettings 的 <clear> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664180"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="7e3a6-102">\<清除 schemeSettings 的 > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="7e3a6-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="7e3a6-103">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="7e3a6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7e3a6-104">\<configuration></span></span>  
<span data-ttu-id="7e3a6-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="7e3a6-105">\<uri></span></span>  
<span data-ttu-id="7e3a6-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="7e3a6-106">\<schemeSettings></span></span>  
<span data-ttu-id="7e3a6-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="7e3a6-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e3a6-108">语法</span><span class="sxs-lookup"><span data-stu-id="7e3a6-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e3a6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e3a6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e3a6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e3a6-111">特性</span><span class="sxs-lookup"><span data-stu-id="7e3a6-111">Attributes</span></span>  
 <span data-ttu-id="7e3a6-112">无。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e3a6-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7e3a6-113">Child Elements</span></span>  
 <span data-ttu-id="7e3a6-114">无。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e3a6-115">父元素</span><span class="sxs-lookup"><span data-stu-id="7e3a6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7e3a6-116">元素</span><span class="sxs-lookup"><span data-stu-id="7e3a6-116">Element</span></span>|<span data-ttu-id="7e3a6-117">描述</span><span class="sxs-lookup"><span data-stu-id="7e3a6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e3a6-118">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="7e3a6-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="7e3a6-119">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e3a6-120">备注</span><span class="sxs-lookup"><span data-stu-id="7e3a6-120">Remarks</span></span>  
 <span data-ttu-id="7e3a6-121">默认情况下, <xref:System.Uri?displayProperty=nameWithType>在执行路径压缩之前, 类会取消转义编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="7e3a6-122">这是作为一种安全机制实现的, 针对以下攻击:</span><span class="sxs-lookup"><span data-stu-id="7e3a6-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7e3a6-123">如果将此 URI 向下传递到模块, 而不是正确处理百分号编码字符, 则可能会导致服务器执行以下命令:</span><span class="sxs-lookup"><span data-stu-id="7e3a6-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="7e3a6-124">出于此原因, <xref:System.Uri?displayProperty=nameWithType>类首先取消转义路径分隔符, 然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="7e3a6-125">将上述恶意 URL 传递到<xref:System.Uri?displayProperty=nameWithType>类构造函数的结果将生成以下 URI:</span><span class="sxs-lookup"><span data-stu-id="7e3a6-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7e3a6-126">使用特定方案的 schemeSettings 配置选项, 可以将此默认行为修改为不取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7e3a6-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="7e3a6-127">Configuration Files</span></span>  
 <span data-ttu-id="7e3a6-128">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e3a6-129">示例</span><span class="sxs-lookup"><span data-stu-id="7e3a6-129">Example</span></span>  
 <span data-ttu-id="7e3a6-130">下面的示例演示了<xref:System.Uri>类使用的配置, 该配置将清除所有方案设置, 并添加了对不转义 http 方案的百分号编码路径分隔符的支持。</span><span class="sxs-lookup"><span data-stu-id="7e3a6-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e3a6-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e3a6-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="7e3a6-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="7e3a6-132">Network Settings Schema</span></span>](index.md)
