---
title: "&lt;Uri&gt;元素 （Uri 设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44ef28ca2188973ccd353f4e8615c7c95f5674a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="6a79b-102">&lt;Uri&gt;元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="6a79b-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="6a79b-103">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="6a79b-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="6a79b-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="6a79b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="6a79b-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="6a79b-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="6a79b-106">\<uri ></span><span class="sxs-lookup"><span data-stu-id="6a79b-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="6a79b-107">语法</span><span class="sxs-lookup"><span data-stu-id="6a79b-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a79b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6a79b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a79b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6a79b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a79b-110">特性</span><span class="sxs-lookup"><span data-stu-id="6a79b-110">Attributes</span></span>  
 <span data-ttu-id="6a79b-111">无。</span><span class="sxs-lookup"><span data-stu-id="6a79b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6a79b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6a79b-112">Child Elements</span></span>  
  
|<span data-ttu-id="6a79b-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="6a79b-113">**Element**</span></span>|<span data-ttu-id="6a79b-114">**描述**</span><span class="sxs-lookup"><span data-stu-id="6a79b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6a79b-115">idn</span><span class="sxs-lookup"><span data-stu-id="6a79b-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="6a79b-116">指定是否对域名应用国际化域名 (IDN) 分析。</span><span class="sxs-lookup"><span data-stu-id="6a79b-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="6a79b-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="6a79b-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="6a79b-118">指定是否对应用国际资源标识符 (IRI) 分析<xref:System.Uri>以及是否应应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="6a79b-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="6a79b-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="6a79b-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="6a79b-120">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="6a79b-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a79b-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6a79b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6a79b-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="6a79b-122">**Element**</span></span>|<span data-ttu-id="6a79b-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="6a79b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6a79b-124">配置</span><span class="sxs-lookup"><span data-stu-id="6a79b-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6a79b-125">包含所有命名空间的设置。</span><span class="sxs-lookup"><span data-stu-id="6a79b-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a79b-126">备注</span><span class="sxs-lookup"><span data-stu-id="6a79b-126">Remarks</span></span>  
 <span data-ttu-id="6a79b-127">`uri`元素包含的成员的设置<xref:System.Uri>类中的类使用<xref:System.Net>命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a79b-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="6a79b-128">设置配置对 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="6a79b-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a79b-129">示例</span><span class="sxs-lookup"><span data-stu-id="6a79b-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6a79b-130">描述</span><span class="sxs-lookup"><span data-stu-id="6a79b-130">Description</span></span>  
 <span data-ttu-id="6a79b-131">下面的示例演示使用的配置<xref:System.Uri>类，以支持 IRI 分析和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="6a79b-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="6a79b-132">该示例还会清除所有方案设置，然后添加了对未转义百分比编码路径分隔符，使用 http 方案的支持。</span><span class="sxs-lookup"><span data-stu-id="6a79b-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6a79b-133">代码</span><span class="sxs-lookup"><span data-stu-id="6a79b-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a79b-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a79b-134">See Also</span></span>  
 [<span data-ttu-id="6a79b-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="6a79b-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
