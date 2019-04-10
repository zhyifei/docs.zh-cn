---
title: <idn> 元素 （Uri 设置）
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 2d2729f9120d6b6fe673904ad2bf6d005ddf5469
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321746"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="ee54e-102">\<idn > 元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="ee54e-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="ee54e-103">指定是否对域名应用国际化域名 (IDN) 分析。</span><span class="sxs-lookup"><span data-stu-id="ee54e-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="ee54e-104">架构层次结构</span><span class="sxs-lookup"><span data-stu-id="ee54e-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="ee54e-105">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="ee54e-106">\<Uri > 元素 （Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="ee54e-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="ee54e-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="ee54e-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="ee54e-108">语法</span><span class="sxs-lookup"><span data-stu-id="ee54e-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee54e-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee54e-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee54e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee54e-111">特性</span><span class="sxs-lookup"><span data-stu-id="ee54e-111">Attributes</span></span>  
  
|**<span data-ttu-id="ee54e-112">元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-112">Element</span></span>**|**<span data-ttu-id="ee54e-113">描述</span><span class="sxs-lookup"><span data-stu-id="ee54e-113">Description</span></span>**|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="ee54e-114">指定对域名应用国际化域名 (IDN) 分析的默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="ee54e-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee54e-115">子元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-115">Child Elements</span></span>  
 <span data-ttu-id="ee54e-116">None</span><span class="sxs-lookup"><span data-stu-id="ee54e-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee54e-117">父元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-117">Parent Elements</span></span>  
  
|**<span data-ttu-id="ee54e-118">元素</span><span class="sxs-lookup"><span data-stu-id="ee54e-118">Element</span></span>**|**<span data-ttu-id="ee54e-119">描述</span><span class="sxs-lookup"><span data-stu-id="ee54e-119">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="ee54e-120">uri</span><span class="sxs-lookup"><span data-stu-id="ee54e-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="ee54e-121">包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。</span><span class="sxs-lookup"><span data-stu-id="ee54e-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee54e-122">备注</span><span class="sxs-lookup"><span data-stu-id="ee54e-122">Remarks</span></span>  
 <span data-ttu-id="ee54e-123">现有<xref:System.Uri>类具有.NET Framework 3.5 中进行了扩展。</span><span class="sxs-lookup"><span data-stu-id="ee54e-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="ee54e-124">3.0 SP1 和 2.0 SP1 中的对国际资源标识符 (IRI) 和国际化域名 (IDN) 的支持。</span><span class="sxs-lookup"><span data-stu-id="ee54e-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="ee54e-125">当前用户不会看到从.NET Framework 2.0 行为的任何更改，除非专门启用 IRI 和 IDN 支持。</span><span class="sxs-lookup"><span data-stu-id="ee54e-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="ee54e-126">这确保了 NET Framework 以前版本的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="ee54e-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ee54e-127">若要启用 IRI 支持，以下两项更改是必需的：</span><span class="sxs-lookup"><span data-stu-id="ee54e-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="ee54e-128">将以下行添加到.NET Framework 2.0 目录下的 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="ee54e-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="ee54e-129">指定是否对域名应用国际化域名 (IDN) 分析以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="ee54e-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="ee54e-130">这可以在 machine.config 或应用配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="ee54e-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="ee54e-131">有三个可能的 IDN 值具体取决于使用的 DNS 服务器：</span><span class="sxs-lookup"><span data-stu-id="ee54e-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="ee54e-132">启用 idn = All</span><span class="sxs-lookup"><span data-stu-id="ee54e-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="ee54e-133">此值会将任何 Unicode 域名转换为 Punycode 等效项 （IDN 名称）。</span><span class="sxs-lookup"><span data-stu-id="ee54e-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="ee54e-134">启用 idn = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="ee54e-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="ee54e-135">此值会将不在使用 Punycode 等效项 （IDN 名称） 在本地 Intranet 上的所有 Unicode 域名都转换。</span><span class="sxs-lookup"><span data-stu-id="ee54e-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="ee54e-136">在这种情况下若要处理本地 Intranet 上的国际化名称，用于 Intranet 的 DNS 服务器应该支持 Unicode 名称解析。</span><span class="sxs-lookup"><span data-stu-id="ee54e-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="ee54e-137">启用 idn = 无</span><span class="sxs-lookup"><span data-stu-id="ee54e-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="ee54e-138">此值不会将转换为使用 Punycode 任何 Unicode 域名。</span><span class="sxs-lookup"><span data-stu-id="ee54e-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="ee54e-139">这是默认值是与.NET Framework 2.0 行为一致。</span><span class="sxs-lookup"><span data-stu-id="ee54e-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="ee54e-140">启用 IDN 可以将域名中所有 Unicode 标签转换成标签的 Punycode 等同项。</span><span class="sxs-lookup"><span data-stu-id="ee54e-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="ee54e-141">Punycode 名称只包含 ASCII 字符，并且始终以 xn-- 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="ee54e-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="ee54e-142">这样是为了支持 Internet 上的 DNS 服务器，因为大部分 DNS 服务器仅支持 ASCII 字符（参见 RFC 3940）。</span><span class="sxs-lookup"><span data-stu-id="ee54e-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="ee54e-143">配置文件</span><span class="sxs-lookup"><span data-stu-id="ee54e-143">Configuration Files</span></span>  
 <span data-ttu-id="ee54e-144">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ee54e-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee54e-145">示例</span><span class="sxs-lookup"><span data-stu-id="ee54e-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ee54e-146">描述</span><span class="sxs-lookup"><span data-stu-id="ee54e-146">Description</span></span>  
 <span data-ttu-id="ee54e-147">下面的示例演示使用的配置<xref:System.Uri>类，以支持分析 IRI 和 IDN 名称。</span><span class="sxs-lookup"><span data-stu-id="ee54e-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ee54e-148">代码</span><span class="sxs-lookup"><span data-stu-id="ee54e-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee54e-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee54e-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="ee54e-150">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ee54e-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
