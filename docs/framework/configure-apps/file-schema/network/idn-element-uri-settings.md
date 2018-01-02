---
title: "&lt;idn&gt;元素 （Uri 设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 44e2db95ec354fff4356a3619fa8230faf67544d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltidngt-element-uri-settings"></a><span data-ttu-id="cc60d-102">&lt;idn&gt;元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="cc60d-102">&lt;idn&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="cc60d-103">指定是否国际化域名 (IDN) 分析将应用于域的名称。</span><span class="sxs-lookup"><span data-stu-id="cc60d-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="cc60d-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="cc60d-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="cc60d-105">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="cc60d-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="cc60d-106">\<Uri > 元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="cc60d-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="cc60d-107">\<idn ></span><span class="sxs-lookup"><span data-stu-id="cc60d-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="cc60d-108">语法</span><span class="sxs-lookup"><span data-stu-id="cc60d-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc60d-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc60d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc60d-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cc60d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc60d-111">特性</span><span class="sxs-lookup"><span data-stu-id="cc60d-111">Attributes</span></span>  
  
|<span data-ttu-id="cc60d-112">**元素**</span><span class="sxs-lookup"><span data-stu-id="cc60d-112">**Element**</span></span>|<span data-ttu-id="cc60d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc60d-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="cc60d-114">指定是否国际化域名 (IDN) 分析应用到一个域名称的默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="cc60d-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc60d-115">子元素</span><span class="sxs-lookup"><span data-stu-id="cc60d-115">Child Elements</span></span>  
 <span data-ttu-id="cc60d-116">无</span><span class="sxs-lookup"><span data-stu-id="cc60d-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc60d-117">父元素</span><span class="sxs-lookup"><span data-stu-id="cc60d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cc60d-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="cc60d-118">**Element**</span></span>|<span data-ttu-id="cc60d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc60d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cc60d-120">uri</span><span class="sxs-lookup"><span data-stu-id="cc60d-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="cc60d-121">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="cc60d-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc60d-122">备注</span><span class="sxs-lookup"><span data-stu-id="cc60d-122">Remarks</span></span>  
 <span data-ttu-id="cc60d-123">现有<xref:System.Uri>已在.NET Framework 3.5 扩展类。</span><span class="sxs-lookup"><span data-stu-id="cc60d-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="cc60d-124">3.0 SP1 和 2.0 SP1 中的对国际资源标识符 (IRI) 和国际化域名 (IDN) 的支持。</span><span class="sxs-lookup"><span data-stu-id="cc60d-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="cc60d-125">当前用户将不会看到从.NET Framework 2.0 行为的任何更改，除非专门允许 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="cc60d-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="cc60d-126">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="cc60d-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cc60d-127">若要启用对 IRI 的支持，以下两项更改是必需的：</span><span class="sxs-lookup"><span data-stu-id="cc60d-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="cc60d-128">将以下行添加到.NET Framework 2.0 目录下的 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="cc60d-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="cc60d-129">指定是否要国际化域名 (IDN) 分析应用到的域名以及是否应应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="cc60d-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="cc60d-130">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="cc60d-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="cc60d-131">有用于 IDN 具体取决于使用的 DNS 服务器的三个可能的值：</span><span class="sxs-lookup"><span data-stu-id="cc60d-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="cc60d-132">启用 idn = All</span><span class="sxs-lookup"><span data-stu-id="cc60d-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="cc60d-133">此值会将任何 Unicode 域名称转换为其 Punycode 等效项 （IDN 名称）。</span><span class="sxs-lookup"><span data-stu-id="cc60d-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="cc60d-134">启用 idn = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="cc60d-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="cc60d-135">此值会将所有 Unicode 域名而不是基于本地 Intranet 使用 Punycode 等效 （IDN 名称）。</span><span class="sxs-lookup"><span data-stu-id="cc60d-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="cc60d-136">在这种情况下来处理本地 Intranet 上的国际名称，用于 Intranet DNS 服务器应支持 Unicode 名称解析。</span><span class="sxs-lookup"><span data-stu-id="cc60d-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="cc60d-137">启用 idn = None</span><span class="sxs-lookup"><span data-stu-id="cc60d-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="cc60d-138">此值不会将转换使用 Punycode 任何 Unicode 域名。</span><span class="sxs-lookup"><span data-stu-id="cc60d-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="cc60d-139">这是默认值，这是与.NET Framework 2.0 行为一致。</span><span class="sxs-lookup"><span data-stu-id="cc60d-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="cc60d-140">启用 IDN 可以将域名中所有 Unicode 标签转换成标签的 Punycode 等同项。</span><span class="sxs-lookup"><span data-stu-id="cc60d-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="cc60d-141">Punycode 名称只包含 ASCII 字符，并且始终以 xn-- 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="cc60d-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="cc60d-142">这样是为了支持 Internet 上的 DNS 服务器，因为大部分 DNS 服务器仅支持 ASCII 字符（参见 RFC 3940）。</span><span class="sxs-lookup"><span data-stu-id="cc60d-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="cc60d-143">配置文件</span><span class="sxs-lookup"><span data-stu-id="cc60d-143">Configuration Files</span></span>  
 <span data-ttu-id="cc60d-144">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="cc60d-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc60d-145">示例</span><span class="sxs-lookup"><span data-stu-id="cc60d-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cc60d-146">描述</span><span class="sxs-lookup"><span data-stu-id="cc60d-146">Description</span></span>  
 <span data-ttu-id="cc60d-147">下面的示例演示使用的配置<xref:System.Uri>类，以支持 IRI 分析和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="cc60d-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cc60d-148">代码</span><span class="sxs-lookup"><span data-stu-id="cc60d-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc60d-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc60d-149">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="cc60d-150">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="cc60d-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
