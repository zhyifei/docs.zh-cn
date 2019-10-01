---
title: <iriParsing> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698095"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="c118b-102">\<iriParsing > 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="c118b-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="c118b-103">指定是否对 <xref:System.Uri> 应用国际资源标识符 (IRI) 分析以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="c118b-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="c118b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c118b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c118b-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c118b-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="c118b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<iriParsing >**</span><span class="sxs-lookup"><span data-stu-id="c118b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c118b-107">语法</span><span class="sxs-lookup"><span data-stu-id="c118b-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c118b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c118b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c118b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c118b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c118b-110">特性</span><span class="sxs-lookup"><span data-stu-id="c118b-110">Attributes</span></span>  
  
|<span data-ttu-id="c118b-111">**元素**</span><span class="sxs-lookup"><span data-stu-id="c118b-111">**Element**</span></span>|<span data-ttu-id="c118b-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="c118b-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="c118b-113">指定是否启用 IRI 分析。</span><span class="sxs-lookup"><span data-stu-id="c118b-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="c118b-114">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c118b-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c118b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="c118b-115">Child Elements</span></span>  
 <span data-ttu-id="c118b-116">None</span><span class="sxs-lookup"><span data-stu-id="c118b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c118b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="c118b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c118b-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="c118b-118">**Element**</span></span>|<span data-ttu-id="c118b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c118b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c118b-120">oma-uri</span><span class="sxs-lookup"><span data-stu-id="c118b-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="c118b-121">包含指定 .NET Framework 如何处理使用统一资源标识符（Uri）表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="c118b-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c118b-122">备注</span><span class="sxs-lookup"><span data-stu-id="c118b-122">Remarks</span></span>  
 <span data-ttu-id="c118b-123">现有的 @no__t 0 类已在 .NET Framework 3.5 中扩展。</span><span class="sxs-lookup"><span data-stu-id="c118b-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="c118b-124">3.0 SP1 和 2.0 SP1，提供对国际资源标识符（IRI）和国际化域名（IDN）的支持。</span><span class="sxs-lookup"><span data-stu-id="c118b-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="c118b-125">当前用户将看不到 .NET Framework 2.0 行为中的任何更改，除非它们专门启用 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="c118b-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="c118b-126">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="c118b-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c118b-127">若要启用对 IRI 的支持，需要以下两项更改：</span><span class="sxs-lookup"><span data-stu-id="c118b-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="c118b-128">将以下行添加到 .NET Framework 2.0 目录下的 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="c118b-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="c118b-129">指定是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="c118b-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="c118b-130">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="c118b-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="c118b-131">启用 IRI 分析（启用 iriparsing> = `true`）将根据 RFC 3987 中的最新 IRI 规则执行规范化和字符检查。</span><span class="sxs-lookup"><span data-stu-id="c118b-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="c118b-132">默认值为 `false`，将根据 RFC 2396 和 RFC 3986 （针对 IPv6 文本）执行规范化和字符检查。</span><span class="sxs-lookup"><span data-stu-id="c118b-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="c118b-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="c118b-133">Configuration Files</span></span>  
 <span data-ttu-id="c118b-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="c118b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c118b-135">示例</span><span class="sxs-lookup"><span data-stu-id="c118b-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c118b-136">描述</span><span class="sxs-lookup"><span data-stu-id="c118b-136">Description</span></span>  
 <span data-ttu-id="c118b-137">下面的示例演示 <xref:System.Uri> 类用于支持 IRI 分析和 IDN 名称的配置。</span><span class="sxs-lookup"><span data-stu-id="c118b-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c118b-138">代码</span><span class="sxs-lookup"><span data-stu-id="c118b-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c118b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="c118b-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="c118b-140">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="c118b-140">Network Settings Schema</span></span>](index.md)
