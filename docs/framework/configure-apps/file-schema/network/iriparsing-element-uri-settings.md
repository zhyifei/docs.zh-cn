---
title: '&lt;iriParsing&gt;元素 （Uri 设置）'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: ca8fc86b5b64b971e54eec8f7338010394b73239
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552939"
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="96aa6-102">&lt;iriParsing&gt;元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="96aa6-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="96aa6-103">指定是否对 <xref:System.Uri> 应用国际资源标识符 (IRI) 分析以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="96aa6-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="96aa6-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="96aa6-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="96aa6-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="96aa6-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="96aa6-106">\<Uri > 元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="96aa6-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="96aa6-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="96aa6-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="96aa6-108">语法</span><span class="sxs-lookup"><span data-stu-id="96aa6-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96aa6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="96aa6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="96aa6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="96aa6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96aa6-111">特性</span><span class="sxs-lookup"><span data-stu-id="96aa6-111">Attributes</span></span>  
  
|<span data-ttu-id="96aa6-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="96aa6-112">**Element**</span></span>|<span data-ttu-id="96aa6-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="96aa6-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="96aa6-114">指定是否启用 IRI 分析。</span><span class="sxs-lookup"><span data-stu-id="96aa6-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="96aa6-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="96aa6-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96aa6-116">子元素</span><span class="sxs-lookup"><span data-stu-id="96aa6-116">Child Elements</span></span>  
 <span data-ttu-id="96aa6-117">无</span><span class="sxs-lookup"><span data-stu-id="96aa6-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96aa6-118">父元素</span><span class="sxs-lookup"><span data-stu-id="96aa6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="96aa6-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="96aa6-119">**Element**</span></span>|<span data-ttu-id="96aa6-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="96aa6-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="96aa6-121">uri</span><span class="sxs-lookup"><span data-stu-id="96aa6-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="96aa6-122">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="96aa6-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96aa6-123">备注</span><span class="sxs-lookup"><span data-stu-id="96aa6-123">Remarks</span></span>  
 <span data-ttu-id="96aa6-124">现有<xref:System.Uri>类具有.NET Framework 3.5 中进行了扩展。</span><span class="sxs-lookup"><span data-stu-id="96aa6-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="96aa6-125">3.0 SP1 和 2.0 SP1 提供对国际资源标识符 (IRI) 和国际化域名 (IDN) 的支持。</span><span class="sxs-lookup"><span data-stu-id="96aa6-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="96aa6-126">当前用户不会看到从.NET Framework 2.0 行为的任何更改，除非专门启用 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="96aa6-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="96aa6-127">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="96aa6-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="96aa6-128">若要启用 IRI 支持，以下两项更改是必需的：</span><span class="sxs-lookup"><span data-stu-id="96aa6-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="96aa6-129">将以下行添加到.NET Framework 2.0 目录下的 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="96aa6-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="96aa6-130">指定是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="96aa6-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="96aa6-131">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="96aa6-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="96aa6-132">启用 IRI 分析 (iriParsing 启用 = `true`) 将执行规范化和字符检查根据最新 IRI 规则在 RFC 3987。</span><span class="sxs-lookup"><span data-stu-id="96aa6-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="96aa6-133">默认值是`false`，将执行规范化和字符检查根据 RFC 2396 和 RFC 3986 （适用于 IPv6 文本）。</span><span class="sxs-lookup"><span data-stu-id="96aa6-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="96aa6-134">配置文件</span><span class="sxs-lookup"><span data-stu-id="96aa6-134">Configuration Files</span></span>  
 <span data-ttu-id="96aa6-135">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="96aa6-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96aa6-136">示例</span><span class="sxs-lookup"><span data-stu-id="96aa6-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="96aa6-137">描述</span><span class="sxs-lookup"><span data-stu-id="96aa6-137">Description</span></span>  
 <span data-ttu-id="96aa6-138">下面的示例演示使用的配置<xref:System.Uri>类，以支持分析 IRI 和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="96aa6-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="96aa6-139">代码</span><span class="sxs-lookup"><span data-stu-id="96aa6-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96aa6-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="96aa6-140">See also</span></span>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="96aa6-141">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="96aa6-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
