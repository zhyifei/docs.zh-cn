---
title: "&lt;publisherPolicy&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5f629dd347f63c8fb8e624c475bfb0ecf658f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltpublisherpolicygt-element"></a><span data-ttu-id="b808c-102">&lt;publisherPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="b808c-102">&lt;publisherPolicy&gt; Element</span></span>
<span data-ttu-id="b808c-103">指定运行时是否使用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="b808c-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="b808c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b808c-104">\<configuration></span></span>  
<span data-ttu-id="b808c-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="b808c-105">\<runtime></span></span>  
<span data-ttu-id="b808c-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="b808c-106">\<assemblyBinding></span></span>  
<span data-ttu-id="b808c-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="b808c-107">\<dependentAssembly></span></span>  
<span data-ttu-id="b808c-108">\<publisherPolicy ></span><span class="sxs-lookup"><span data-stu-id="b808c-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b808c-109">语法</span><span class="sxs-lookup"><span data-stu-id="b808c-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b808c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b808c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b808c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b808c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b808c-112">特性</span><span class="sxs-lookup"><span data-stu-id="b808c-112">Attributes</span></span>  
  
|<span data-ttu-id="b808c-113">特性</span><span class="sxs-lookup"><span data-stu-id="b808c-113">Attribute</span></span>|<span data-ttu-id="b808c-114">描述</span><span class="sxs-lookup"><span data-stu-id="b808c-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="b808c-115">指定是否要应用发布服务器策略。</span><span class="sxs-lookup"><span data-stu-id="b808c-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="b808c-116">应用特性</span><span class="sxs-lookup"><span data-stu-id="b808c-116">apply Attribute</span></span>  
  
|<span data-ttu-id="b808c-117">值</span><span class="sxs-lookup"><span data-stu-id="b808c-117">Value</span></span>|<span data-ttu-id="b808c-118">描述</span><span class="sxs-lookup"><span data-stu-id="b808c-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="b808c-119">将发布服务器策略的应用。</span><span class="sxs-lookup"><span data-stu-id="b808c-119">Applies publisher policy.</span></span> <span data-ttu-id="b808c-120">此为默认设置。</span><span class="sxs-lookup"><span data-stu-id="b808c-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="b808c-121">不适用于发布服务器策略。</span><span class="sxs-lookup"><span data-stu-id="b808c-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b808c-122">子元素</span><span class="sxs-lookup"><span data-stu-id="b808c-122">Child Elements</span></span>  
 <span data-ttu-id="b808c-123">无。</span><span class="sxs-lookup"><span data-stu-id="b808c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b808c-124">父元素</span><span class="sxs-lookup"><span data-stu-id="b808c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b808c-125">元素</span><span class="sxs-lookup"><span data-stu-id="b808c-125">Element</span></span>|<span data-ttu-id="b808c-126">说明</span><span class="sxs-lookup"><span data-stu-id="b808c-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b808c-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b808c-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b808c-128">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="b808c-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b808c-129">备注</span><span class="sxs-lookup"><span data-stu-id="b808c-129">Remarks</span></span>  
 <span data-ttu-id="b808c-130">当组件供应商释放程序集的新版本时，供应商可以包括发布服务器策略，因此现在使用旧版本的应用程序使用新版本。</span><span class="sxs-lookup"><span data-stu-id="b808c-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="b808c-131">若要指定是否为特定的程序集应用出版商策略，请将 **\<publisherPolicy >**中的元素 **\<dependentAssembly >**元素。</span><span class="sxs-lookup"><span data-stu-id="b808c-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="b808c-132">默认设置**应用**属性是**是**。</span><span class="sxs-lookup"><span data-stu-id="b808c-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="b808c-133">设置**应用**属性设为**没有**替代以前所有**是**的程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="b808c-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="b808c-134">权限是必需的应用程序显式忽略发行者策略使用[ \<publisherPolicy 适用 ="no"/ >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="b808c-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="b808c-135">通过设置授予此权限<xref:System.Security.Permissions.SecurityPermissionFlag>标志<xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="b808c-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="b808c-136">有关详细信息，请参阅[程序集绑定重定向安全权限](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)。</span><span class="sxs-lookup"><span data-stu-id="b808c-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b808c-137">示例</span><span class="sxs-lookup"><span data-stu-id="b808c-137">Example</span></span>  
 <span data-ttu-id="b808c-138">下面的示例从发布服务器策略关闭后的程序集`myAssembly`。</span><span class="sxs-lookup"><span data-stu-id="b808c-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b808c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b808c-139">See Also</span></span>  
 [<span data-ttu-id="b808c-140">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="b808c-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b808c-141">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b808c-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="b808c-142">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="b808c-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="b808c-143">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="b808c-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
