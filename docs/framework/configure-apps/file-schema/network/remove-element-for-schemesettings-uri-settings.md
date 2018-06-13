---
title: '&lt;删除&gt;schemeSettings （Uri 设置） 的元素'
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8e01f82a476286e27129e4b1a47fefc1ac77c2b5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744156"
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="59702-102">&lt;删除&gt;schemeSettings （Uri 设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="59702-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="59702-103">删除一个方案名称方案设置。</span><span class="sxs-lookup"><span data-stu-id="59702-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="59702-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="59702-104">\<configuration></span></span>  
<span data-ttu-id="59702-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="59702-105">\<uri></span></span>  
<span data-ttu-id="59702-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="59702-106">\<schemeSettings></span></span>  
<span data-ttu-id="59702-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="59702-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59702-108">语法</span><span class="sxs-lookup"><span data-stu-id="59702-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59702-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59702-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59702-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59702-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59702-111">特性</span><span class="sxs-lookup"><span data-stu-id="59702-111">Attributes</span></span>  
  
|<span data-ttu-id="59702-112">特性</span><span class="sxs-lookup"><span data-stu-id="59702-112">Attribute</span></span>|<span data-ttu-id="59702-113">描述</span><span class="sxs-lookup"><span data-stu-id="59702-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59702-114">name</span><span class="sxs-lookup"><span data-stu-id="59702-114">name</span></span>|<span data-ttu-id="59702-115">此设置适用于方案名称。</span><span class="sxs-lookup"><span data-stu-id="59702-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="59702-116">只有受支持的值名称 ="http"和名称 ="https"。</span><span class="sxs-lookup"><span data-stu-id="59702-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59702-117">子元素</span><span class="sxs-lookup"><span data-stu-id="59702-117">Child Elements</span></span>  
 <span data-ttu-id="59702-118">无。</span><span class="sxs-lookup"><span data-stu-id="59702-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59702-119">父元素</span><span class="sxs-lookup"><span data-stu-id="59702-119">Parent Elements</span></span>  
  
|<span data-ttu-id="59702-120">元素</span><span class="sxs-lookup"><span data-stu-id="59702-120">Element</span></span>|<span data-ttu-id="59702-121">描述</span><span class="sxs-lookup"><span data-stu-id="59702-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59702-122">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="59702-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="59702-123">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="59702-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59702-124">备注</span><span class="sxs-lookup"><span data-stu-id="59702-124">Remarks</span></span>  
 <span data-ttu-id="59702-125">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码在执行路径压缩前的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="59702-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="59702-126">这实现为一种安全机制免受攻击如下所示：</span><span class="sxs-lookup"><span data-stu-id="59702-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="59702-127">如果此 URI 获取传递给模块不处理百分号编码字符正确，则可能导致服务器正在执行的以下命令：</span><span class="sxs-lookup"><span data-stu-id="59702-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="59702-128">为此，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义路径分隔符，然后将应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="59702-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="59702-129">将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数会产生以下 URI:</span><span class="sxs-lookup"><span data-stu-id="59702-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="59702-130">SchemeSettings 配置选项用于特定方案的不取消转义百分比编码的路径分隔符，可以修改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="59702-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="59702-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="59702-131">Configuration Files</span></span>  
 <span data-ttu-id="59702-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="59702-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59702-133">示例</span><span class="sxs-lookup"><span data-stu-id="59702-133">Example</span></span>  
 <span data-ttu-id="59702-134">下面的示例演示使用的配置<xref:System.Uri>删除 http 方案所有方案设置的类。</span><span class="sxs-lookup"><span data-stu-id="59702-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59702-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="59702-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="59702-136">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="59702-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
