---
title: <publisherPolicy> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076284"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="273b0-102">\<publisherPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="273b0-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="273b0-103">指定运行时是否使用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="273b0-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="273b0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="273b0-104">\<configuration></span></span>  
<span data-ttu-id="273b0-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="273b0-105">\<runtime></span></span>  
<span data-ttu-id="273b0-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="273b0-106">\<assemblyBinding></span></span>  
<span data-ttu-id="273b0-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="273b0-107">\<dependentAssembly></span></span>  
<span data-ttu-id="273b0-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="273b0-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="273b0-109">语法</span><span class="sxs-lookup"><span data-stu-id="273b0-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="273b0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="273b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="273b0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="273b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="273b0-112">特性</span><span class="sxs-lookup"><span data-stu-id="273b0-112">Attributes</span></span>  
  
|<span data-ttu-id="273b0-113">特性</span><span class="sxs-lookup"><span data-stu-id="273b0-113">Attribute</span></span>|<span data-ttu-id="273b0-114">描述</span><span class="sxs-lookup"><span data-stu-id="273b0-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="273b0-115">指定是否将应用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="273b0-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="273b0-116">应用特性</span><span class="sxs-lookup"><span data-stu-id="273b0-116">apply Attribute</span></span>  
  
|<span data-ttu-id="273b0-117">“值”</span><span class="sxs-lookup"><span data-stu-id="273b0-117">Value</span></span>|<span data-ttu-id="273b0-118">描述</span><span class="sxs-lookup"><span data-stu-id="273b0-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="273b0-119">将发布服务器策略应用。</span><span class="sxs-lookup"><span data-stu-id="273b0-119">Applies publisher policy.</span></span> <span data-ttu-id="273b0-120">此为默认设置。</span><span class="sxs-lookup"><span data-stu-id="273b0-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="273b0-121">不适用于发布服务器策略。</span><span class="sxs-lookup"><span data-stu-id="273b0-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="273b0-122">子元素</span><span class="sxs-lookup"><span data-stu-id="273b0-122">Child Elements</span></span>  
 <span data-ttu-id="273b0-123">无。</span><span class="sxs-lookup"><span data-stu-id="273b0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="273b0-124">父元素</span><span class="sxs-lookup"><span data-stu-id="273b0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="273b0-125">元素</span><span class="sxs-lookup"><span data-stu-id="273b0-125">Element</span></span>|<span data-ttu-id="273b0-126">描述</span><span class="sxs-lookup"><span data-stu-id="273b0-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="273b0-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="273b0-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="273b0-128">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="273b0-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="273b0-129">备注</span><span class="sxs-lookup"><span data-stu-id="273b0-129">Remarks</span></span>  
 <span data-ttu-id="273b0-130">时组件供应商发布新版本的程序集，供应商可以包括发布服务器策略，以便现在使用旧版本的应用程序使用新版本。</span><span class="sxs-lookup"><span data-stu-id="273b0-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="273b0-131">若要指定是否为特定的程序集应用出版商策略，请将 **\<publisherPolicy >** 中的元素 **\<dependentAssembly >** 元素。</span><span class="sxs-lookup"><span data-stu-id="273b0-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="273b0-132">默认设置为**应用**属性是**是**。</span><span class="sxs-lookup"><span data-stu-id="273b0-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="273b0-133">设置**应用**归于**没有**替代以前所有**是**程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="273b0-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="273b0-134">权限是以显式忽略发行者策略使用的应用需要[ \<apply ="no"/ >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="273b0-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="273b0-135">通过设置授予权限<xref:System.Security.Permissions.SecurityPermissionFlag>标志<xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="273b0-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="273b0-136">有关详细信息，请参阅[程序集绑定重定向安全权限](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)。</span><span class="sxs-lookup"><span data-stu-id="273b0-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="273b0-137">示例</span><span class="sxs-lookup"><span data-stu-id="273b0-137">Example</span></span>  
 <span data-ttu-id="273b0-138">下面的示例会关闭发行者策略程序集， `myAssembly`。</span><span class="sxs-lookup"><span data-stu-id="273b0-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="273b0-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="273b0-139">See also</span></span>

- [<span data-ttu-id="273b0-140">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="273b0-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="273b0-141">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="273b0-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="273b0-142">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="273b0-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="273b0-143">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="273b0-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
