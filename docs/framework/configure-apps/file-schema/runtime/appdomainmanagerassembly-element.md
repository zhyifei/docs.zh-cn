---
title: "&lt;appDomainManagerAssembly&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e07b7bd18f19439f64ed8eaef5bda3bad5cef77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="10637-102">&lt;appDomainManagerAssembly&gt;元素</span><span class="sxs-lookup"><span data-stu-id="10637-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="10637-103">指定为过程中的默认应用程序域提供应用程序域管理器的程序集。</span><span class="sxs-lookup"><span data-stu-id="10637-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="10637-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="10637-104">\<configuration></span></span>  
<span data-ttu-id="10637-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="10637-105">\<runtime></span></span>  
<span data-ttu-id="10637-106">\<appDomainManagerAssembly ></span><span class="sxs-lookup"><span data-stu-id="10637-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10637-107">语法</span><span class="sxs-lookup"><span data-stu-id="10637-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10637-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10637-108">Attributes and Elements</span></span>  
 <span data-ttu-id="10637-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10637-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10637-110">特性</span><span class="sxs-lookup"><span data-stu-id="10637-110">Attributes</span></span>  
  
|<span data-ttu-id="10637-111">特性</span><span class="sxs-lookup"><span data-stu-id="10637-111">Attribute</span></span>|<span data-ttu-id="10637-112">描述</span><span class="sxs-lookup"><span data-stu-id="10637-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="10637-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="10637-113">Required attribute.</span></span> <span data-ttu-id="10637-114">指定用于在过程中的默认应用程序域提供应用程序域管理器的程序集的显示名称。</span><span class="sxs-lookup"><span data-stu-id="10637-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10637-115">子元素</span><span class="sxs-lookup"><span data-stu-id="10637-115">Child Elements</span></span>  
 <span data-ttu-id="10637-116">无。</span><span class="sxs-lookup"><span data-stu-id="10637-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10637-117">父元素</span><span class="sxs-lookup"><span data-stu-id="10637-117">Parent Elements</span></span>  
  
|<span data-ttu-id="10637-118">元素</span><span class="sxs-lookup"><span data-stu-id="10637-118">Element</span></span>|<span data-ttu-id="10637-119">描述</span><span class="sxs-lookup"><span data-stu-id="10637-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10637-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="10637-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10637-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="10637-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10637-122">备注</span><span class="sxs-lookup"><span data-stu-id="10637-122">Remarks</span></span>  
 <span data-ttu-id="10637-123">若要指定应用程序域管理器的类型，你必须同时指定此元素与[ \<p e >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="10637-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="10637-124">如果未指定任一这些元素，另一个被忽略。</span><span class="sxs-lookup"><span data-stu-id="10637-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="10637-125">加载默认应用程序域后，<xref:System.TypeLoadException>如果指定的程序集中不存在，或者如果程序集不包含由指定的类型将引发[ \<p e >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素; 和进程无法启动。</span><span class="sxs-lookup"><span data-stu-id="10637-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="10637-126">如果找到的程序集但不是匹配的版本信息，<xref:System.IO.FileLoadException>引发。</span><span class="sxs-lookup"><span data-stu-id="10637-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="10637-127">当指定默认应用程序域的应用程序域管理器类型时，从默认应用程序域创建其他应用程序域继承的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="10637-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="10637-128">使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性以指定新的应用程序域不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="10637-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="10637-129">指定的应用程序域管理器类型要求应用程序具有完全信任。</span><span class="sxs-lookup"><span data-stu-id="10637-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="10637-130">（例如，在桌面上运行的应用程序具有完全信任。）如果应用程序不具有完全信任，<xref:System.TypeLoadException>引发。</span><span class="sxs-lookup"><span data-stu-id="10637-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="10637-131">有关程序集显示名称的格式，请参阅<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="10637-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="10637-132">此配置元素可仅用于[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]及更高版本。</span><span class="sxs-lookup"><span data-stu-id="10637-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10637-133">示例</span><span class="sxs-lookup"><span data-stu-id="10637-133">Example</span></span>  
 <span data-ttu-id="10637-134">下面的示例演示如何指定进程的默认应用程序域的应用程序域管理器是`MyMgr`键入`AdMgrExample`程序集。</span><span class="sxs-lookup"><span data-stu-id="10637-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10637-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10637-135">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="10637-136">\<p e > 元素</span><span class="sxs-lookup"><span data-stu-id="10637-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [<span data-ttu-id="10637-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="10637-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="10637-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="10637-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="10637-139">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="10637-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
