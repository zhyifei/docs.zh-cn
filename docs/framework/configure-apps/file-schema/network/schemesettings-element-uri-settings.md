---
title: <schemeSettings> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154642"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="05869-102">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="05869-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="05869-103">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="05869-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="05869-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="05869-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="05869-105">&nbsp;&nbsp;[**\<乌里>**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="05869-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="05869-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<方案设置>**</span><span class="sxs-lookup"><span data-stu-id="05869-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05869-107">语法</span><span class="sxs-lookup"><span data-stu-id="05869-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05869-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="05869-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05869-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="05869-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05869-110">属性</span><span class="sxs-lookup"><span data-stu-id="05869-110">Attributes</span></span>  
 <span data-ttu-id="05869-111">无</span><span class="sxs-lookup"><span data-stu-id="05869-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05869-112">子元素</span><span class="sxs-lookup"><span data-stu-id="05869-112">Child Elements</span></span>  
  
|<span data-ttu-id="05869-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="05869-113">**Element**</span></span>|<span data-ttu-id="05869-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="05869-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05869-115">添加</span><span class="sxs-lookup"><span data-stu-id="05869-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05869-116">添加方案名称的方案设置。</span><span class="sxs-lookup"><span data-stu-id="05869-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="05869-117">清楚</span><span class="sxs-lookup"><span data-stu-id="05869-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05869-118">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="05869-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="05869-119">删除</span><span class="sxs-lookup"><span data-stu-id="05869-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05869-120">删除方案名称的方案设置。</span><span class="sxs-lookup"><span data-stu-id="05869-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05869-121">父元素</span><span class="sxs-lookup"><span data-stu-id="05869-121">Parent Elements</span></span>  
  
|<span data-ttu-id="05869-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="05869-122">**Element**</span></span>|<span data-ttu-id="05869-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="05869-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05869-124">Uri</span><span class="sxs-lookup"><span data-stu-id="05869-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="05869-125">包含指定 .NET 框架如何处理使用统一资源标识符 （URI） 表示的 Web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="05869-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05869-126">备注</span><span class="sxs-lookup"><span data-stu-id="05869-126">Remarks</span></span>  
 <span data-ttu-id="05869-127">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分比编码的路径分隔符，然后再执行路径压缩。</span><span class="sxs-lookup"><span data-stu-id="05869-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="05869-128">这是作为针对以下攻击的安全机制实现的：</span><span class="sxs-lookup"><span data-stu-id="05869-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="05869-129">如果此 URI 传递给未正确处理编码百分比的模块，则可能导致服务器执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="05869-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="05869-130">因此，<xref:System.Uri?displayProperty=nameWithType>类首先取消转义路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="05869-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="05869-131">将上述恶意 URL 传递给<xref:System.Uri?displayProperty=nameWithType>类构造函数的结果会导致以下 URI：</span><span class="sxs-lookup"><span data-stu-id="05869-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="05869-132">可以使用方案设置配置选项修改此默认行为，以不取消转义百分比编码路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="05869-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="05869-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="05869-133">Configuration Files</span></span>  
 <span data-ttu-id="05869-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="05869-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05869-135">示例</span><span class="sxs-lookup"><span data-stu-id="05869-135">Example</span></span>  
 <span data-ttu-id="05869-136">下面的示例显示了<xref:System.Uri>类用于支持不为 http 方案提供百分比编码的路径分隔符的配置。</span><span class="sxs-lookup"><span data-stu-id="05869-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="05869-137">元素信息</span><span class="sxs-lookup"><span data-stu-id="05869-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="05869-138">命名空间</span><span class="sxs-lookup"><span data-stu-id="05869-138">Namespace</span></span>|<span data-ttu-id="05869-139">系统</span><span class="sxs-lookup"><span data-stu-id="05869-139">System</span></span>|  
|<span data-ttu-id="05869-140">架构名称</span><span class="sxs-lookup"><span data-stu-id="05869-140">Schema Name</span></span>||  
|<span data-ttu-id="05869-141">验证文件</span><span class="sxs-lookup"><span data-stu-id="05869-141">Validation File</span></span>||  
|<span data-ttu-id="05869-142">可以为空</span><span class="sxs-lookup"><span data-stu-id="05869-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="05869-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05869-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="05869-144">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="05869-144">Network Settings Schema</span></span>](index.md)
