---
title: <bindingRedirect> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: 1db46d4eb4418682613624182cca133980206ea6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281198"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="7c7dc-102">\<bindingRedirect > 元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="7c7dc-103">将一个程序集版本重定向到另一个版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="7c7dc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c7dc-104">\<configuration></span></span>  
<span data-ttu-id="7c7dc-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="7c7dc-105">\<runtime></span></span>  
<span data-ttu-id="7c7dc-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="7c7dc-106">\<assemblyBinding></span></span>  
<span data-ttu-id="7c7dc-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="7c7dc-107">\<dependentAssembly></span></span>  
<span data-ttu-id="7c7dc-108">\<bindingRedirect></span><span class="sxs-lookup"><span data-stu-id="7c7dc-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7dc-109">语法</span><span class="sxs-lookup"><span data-stu-id="7c7dc-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c7dc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7c7dc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c7dc-112">特性</span><span class="sxs-lookup"><span data-stu-id="7c7dc-112">Attributes</span></span>  
  
|<span data-ttu-id="7c7dc-113">特性</span><span class="sxs-lookup"><span data-stu-id="7c7dc-113">Attribute</span></span>|<span data-ttu-id="7c7dc-114">描述</span><span class="sxs-lookup"><span data-stu-id="7c7dc-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="7c7dc-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="7c7dc-116">指定最初请求的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="7c7dc-117">程序集版本号的格式*major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="7c7dc-118">该版本号的每个部分的有效值介于 0 和 65535 之间。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="7c7dc-119">你还可以按下列格式指定版本范围：</span><span class="sxs-lookup"><span data-stu-id="7c7dc-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="7c7dc-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="7c7dc-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="7c7dc-121">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="7c7dc-122">指定要使用而不是最初请求的版本格式的程序集的版本： *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="7c7dc-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="7c7dc-123">此值可以指定 `oldVersion` 之前的版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c7dc-124">子元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-124">Child Elements</span></span>  
  
|<span data-ttu-id="7c7dc-125">元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-125">Element</span></span>|<span data-ttu-id="7c7dc-126">描述</span><span class="sxs-lookup"><span data-stu-id="7c7dc-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c7dc-127">无</span><span class="sxs-lookup"><span data-stu-id="7c7dc-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="7c7dc-128">父元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7c7dc-129">元素</span><span class="sxs-lookup"><span data-stu-id="7c7dc-129">Element</span></span>|<span data-ttu-id="7c7dc-130">描述</span><span class="sxs-lookup"><span data-stu-id="7c7dc-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="7c7dc-131">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="7c7dc-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="7c7dc-133">封装每个程序集的绑定策略和程序集位置。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="7c7dc-134">为每个程序集使用一个 dependentAssembly 元素。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="7c7dc-135">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c7dc-136">备注</span><span class="sxs-lookup"><span data-stu-id="7c7dc-136">Remarks</span></span>  
 <span data-ttu-id="7c7dc-137">在针对具有强名称的程序集生成 .NET Framework 应用程序时，默认情况下，应用程序在运行时使用该版本的程序集，即使提供了新版本也是如此。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="7c7dc-138">但是，你可以将应用程序配置为针对更新版本的程序集运行。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="7c7dc-139">有关运行时如何使用这些文件来确定要使用的程序集版本的详细信息，请参阅[运行时如何定位程序集](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="7c7dc-140">通过在一个 `bindingRedirect` 元素中包含多个 `dependentAssembly` 元素，你可以重定向多个程序集版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="7c7dc-141">你还可从程序集的更新版本重定向到较旧版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="7c7dc-142">应用程序配置文件中的显式程序集绑定重定向需要安全权限。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="7c7dc-143">这适用于对 .NET Framework 程序集和来自第三方的程序集的重定向。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="7c7dc-144">通过设置授予权限<xref:System.Security.Permissions.SecurityPermissionFlag>标志<xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="7c7dc-145">有关详细信息，请参阅[程序集绑定重定向安全权限](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c7dc-146">示例</span><span class="sxs-lookup"><span data-stu-id="7c7dc-146">Example</span></span>  
 <span data-ttu-id="7c7dc-147">下面的示例演示如何将一个程序集版本重定向到另一个版本。</span><span class="sxs-lookup"><span data-stu-id="7c7dc-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c7dc-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c7dc-148">See also</span></span>
- [<span data-ttu-id="7c7dc-149">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7c7dc-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7c7dc-150">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7c7dc-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7c7dc-151">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="7c7dc-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
