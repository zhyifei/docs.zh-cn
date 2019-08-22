---
title: <iriParsing> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664091"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="b74ff-102">\<Iriparsing> > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="b74ff-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="b74ff-103">指定是否对 <xref:System.Uri> 应用国际资源标识符 (IRI) 分析以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="b74ff-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="b74ff-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="b74ff-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="b74ff-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="b74ff-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="b74ff-106">\<Uri > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="b74ff-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="b74ff-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="b74ff-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="b74ff-108">语法</span><span class="sxs-lookup"><span data-stu-id="b74ff-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b74ff-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b74ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b74ff-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b74ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b74ff-111">特性</span><span class="sxs-lookup"><span data-stu-id="b74ff-111">Attributes</span></span>  
  
|<span data-ttu-id="b74ff-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="b74ff-112">**Element**</span></span>|<span data-ttu-id="b74ff-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="b74ff-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="b74ff-114">指定是否启用 IRI 分析。</span><span class="sxs-lookup"><span data-stu-id="b74ff-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="b74ff-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b74ff-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b74ff-116">子元素</span><span class="sxs-lookup"><span data-stu-id="b74ff-116">Child Elements</span></span>  
 <span data-ttu-id="b74ff-117">无</span><span class="sxs-lookup"><span data-stu-id="b74ff-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b74ff-118">父元素</span><span class="sxs-lookup"><span data-stu-id="b74ff-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b74ff-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="b74ff-119">**Element**</span></span>|<span data-ttu-id="b74ff-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="b74ff-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b74ff-121">oma-uri</span><span class="sxs-lookup"><span data-stu-id="b74ff-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="b74ff-122">包含指定 .NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="b74ff-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b74ff-123">备注</span><span class="sxs-lookup"><span data-stu-id="b74ff-123">Remarks</span></span>  
 <span data-ttu-id="b74ff-124">已在<xref:System.Uri> .NET Framework 3.5 中扩展了现有的类。</span><span class="sxs-lookup"><span data-stu-id="b74ff-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="b74ff-125">3.0 SP1 和 2.0 SP1, 提供对国际资源标识符 (IRI) 和国际化域名 (IDN) 的支持。</span><span class="sxs-lookup"><span data-stu-id="b74ff-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="b74ff-126">当前用户将看不到 .NET Framework 2.0 行为中的任何更改, 除非它们专门启用 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="b74ff-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="b74ff-127">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="b74ff-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b74ff-128">若要启用对 IRI 的支持, 需要以下两项更改:</span><span class="sxs-lookup"><span data-stu-id="b74ff-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="b74ff-129">将以下行添加到 .NET Framework 2.0 目录下的 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="b74ff-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="b74ff-130">指定是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="b74ff-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="b74ff-131">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="b74ff-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="b74ff-132">启用 IRI 分析 (启用 iriparsing> = `true`) 将根据 RFC 3987 中的最新 IRI 规则执行规范化和字符检查。</span><span class="sxs-lookup"><span data-stu-id="b74ff-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="b74ff-133">默认值为`false` , 将根据 rfc 2396 和 rfc 3986 (针对 IPv6 文本) 执行规范化和字符检查。</span><span class="sxs-lookup"><span data-stu-id="b74ff-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="b74ff-134">配置文件</span><span class="sxs-lookup"><span data-stu-id="b74ff-134">Configuration Files</span></span>  
 <span data-ttu-id="b74ff-135">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="b74ff-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b74ff-136">示例</span><span class="sxs-lookup"><span data-stu-id="b74ff-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b74ff-137">描述</span><span class="sxs-lookup"><span data-stu-id="b74ff-137">Description</span></span>  
 <span data-ttu-id="b74ff-138">下面的示例演示<xref:System.Uri>类使用的配置, 以支持 IRI 分析和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="b74ff-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b74ff-139">代码</span><span class="sxs-lookup"><span data-stu-id="b74ff-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b74ff-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="b74ff-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="b74ff-141">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b74ff-141">Network Settings Schema</span></span>](index.md)
