---
title: "&lt;p e&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfdd9bcd1aa458aad705d4ab129646e746d63b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="d6726-102">&lt;p e&gt;元素</span><span class="sxs-lookup"><span data-stu-id="d6726-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="d6726-103">指定用作默认应用程序域的应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="d6726-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="d6726-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6726-104">\<configuration></span></span>  
<span data-ttu-id="d6726-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="d6726-105">\<runtime></span></span>  
<span data-ttu-id="d6726-106">\<p e ></span><span class="sxs-lookup"><span data-stu-id="d6726-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6726-107">语法</span><span class="sxs-lookup"><span data-stu-id="d6726-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6726-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6726-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d6726-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6726-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6726-110">特性</span><span class="sxs-lookup"><span data-stu-id="d6726-110">Attributes</span></span>  
  
|<span data-ttu-id="d6726-111">特性</span><span class="sxs-lookup"><span data-stu-id="d6726-111">Attribute</span></span>|<span data-ttu-id="d6726-112">描述</span><span class="sxs-lookup"><span data-stu-id="d6726-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="d6726-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d6726-113">Required attribute.</span></span> <span data-ttu-id="d6726-114">指定的类型，包括用作进程内的默认应用程序域的应用程序域管理器的命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="d6726-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6726-115">子元素</span><span class="sxs-lookup"><span data-stu-id="d6726-115">Child Elements</span></span>  
 <span data-ttu-id="d6726-116">无。</span><span class="sxs-lookup"><span data-stu-id="d6726-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6726-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d6726-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d6726-118">元素</span><span class="sxs-lookup"><span data-stu-id="d6726-118">Element</span></span>|<span data-ttu-id="d6726-119">说明</span><span class="sxs-lookup"><span data-stu-id="d6726-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6726-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d6726-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d6726-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="d6726-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6726-122">备注</span><span class="sxs-lookup"><span data-stu-id="d6726-122">Remarks</span></span>  
 <span data-ttu-id="d6726-123">若要指定应用程序域管理器的类型，你必须同时指定此元素与[ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d6726-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="d6726-124">如果未指定任一这些元素，另一个被忽略。</span><span class="sxs-lookup"><span data-stu-id="d6726-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="d6726-125">加载默认应用程序域后，<xref:System.TypeLoadException>如果中由指定的程序集不存在指定的类型，将引发[ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)元素; 和进程无法将到开始日期。</span><span class="sxs-lookup"><span data-stu-id="d6726-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="d6726-126">当指定默认应用程序域的应用程序域管理器类型时，从默认应用程序域创建其他应用程序域继承的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="d6726-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="d6726-127">使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性以指定新的应用程序域不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="d6726-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="d6726-128">指定的应用程序域管理器类型要求应用程序具有完全信任。</span><span class="sxs-lookup"><span data-stu-id="d6726-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="d6726-129">（例如，在桌面上运行的应用程序具有完全信任。）如果应用程序不具有完全信任，<xref:System.TypeLoadException>引发。</span><span class="sxs-lookup"><span data-stu-id="d6726-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="d6726-130">类型和命名空间的格式是相同的格式用于<xref:System.Type.FullName%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="d6726-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="d6726-131">此配置元素可仅用于[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]及更高版本。</span><span class="sxs-lookup"><span data-stu-id="d6726-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6726-132">示例</span><span class="sxs-lookup"><span data-stu-id="d6726-132">Example</span></span>  
 <span data-ttu-id="d6726-133">下面的示例演示如何指定进程的默认应用程序域的应用程序域管理器是`MyMgr`键入`AdMgrExample`程序集。</span><span class="sxs-lookup"><span data-stu-id="d6726-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6726-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6726-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d6726-135">\<appDomainManagerAssembly > 元素</span><span class="sxs-lookup"><span data-stu-id="d6726-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="d6726-136">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d6726-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d6726-137">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d6726-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d6726-138">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="d6726-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
