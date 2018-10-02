---
title: '&lt;清除&gt;schemeSettings （Uri 设置） 的'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f0daa689ba09fa39ffe0f38d769112f0f095592a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028035"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="3d9d0-102">&lt;清除&gt;schemeSettings （Uri 设置） 的</span><span class="sxs-lookup"><span data-stu-id="3d9d0-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="3d9d0-103">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="3d9d0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3d9d0-104">\<configuration></span></span>  
<span data-ttu-id="3d9d0-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="3d9d0-105">\<uri></span></span>  
<span data-ttu-id="3d9d0-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="3d9d0-106">\<schemeSettings></span></span>  
<span data-ttu-id="3d9d0-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="3d9d0-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9d0-108">语法</span><span class="sxs-lookup"><span data-stu-id="3d9d0-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d9d0-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3d9d0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3d9d0-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d9d0-111">特性</span><span class="sxs-lookup"><span data-stu-id="3d9d0-111">Attributes</span></span>  
 <span data-ttu-id="3d9d0-112">无。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d9d0-113">子元素</span><span class="sxs-lookup"><span data-stu-id="3d9d0-113">Child Elements</span></span>  
 <span data-ttu-id="3d9d0-114">无。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d9d0-115">父元素</span><span class="sxs-lookup"><span data-stu-id="3d9d0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3d9d0-116">元素</span><span class="sxs-lookup"><span data-stu-id="3d9d0-116">Element</span></span>|<span data-ttu-id="3d9d0-117">描述</span><span class="sxs-lookup"><span data-stu-id="3d9d0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d9d0-118">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="3d9d0-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="3d9d0-119">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d9d0-120">备注</span><span class="sxs-lookup"><span data-stu-id="3d9d0-120">Remarks</span></span>  
 <span data-ttu-id="3d9d0-121">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码执行路径压缩前的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3d9d0-122">此操作实施为针对攻击，如以下一种安全机制：</span><span class="sxs-lookup"><span data-stu-id="3d9d0-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3d9d0-123">如果此 URI 获取传递给模块不处理百分号编码字符正确，可能会导致服务器正在执行的以下命令：</span><span class="sxs-lookup"><span data-stu-id="3d9d0-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3d9d0-124">出于此原因，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义的路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3d9d0-125">将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数结果中的以下 URI:</span><span class="sxs-lookup"><span data-stu-id="3d9d0-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3d9d0-126">SchemeSettings 配置选项用于特定方案的未取消转义百分比编码的路径分隔符，可以修改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3d9d0-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="3d9d0-127">Configuration Files</span></span>  
 <span data-ttu-id="3d9d0-128">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d9d0-129">示例</span><span class="sxs-lookup"><span data-stu-id="3d9d0-129">Example</span></span>  
 <span data-ttu-id="3d9d0-130">下面的示例演示使用的配置<xref:System.Uri>清除所有方案设置，然后添加对未转义的 http 方案的百分比编码路径分隔符的支持的类。</span><span class="sxs-lookup"><span data-stu-id="3d9d0-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d9d0-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d9d0-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="3d9d0-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="3d9d0-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
