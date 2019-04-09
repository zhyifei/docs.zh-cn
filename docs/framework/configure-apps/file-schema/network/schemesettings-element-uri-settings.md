---
title: <schemeSettings> 元素 （Uri 设置）
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 8dc505d8a9de4e8939372af61b23652551c36530
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094225"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="9dbeb-102">\<schemeSettings > 元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="9dbeb-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="9dbeb-103">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="9dbeb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9dbeb-104">\<configuration></span></span>  
<span data-ttu-id="9dbeb-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="9dbeb-105">\<uri></span></span>  
<span data-ttu-id="9dbeb-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="9dbeb-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbeb-107">语法</span><span class="sxs-lookup"><span data-stu-id="9dbeb-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dbeb-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9dbeb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9dbeb-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dbeb-110">特性</span><span class="sxs-lookup"><span data-stu-id="9dbeb-110">Attributes</span></span>  
 <span data-ttu-id="9dbeb-111">None</span><span class="sxs-lookup"><span data-stu-id="9dbeb-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9dbeb-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9dbeb-112">Child Elements</span></span>  
  
|**<span data-ttu-id="9dbeb-113">元素</span><span class="sxs-lookup"><span data-stu-id="9dbeb-113">Element</span></span>**|**<span data-ttu-id="9dbeb-114">描述</span><span class="sxs-lookup"><span data-stu-id="9dbeb-114">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="9dbeb-115">添加</span><span class="sxs-lookup"><span data-stu-id="9dbeb-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9dbeb-116">添加方案设置的方案名称。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="9dbeb-117">清除</span><span class="sxs-lookup"><span data-stu-id="9dbeb-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9dbeb-118">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="9dbeb-119">remove</span><span class="sxs-lookup"><span data-stu-id="9dbeb-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="9dbeb-120">删除方案名称的方案设置。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9dbeb-121">父元素</span><span class="sxs-lookup"><span data-stu-id="9dbeb-121">Parent Elements</span></span>  
  
|**<span data-ttu-id="9dbeb-122">元素</span><span class="sxs-lookup"><span data-stu-id="9dbeb-122">Element</span></span>**|**<span data-ttu-id="9dbeb-123">描述</span><span class="sxs-lookup"><span data-stu-id="9dbeb-123">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="9dbeb-124">uri</span><span class="sxs-lookup"><span data-stu-id="9dbeb-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="9dbeb-125">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbeb-126">备注</span><span class="sxs-lookup"><span data-stu-id="9dbeb-126">Remarks</span></span>  
 <span data-ttu-id="9dbeb-127">默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码执行路径压缩前的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9dbeb-128">此操作实施为针对攻击，如以下一种安全机制：</span><span class="sxs-lookup"><span data-stu-id="9dbeb-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9dbeb-129">如果此 URI 获取传递给模块不处理百分号编码字符正确，可能会导致服务器正在执行的以下命令：</span><span class="sxs-lookup"><span data-stu-id="9dbeb-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9dbeb-130">出于此原因，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义的路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9dbeb-131">将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数结果中的以下 URI:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9dbeb-132">SchemeSettings 配置选项用于特定方案的未取消转义百分比编码的路径分隔符，可以修改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9dbeb-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="9dbeb-133">Configuration Files</span></span>  
 <span data-ttu-id="9dbeb-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dbeb-135">示例</span><span class="sxs-lookup"><span data-stu-id="9dbeb-135">Example</span></span>  
 <span data-ttu-id="9dbeb-136">下面的示例演示使用的配置<xref:System.Uri>类，以支持非转义的 http 方案的百分比编码路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="9dbeb-137">元素信息</span><span class="sxs-lookup"><span data-stu-id="9dbeb-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="9dbeb-138">命名空间</span><span class="sxs-lookup"><span data-stu-id="9dbeb-138">Namespace</span></span>|<span data-ttu-id="9dbeb-139">系统</span><span class="sxs-lookup"><span data-stu-id="9dbeb-139">System</span></span>|  
|<span data-ttu-id="9dbeb-140">架构名称</span><span class="sxs-lookup"><span data-stu-id="9dbeb-140">Schema Name</span></span>||  
|<span data-ttu-id="9dbeb-141">验证文件</span><span class="sxs-lookup"><span data-stu-id="9dbeb-141">Validation File</span></span>||  
|<span data-ttu-id="9dbeb-142">可以为空</span><span class="sxs-lookup"><span data-stu-id="9dbeb-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="9dbeb-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbeb-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9dbeb-144">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="9dbeb-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
