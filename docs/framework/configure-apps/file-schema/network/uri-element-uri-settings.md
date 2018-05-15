---
title: '&lt;Uri&gt;元素 （Uri 设置）'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 05b2fb4255643f657f37012ec51a1b29ed68095d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="79b02-102">&lt;Uri&gt;元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="79b02-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="79b02-103">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="79b02-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="79b02-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="79b02-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="79b02-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="79b02-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="79b02-106">\<uri ></span><span class="sxs-lookup"><span data-stu-id="79b02-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="79b02-107">语法</span><span class="sxs-lookup"><span data-stu-id="79b02-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79b02-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79b02-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79b02-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79b02-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79b02-110">特性</span><span class="sxs-lookup"><span data-stu-id="79b02-110">Attributes</span></span>  
 <span data-ttu-id="79b02-111">无。</span><span class="sxs-lookup"><span data-stu-id="79b02-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79b02-112">子元素</span><span class="sxs-lookup"><span data-stu-id="79b02-112">Child Elements</span></span>  
  
|<span data-ttu-id="79b02-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="79b02-113">**Element**</span></span>|<span data-ttu-id="79b02-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="79b02-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="79b02-115">idn</span><span class="sxs-lookup"><span data-stu-id="79b02-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="79b02-116">指定是否对域名应用国际化域名 (IDN) 分析。</span><span class="sxs-lookup"><span data-stu-id="79b02-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="79b02-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="79b02-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="79b02-118">指定是否对应用国际资源标识符 (IRI) 分析<xref:System.Uri>以及是否应应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="79b02-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="79b02-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="79b02-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="79b02-120">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="79b02-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79b02-121">父元素</span><span class="sxs-lookup"><span data-stu-id="79b02-121">Parent Elements</span></span>  
  
|<span data-ttu-id="79b02-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="79b02-122">**Element**</span></span>|<span data-ttu-id="79b02-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="79b02-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="79b02-124">配置</span><span class="sxs-lookup"><span data-stu-id="79b02-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="79b02-125">包含所有命名空间的设置。</span><span class="sxs-lookup"><span data-stu-id="79b02-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79b02-126">备注</span><span class="sxs-lookup"><span data-stu-id="79b02-126">Remarks</span></span>  
 <span data-ttu-id="79b02-127">`uri`元素包含的成员的设置<xref:System.Uri>类中的类使用<xref:System.Net>命名空间。</span><span class="sxs-lookup"><span data-stu-id="79b02-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="79b02-128">设置配置对 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="79b02-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79b02-129">示例</span><span class="sxs-lookup"><span data-stu-id="79b02-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="79b02-130">描述</span><span class="sxs-lookup"><span data-stu-id="79b02-130">Description</span></span>  
 <span data-ttu-id="79b02-131">下面的示例演示使用的配置<xref:System.Uri>类，以支持 IRI 分析和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="79b02-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="79b02-132">该示例还会清除所有方案设置，然后添加了对未转义百分比编码路径分隔符，使用 http 方案的支持。</span><span class="sxs-lookup"><span data-stu-id="79b02-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="79b02-133">代码</span><span class="sxs-lookup"><span data-stu-id="79b02-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79b02-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="79b02-134">See Also</span></span>  
 [<span data-ttu-id="79b02-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="79b02-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
