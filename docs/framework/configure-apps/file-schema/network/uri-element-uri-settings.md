---
title: <uri> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697439"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="2bd10-102">\<uri > 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="2bd10-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="2bd10-103">包含指定 .NET Framework 如何处理使用统一资源标识符（Uri）表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="2bd10-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="2bd10-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2bd10-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2bd10-105">&nbsp; @ no__t-1 **\<uri >**</span><span class="sxs-lookup"><span data-stu-id="2bd10-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd10-106">语法</span><span class="sxs-lookup"><span data-stu-id="2bd10-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bd10-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2bd10-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2bd10-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2bd10-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bd10-109">特性</span><span class="sxs-lookup"><span data-stu-id="2bd10-109">Attributes</span></span>  
 <span data-ttu-id="2bd10-110">无。</span><span class="sxs-lookup"><span data-stu-id="2bd10-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2bd10-111">子元素</span><span class="sxs-lookup"><span data-stu-id="2bd10-111">Child Elements</span></span>  
  
|<span data-ttu-id="2bd10-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="2bd10-112">**Element**</span></span>|<span data-ttu-id="2bd10-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2bd10-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2bd10-114">idn</span><span class="sxs-lookup"><span data-stu-id="2bd10-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="2bd10-115">指定是否对域名应用国际化域名 (IDN) 分析。</span><span class="sxs-lookup"><span data-stu-id="2bd10-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="2bd10-116">Iriparsing></span><span class="sxs-lookup"><span data-stu-id="2bd10-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="2bd10-117">指定是否将国际化资源标识符（IRI）分析应用到 <xref:System.Uri> 以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="2bd10-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="2bd10-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="2bd10-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="2bd10-119">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="2bd10-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bd10-120">父元素</span><span class="sxs-lookup"><span data-stu-id="2bd10-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2bd10-121">**元素**</span><span class="sxs-lookup"><span data-stu-id="2bd10-121">**Element**</span></span>|<span data-ttu-id="2bd10-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="2bd10-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2bd10-123">configuration</span><span class="sxs-lookup"><span data-stu-id="2bd10-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="2bd10-124">包含所有命名空间的设置。</span><span class="sxs-lookup"><span data-stu-id="2bd10-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bd10-125">备注</span><span class="sxs-lookup"><span data-stu-id="2bd10-125">Remarks</span></span>  
 <span data-ttu-id="2bd10-126">@No__t-0 元素包含 <xref:System.Net> 命名空间中的类所使用的 @no__t 1 类的成员的设置。</span><span class="sxs-lookup"><span data-stu-id="2bd10-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="2bd10-127">设置配置对 IRI 和 IDN 的支持。</span><span class="sxs-lookup"><span data-stu-id="2bd10-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bd10-128">示例</span><span class="sxs-lookup"><span data-stu-id="2bd10-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2bd10-129">描述</span><span class="sxs-lookup"><span data-stu-id="2bd10-129">Description</span></span>  
 <span data-ttu-id="2bd10-130">下面的示例演示 <xref:System.Uri> 类用于支持 IRI 分析和 IDN 名称的配置。</span><span class="sxs-lookup"><span data-stu-id="2bd10-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="2bd10-131">该示例还会清除所有方案设置，然后添加对 http 方案不转义百分号编码路径分隔符的支持。</span><span class="sxs-lookup"><span data-stu-id="2bd10-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2bd10-132">代码</span><span class="sxs-lookup"><span data-stu-id="2bd10-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2bd10-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bd10-133">See also</span></span>

- [<span data-ttu-id="2bd10-134">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="2bd10-134">Network Settings Schema</span></span>](index.md)
