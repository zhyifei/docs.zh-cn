---
title: '&lt;appDomainManagerAssembly&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e2c43a5cfba89df3ae90950f09a7a947729f51b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746591"
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="9a9b5-102">&lt;appDomainManagerAssembly&gt;元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="9a9b5-103">指定为过程中的默认应用程序域提供应用程序域管理器的程序集。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="9a9b5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a9b5-104">\<configuration></span></span>  
<span data-ttu-id="9a9b5-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="9a9b5-105">\<runtime></span></span>  
<span data-ttu-id="9a9b5-106">\<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="9a9b5-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9b5-107">语法</span><span class="sxs-lookup"><span data-stu-id="9a9b5-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a9b5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9a9b5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a9b5-110">特性</span><span class="sxs-lookup"><span data-stu-id="9a9b5-110">Attributes</span></span>  
  
|<span data-ttu-id="9a9b5-111">特性</span><span class="sxs-lookup"><span data-stu-id="9a9b5-111">Attribute</span></span>|<span data-ttu-id="9a9b5-112">描述</span><span class="sxs-lookup"><span data-stu-id="9a9b5-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="9a9b5-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-113">Required attribute.</span></span> <span data-ttu-id="9a9b5-114">指定进程中的默认应用程序域提供应用程序域管理器的程序集的显示的名称。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a9b5-115">子元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-115">Child Elements</span></span>  
 <span data-ttu-id="9a9b5-116">无。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a9b5-117">父元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9a9b5-118">元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-118">Element</span></span>|<span data-ttu-id="9a9b5-119">描述</span><span class="sxs-lookup"><span data-stu-id="9a9b5-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9a9b5-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9a9b5-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a9b5-122">备注</span><span class="sxs-lookup"><span data-stu-id="9a9b5-122">Remarks</span></span>  
 <span data-ttu-id="9a9b5-123">若要指定应用程序域管理器的类型，您必须同时指定此元素以及[ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="9a9b5-124">如果未指定这些元素之一，另一个被忽略。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="9a9b5-125">加载默认应用程序域时，<xref:System.TypeLoadException>如果指定的程序集不存在，或者如果该程序集不包含由指定的类型则会引发[ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素; 和进程无法启动。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="9a9b5-126">如果找到的程序集，但版本信息不匹配，<xref:System.IO.FileLoadException>引发。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="9a9b5-127">指定默认应用程序域的应用程序域管理器类型，请从默认应用程序域创建其他应用程序域将继承的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="9a9b5-128">使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性以指定新的应用程序域是不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="9a9b5-129">指定应用程序域管理器类型要求具有完全信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="9a9b5-130">（例如，在桌面上运行的应用程序具有完全信任。）如果应用程序不具有完全信任，<xref:System.TypeLoadException>引发。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="9a9b5-131">有关程序集显示名称的格式，请参阅<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="9a9b5-132">此配置元素是仅适用于[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]及更高版本。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a9b5-133">示例</span><span class="sxs-lookup"><span data-stu-id="9a9b5-133">Example</span></span>  
 <span data-ttu-id="9a9b5-134">下面的示例演示如何指定进程的默认应用程序域的应用程序域管理器是`MyMgr`中键入`AdMgrExample`程序集。</span><span class="sxs-lookup"><span data-stu-id="9a9b5-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a9b5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a9b5-135">See also</span></span>
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9a9b5-136">\<appDomainManagerType > 元素</span><span class="sxs-lookup"><span data-stu-id="9a9b5-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [<span data-ttu-id="9a9b5-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="9a9b5-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9a9b5-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9a9b5-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9a9b5-139">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="9a9b5-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
