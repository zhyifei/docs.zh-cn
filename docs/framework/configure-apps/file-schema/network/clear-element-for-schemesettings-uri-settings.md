---
title: schemeSettings 的 <clear> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: e954fef455d0279a945c33f2014913fea9d63064
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699443"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="140ba-102">用于 schemeSettings 的 0clear > 元素（Uri 设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="140ba-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="140ba-103">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="140ba-103">Clears all existing scheme settings.</span></span>  
  
[<span data-ttu-id="140ba-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="140ba-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="140ba-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="140ba-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="140ba-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="140ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="140ba-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="140ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140ba-108">语法</span><span class="sxs-lookup"><span data-stu-id="140ba-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="140ba-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="140ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="140ba-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="140ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="140ba-111">特性</span><span class="sxs-lookup"><span data-stu-id="140ba-111">Attributes</span></span>  
 <span data-ttu-id="140ba-112">无。</span><span class="sxs-lookup"><span data-stu-id="140ba-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="140ba-113">子元素</span><span class="sxs-lookup"><span data-stu-id="140ba-113">Child Elements</span></span>  
 <span data-ttu-id="140ba-114">无。</span><span class="sxs-lookup"><span data-stu-id="140ba-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="140ba-115">父元素</span><span class="sxs-lookup"><span data-stu-id="140ba-115">Parent Elements</span></span>  
  
|<span data-ttu-id="140ba-116">元素</span><span class="sxs-lookup"><span data-stu-id="140ba-116">Element</span></span>|<span data-ttu-id="140ba-117">描述</span><span class="sxs-lookup"><span data-stu-id="140ba-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="140ba-118">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="140ba-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="140ba-119">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="140ba-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="140ba-120">备注</span><span class="sxs-lookup"><span data-stu-id="140ba-120">Remarks</span></span>  
 <span data-ttu-id="140ba-121">默认情况下，在执行路径压缩之前，@no__t 0 类会取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="140ba-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="140ba-122">这是作为一种安全机制实现的，针对以下攻击：</span><span class="sxs-lookup"><span data-stu-id="140ba-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="140ba-123">如果将此 URI 向下传递到模块，而不是正确处理百分号编码字符，则可能会导致服务器执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="140ba-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="140ba-124">出于此原因，@no__t 0 类首先取消转义路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="140ba-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="140ba-125">将上述恶意 URL 传递到 <xref:System.Uri?displayProperty=nameWithType> 类构造函数的结果将生成以下 URI：</span><span class="sxs-lookup"><span data-stu-id="140ba-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="140ba-126">使用特定方案的 schemeSettings 配置选项，可以将此默认行为修改为不取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="140ba-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="140ba-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="140ba-127">Configuration Files</span></span>  
 <span data-ttu-id="140ba-128">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="140ba-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="140ba-129">示例</span><span class="sxs-lookup"><span data-stu-id="140ba-129">Example</span></span>  
 <span data-ttu-id="140ba-130">下面的示例演示了 <xref:System.Uri> 类使用的配置，该配置清除所有方案设置，并添加了对 http 方案的非转义百分比编码路径分隔符的支持。</span><span class="sxs-lookup"><span data-stu-id="140ba-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="140ba-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="140ba-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="140ba-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="140ba-132">Network Settings Schema</span></span>](index.md)
