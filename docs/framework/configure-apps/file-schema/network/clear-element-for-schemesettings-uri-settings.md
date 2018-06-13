---
title: '&lt;清除&gt;schemeSettings （Uri 设置） 的元素'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 32c7a9e07b48536584f7ca5588226fb4479bacb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742518"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="b0d90-102">&lt;清除&gt;schemeSettings （Uri 设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="b0d90-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="b0d90-103">清除所有现有的方案设置。</span><span class="sxs-lookup"><span data-stu-id="b0d90-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="b0d90-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0d90-104">\<configuration></span></span>  
<span data-ttu-id="b0d90-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="b0d90-105">\<uri></span></span>  
<span data-ttu-id="b0d90-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="b0d90-106">\<schemeSettings></span></span>  
<span data-ttu-id="b0d90-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="b0d90-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d90-108">语法</span><span class="sxs-lookup"><span data-stu-id="b0d90-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0d90-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b0d90-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b0d90-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b0d90-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0d90-111">特性</span><span class="sxs-lookup"><span data-stu-id="b0d90-111">Attributes</span></span>  
 <span data-ttu-id="b0d90-112">无。</span><span class="sxs-lookup"><span data-stu-id="b0d90-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0d90-113">子元素</span><span class="sxs-lookup"><span data-stu-id="b0d90-113">Child Elements</span></span>  
 <span data-ttu-id="b0d90-114">无。</span><span class="sxs-lookup"><span data-stu-id="b0d90-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0d90-115">父元素</span><span class="sxs-lookup"><span data-stu-id="b0d90-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b0d90-116">元素</span><span class="sxs-lookup"><span data-stu-id="b0d90-116">Element</span></span>|<span data-ttu-id="b0d90-117">描述</span><span class="sxs-lookup"><span data-stu-id="b0d90-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0d90-118">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="b0d90-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b0d90-119">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="b0d90-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0d90-120">备注</span><span class="sxs-lookup"><span data-stu-id="b0d90-120">Remarks</span></span>  
 <span data-ttu-id="b0d90-121">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码在执行路径压缩前的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="b0d90-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b0d90-122">这实现为一种安全机制免受攻击如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0d90-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b0d90-123">如果此 URI 获取传递给模块不处理百分号编码字符正确，则可能导致服务器正在执行的以下命令：</span><span class="sxs-lookup"><span data-stu-id="b0d90-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b0d90-124">为此，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义路径分隔符，然后将应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="b0d90-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b0d90-125">将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数会产生以下 URI:</span><span class="sxs-lookup"><span data-stu-id="b0d90-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b0d90-126">SchemeSettings 配置选项用于特定方案的不取消转义百分比编码的路径分隔符，可以修改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="b0d90-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b0d90-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="b0d90-127">Configuration Files</span></span>  
 <span data-ttu-id="b0d90-128">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="b0d90-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d90-129">示例</span><span class="sxs-lookup"><span data-stu-id="b0d90-129">Example</span></span>  
 <span data-ttu-id="b0d90-130">下面的示例演示使用的配置<xref:System.Uri>清除所有方案设置，然后添加对非转义 http 方案的百分比编码路径分隔符的支持的类。</span><span class="sxs-lookup"><span data-stu-id="b0d90-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0d90-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0d90-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="b0d90-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b0d90-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
