---
title: schemeSettings 的 <remove> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: faf254174527ea74638442a139841eb2365d1e5d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089151"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="922e0-102">\<删除 schemeSettings 的 > 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="922e0-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="922e0-103">删除方案名称的方案设置。</span><span class="sxs-lookup"><span data-stu-id="922e0-103">Removes a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="922e0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="922e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="922e0-105">&nbsp;&nbsp;[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="922e0-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="922e0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="922e0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="922e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="922e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="922e0-108">语法</span><span class="sxs-lookup"><span data-stu-id="922e0-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="922e0-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="922e0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="922e0-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="922e0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="922e0-111">特性</span><span class="sxs-lookup"><span data-stu-id="922e0-111">Attributes</span></span>  
  
|<span data-ttu-id="922e0-112">特性</span><span class="sxs-lookup"><span data-stu-id="922e0-112">Attribute</span></span>|<span data-ttu-id="922e0-113">描述</span><span class="sxs-lookup"><span data-stu-id="922e0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="922e0-114">NAME</span><span class="sxs-lookup"><span data-stu-id="922e0-114">name</span></span>|<span data-ttu-id="922e0-115">应用此设置的方案名称。</span><span class="sxs-lookup"><span data-stu-id="922e0-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="922e0-116">唯一受支持的值为 name = "http" 和 name = "https"。</span><span class="sxs-lookup"><span data-stu-id="922e0-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="922e0-117">子元素</span><span class="sxs-lookup"><span data-stu-id="922e0-117">Child Elements</span></span>  
 <span data-ttu-id="922e0-118">无。</span><span class="sxs-lookup"><span data-stu-id="922e0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="922e0-119">父元素</span><span class="sxs-lookup"><span data-stu-id="922e0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="922e0-120">元素</span><span class="sxs-lookup"><span data-stu-id="922e0-120">Element</span></span>|<span data-ttu-id="922e0-121">描述</span><span class="sxs-lookup"><span data-stu-id="922e0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="922e0-122">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="922e0-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="922e0-123">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="922e0-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="922e0-124">备注</span><span class="sxs-lookup"><span data-stu-id="922e0-124">Remarks</span></span>  
 <span data-ttu-id="922e0-125">默认情况下，在执行路径压缩之前，<xref:System.Uri?displayProperty=nameWithType> 类会取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="922e0-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="922e0-126">这是作为一种安全机制实现的，针对以下攻击：</span><span class="sxs-lookup"><span data-stu-id="922e0-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="922e0-127">如果将此 URI 向下传递到模块，而不是正确处理百分号编码字符，则可能会导致服务器执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="922e0-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="922e0-128">出于此原因，<xref:System.Uri?displayProperty=nameWithType> 类首先取消转义路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="922e0-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="922e0-129">将上述恶意 URL 传递到 <xref:System.Uri?displayProperty=nameWithType> 类构造函数的结果将生成以下 URI：</span><span class="sxs-lookup"><span data-stu-id="922e0-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="922e0-130">使用特定方案的 schemeSettings 配置选项，可以将此默认行为修改为不取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="922e0-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="922e0-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="922e0-131">Configuration Files</span></span>  
 <span data-ttu-id="922e0-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="922e0-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="922e0-133">示例</span><span class="sxs-lookup"><span data-stu-id="922e0-133">Example</span></span>  
 <span data-ttu-id="922e0-134">下面的示例演示 <xref:System.Uri> 类使用的配置，该配置将删除 http 方案的任何方案设置。</span><span class="sxs-lookup"><span data-stu-id="922e0-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="922e0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="922e0-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="922e0-136">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="922e0-136">Network Settings Schema</span></span>](index.md)
