---
title: <idn> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 5fe2eafee702be96bfdca80a06af4a040d9ef0f6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664125"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="59063-102">\<idn > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="59063-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="59063-103">指定是否将国际化域名 (IDN) 分析应用于域名。</span><span class="sxs-lookup"><span data-stu-id="59063-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="59063-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="59063-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="59063-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="59063-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="59063-106">\<Uri > 元素 (Uri 设置)</span><span class="sxs-lookup"><span data-stu-id="59063-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="59063-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="59063-107">\<idn></span></span>](idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="59063-108">语法</span><span class="sxs-lookup"><span data-stu-id="59063-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59063-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59063-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59063-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59063-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59063-111">特性</span><span class="sxs-lookup"><span data-stu-id="59063-111">Attributes</span></span>  
  
|<span data-ttu-id="59063-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="59063-112">**Element**</span></span>|<span data-ttu-id="59063-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="59063-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="59063-114">指定是否将国际化域名 (IDN) 分析应用于域名。默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="59063-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59063-115">子元素</span><span class="sxs-lookup"><span data-stu-id="59063-115">Child Elements</span></span>  
 <span data-ttu-id="59063-116">无</span><span class="sxs-lookup"><span data-stu-id="59063-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59063-117">父元素</span><span class="sxs-lookup"><span data-stu-id="59063-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59063-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="59063-118">**Element**</span></span>|<span data-ttu-id="59063-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="59063-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59063-120">oma-uri</span><span class="sxs-lookup"><span data-stu-id="59063-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="59063-121">包含指定 .NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="59063-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59063-122">备注</span><span class="sxs-lookup"><span data-stu-id="59063-122">Remarks</span></span>  
 <span data-ttu-id="59063-123">已在<xref:System.Uri> .NET Framework 3.5 中扩展了现有的类。</span><span class="sxs-lookup"><span data-stu-id="59063-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="59063-124">3.0 SP1 和 2.0 SP1, 支持国际资源标识符 (IRI) 和国际化域名 (IDN)。</span><span class="sxs-lookup"><span data-stu-id="59063-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="59063-125">当前用户将看不到 .NET Framework 2.0 行为中的任何更改, 除非它们专门启用 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="59063-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="59063-126">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="59063-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="59063-127">若要启用对 IRI 的支持, 需要以下两项更改:</span><span class="sxs-lookup"><span data-stu-id="59063-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="59063-128">将以下行添加到 .NET Framework 2.0 目录下的 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="59063-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="59063-129">指定是否要将国际化域名 (IDN) 分析应用于域名, 以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="59063-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="59063-130">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="59063-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="59063-131">根据所使用的 DNS 服务器, IDN 有三个可能的值:</span><span class="sxs-lookup"><span data-stu-id="59063-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="59063-132">已启用 idn = 全部</span><span class="sxs-lookup"><span data-stu-id="59063-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="59063-133">此值会将任何 Unicode 域名转换为其 Punycode 等效项 (IDN 名称)。</span><span class="sxs-lookup"><span data-stu-id="59063-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="59063-134">启用 idn = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="59063-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="59063-135">此值会将本地 Intranet 上的所有 Unicode 域名转换为使用 Punycode 等效项 (IDN 名称)。</span><span class="sxs-lookup"><span data-stu-id="59063-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="59063-136">在这种情况下, 为了处理本地 Intranet 上的国际名称, 用于 Intranet 的 DNS 服务器应该支持 Unicode 名称解析。</span><span class="sxs-lookup"><span data-stu-id="59063-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="59063-137">启用 idn = 无</span><span class="sxs-lookup"><span data-stu-id="59063-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="59063-138">此值不会将任何 Unicode 域名转换为使用 Punycode。</span><span class="sxs-lookup"><span data-stu-id="59063-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="59063-139">这是与 .NET Framework 2.0 行为一致的默认值。</span><span class="sxs-lookup"><span data-stu-id="59063-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="59063-140">启用 IDN 可以将域名中所有 Unicode 标签转换成标签的 Punycode 等同项。</span><span class="sxs-lookup"><span data-stu-id="59063-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="59063-141">Punycode 名称只包含 ASCII 字符，并且始终以 xn-- 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="59063-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="59063-142">这样是为了支持 Internet 上的 DNS 服务器，因为大部分 DNS 服务器仅支持 ASCII 字符（参见 RFC 3940）。</span><span class="sxs-lookup"><span data-stu-id="59063-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="59063-143">配置文件</span><span class="sxs-lookup"><span data-stu-id="59063-143">Configuration Files</span></span>  
 <span data-ttu-id="59063-144">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="59063-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59063-145">示例</span><span class="sxs-lookup"><span data-stu-id="59063-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="59063-146">描述</span><span class="sxs-lookup"><span data-stu-id="59063-146">Description</span></span>  
 <span data-ttu-id="59063-147">下面的示例演示<xref:System.Uri>类使用的配置, 以支持 IRI 分析和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="59063-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="59063-148">代码</span><span class="sxs-lookup"><span data-stu-id="59063-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59063-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="59063-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="59063-150">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="59063-150">Network Settings Schema</span></span>](index.md)
