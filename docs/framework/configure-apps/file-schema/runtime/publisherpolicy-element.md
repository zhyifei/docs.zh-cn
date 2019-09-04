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
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252384"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="152a7-102">\<Publisherpolicy apply > 元素</span><span class="sxs-lookup"><span data-stu-id="152a7-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="152a7-103">指定运行时是否使用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="152a7-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="152a7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="152a7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="152a7-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="152a7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="152a7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="152a7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="152a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="152a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="152a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Publisherpolicy apply >**</span><span class="sxs-lookup"><span data-stu-id="152a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="152a7-109">语法</span><span class="sxs-lookup"><span data-stu-id="152a7-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="152a7-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="152a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="152a7-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="152a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="152a7-112">特性</span><span class="sxs-lookup"><span data-stu-id="152a7-112">Attributes</span></span>  
  
|<span data-ttu-id="152a7-113">特性</span><span class="sxs-lookup"><span data-stu-id="152a7-113">Attribute</span></span>|<span data-ttu-id="152a7-114">描述</span><span class="sxs-lookup"><span data-stu-id="152a7-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="152a7-115">指定是否应用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="152a7-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="152a7-116">应用属性</span><span class="sxs-lookup"><span data-stu-id="152a7-116">apply Attribute</span></span>  
  
|<span data-ttu-id="152a7-117">值</span><span class="sxs-lookup"><span data-stu-id="152a7-117">Value</span></span>|<span data-ttu-id="152a7-118">描述</span><span class="sxs-lookup"><span data-stu-id="152a7-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="152a7-119">应用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="152a7-119">Applies publisher policy.</span></span> <span data-ttu-id="152a7-120">此为默认设置。</span><span class="sxs-lookup"><span data-stu-id="152a7-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="152a7-121">不应用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="152a7-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="152a7-122">子元素</span><span class="sxs-lookup"><span data-stu-id="152a7-122">Child Elements</span></span>  

<span data-ttu-id="152a7-123">无。</span><span class="sxs-lookup"><span data-stu-id="152a7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="152a7-124">父元素</span><span class="sxs-lookup"><span data-stu-id="152a7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="152a7-125">元素</span><span class="sxs-lookup"><span data-stu-id="152a7-125">Element</span></span>|<span data-ttu-id="152a7-126">描述</span><span class="sxs-lookup"><span data-stu-id="152a7-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="152a7-127">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="152a7-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="152a7-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="152a7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="152a7-129">封装每个程序集的绑定策略和程序集位置。</span><span class="sxs-lookup"><span data-stu-id="152a7-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="152a7-130">为每`<dependentAssembly>`个程序集使用一个元素。</span><span class="sxs-lookup"><span data-stu-id="152a7-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="152a7-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="152a7-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="152a7-132">备注</span><span class="sxs-lookup"><span data-stu-id="152a7-132">Remarks</span></span>  
 <span data-ttu-id="152a7-133">当组件供应商发布程序集的新版本时，供应商可以包括发行者策略，以便使用旧版本的应用程序现在使用新版本。</span><span class="sxs-lookup"><span data-stu-id="152a7-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="152a7-134">若要指定是否将发布服务器策略应用于特定程序集，请将 **\<publisherpolicy apply >** 元素放在 **\<dependentAssembly >** 元素中。</span><span class="sxs-lookup"><span data-stu-id="152a7-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="152a7-135">**Apply**属性的默认设置为 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="152a7-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="152a7-136">如果将**apply**特性设置为 "**否**"，则将替代程序集以前的 **"是"** 设置。</span><span class="sxs-lookup"><span data-stu-id="152a7-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="152a7-137">若要让应用程序使用应用程序配置文件中的[ \<publisherpolicy apply apply = "no"/>](publisherpolicy-element.md)元素显式忽略发行者策略，则必须具有权限。</span><span class="sxs-lookup"><span data-stu-id="152a7-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="152a7-138">通过在<xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission>上设置标志来授予权限。</span><span class="sxs-lookup"><span data-stu-id="152a7-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="152a7-139">有关详细信息，请参阅[程序集绑定重定向安全权限](../../assembly-binding-redirection-security-permission.md)。</span><span class="sxs-lookup"><span data-stu-id="152a7-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="152a7-140">示例</span><span class="sxs-lookup"><span data-stu-id="152a7-140">Example</span></span>  
 <span data-ttu-id="152a7-141">下面的示例将关闭程序集`myAssembly`的发布服务器策略。</span><span class="sxs-lookup"><span data-stu-id="152a7-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="152a7-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="152a7-142">See also</span></span>

- [<span data-ttu-id="152a7-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="152a7-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="152a7-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="152a7-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="152a7-145">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="152a7-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="152a7-146">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="152a7-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
