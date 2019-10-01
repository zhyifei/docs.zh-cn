---
title: <schemeSettings> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697760"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="2b4cd-102">\<schemeSettings > 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="2b4cd-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="2b4cd-103">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="2b4cd-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2b4cd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2b4cd-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2b4cd-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="2b4cd-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<schemeSettings >**</span><span class="sxs-lookup"><span data-stu-id="2b4cd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4cd-107">语法</span><span class="sxs-lookup"><span data-stu-id="2b4cd-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b4cd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b4cd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2b4cd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b4cd-110">特性</span><span class="sxs-lookup"><span data-stu-id="2b4cd-110">Attributes</span></span>  
 <span data-ttu-id="2b4cd-111">None</span><span class="sxs-lookup"><span data-stu-id="2b4cd-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b4cd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b4cd-112">Child Elements</span></span>  
  
|<span data-ttu-id="2b4cd-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b4cd-113">**Element**</span></span>|<span data-ttu-id="2b4cd-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b4cd-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b4cd-115">add</span><span class="sxs-lookup"><span data-stu-id="2b4cd-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="2b4cd-116">为方案名称添加方案设置。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="2b4cd-117">clear</span><span class="sxs-lookup"><span data-stu-id="2b4cd-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="2b4cd-118">清除所有现有方案设置。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="2b4cd-119">remove</span><span class="sxs-lookup"><span data-stu-id="2b4cd-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="2b4cd-120">删除方案名称的方案设置。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b4cd-121">父元素</span><span class="sxs-lookup"><span data-stu-id="2b4cd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2b4cd-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b4cd-122">**Element**</span></span>|<span data-ttu-id="2b4cd-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b4cd-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b4cd-124">oma-uri</span><span class="sxs-lookup"><span data-stu-id="2b4cd-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="2b4cd-125">包含指定 .NET Framework 如何处理使用统一资源标识符（Uri）表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b4cd-126">备注</span><span class="sxs-lookup"><span data-stu-id="2b4cd-126">Remarks</span></span>  
 <span data-ttu-id="2b4cd-127">默认情况下，在执行路径压缩之前，@no__t 0 类会取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="2b4cd-128">这是作为一种安全机制实现的，针对以下攻击：</span><span class="sxs-lookup"><span data-stu-id="2b4cd-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2b4cd-129">如果将此 URI 向下传递到模块，而不是正确处理百分号编码字符，则可能会导致服务器执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2b4cd-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="2b4cd-130">出于此原因，@no__t 0 类首先取消转义路径分隔符，然后应用路径压缩。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="2b4cd-131">将上述恶意 URL 传递到 <xref:System.Uri?displayProperty=nameWithType> 类构造函数的结果将生成以下 URI：</span><span class="sxs-lookup"><span data-stu-id="2b4cd-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2b4cd-132">使用特定方案的 schemeSettings 配置选项，可以将此默认行为修改为不取消转义百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2b4cd-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="2b4cd-133">Configuration Files</span></span>  
 <span data-ttu-id="2b4cd-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b4cd-135">示例</span><span class="sxs-lookup"><span data-stu-id="2b4cd-135">Example</span></span>  
 <span data-ttu-id="2b4cd-136">下面的示例演示 <xref:System.Uri> 类使用的配置，以支持不转义 http 方案的百分号编码的路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="2b4cd-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="2b4cd-137">元素信息</span><span class="sxs-lookup"><span data-stu-id="2b4cd-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="2b4cd-138">命名空间</span><span class="sxs-lookup"><span data-stu-id="2b4cd-138">Namespace</span></span>|<span data-ttu-id="2b4cd-139">System</span><span class="sxs-lookup"><span data-stu-id="2b4cd-139">System</span></span>|  
|<span data-ttu-id="2b4cd-140">架构名称</span><span class="sxs-lookup"><span data-stu-id="2b4cd-140">Schema Name</span></span>||  
|<span data-ttu-id="2b4cd-141">验证文件</span><span class="sxs-lookup"><span data-stu-id="2b4cd-141">Validation File</span></span>||  
|<span data-ttu-id="2b4cd-142">可以为空</span><span class="sxs-lookup"><span data-stu-id="2b4cd-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="2b4cd-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b4cd-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="2b4cd-144">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="2b4cd-144">Network Settings Schema</span></span>](index.md)
