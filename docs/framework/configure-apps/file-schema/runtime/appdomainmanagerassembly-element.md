---
title: <appDomainManagerAssembly> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154416"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="ffa65-102">\<应用程序域管理器程序集>元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="ffa65-103">指定为过程中的默认应用程序域提供应用程序域管理器的程序集。</span><span class="sxs-lookup"><span data-stu-id="ffa65-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="ffa65-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffa65-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ffa65-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffa65-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ffa65-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<应用程序域管理器组装>**</span><span class="sxs-lookup"><span data-stu-id="ffa65-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa65-107">语法</span><span class="sxs-lookup"><span data-stu-id="ffa65-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffa65-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ffa65-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ffa65-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffa65-110">属性</span><span class="sxs-lookup"><span data-stu-id="ffa65-110">Attributes</span></span>  
  
|<span data-ttu-id="ffa65-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ffa65-111">Attribute</span></span>|<span data-ttu-id="ffa65-112">说明</span><span class="sxs-lookup"><span data-stu-id="ffa65-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="ffa65-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ffa65-113">Required attribute.</span></span> <span data-ttu-id="ffa65-114">指定在此过程中为默认应用程序域提供应用程序域管理器的程序集的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ffa65-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffa65-115">子元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-115">Child Elements</span></span>  
 <span data-ttu-id="ffa65-116">无。</span><span class="sxs-lookup"><span data-stu-id="ffa65-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffa65-117">父元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ffa65-118">元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-118">Element</span></span>|<span data-ttu-id="ffa65-119">说明</span><span class="sxs-lookup"><span data-stu-id="ffa65-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ffa65-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ffa65-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ffa65-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="ffa65-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffa65-122">备注</span><span class="sxs-lookup"><span data-stu-id="ffa65-122">Remarks</span></span>  
 <span data-ttu-id="ffa65-123">要指定应用程序域管理器的类型，必须同时指定此元素和[\<appDomainManagerType>](appdomainmanagertype-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="ffa65-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="ffa65-124">如果未指定其中任一元素，则忽略另一个元素。</span><span class="sxs-lookup"><span data-stu-id="ffa65-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="ffa65-125">加载默认应用程序域时，<xref:System.TypeLoadException>如果指定的程序集不存在，或者程序集不包含[\<appDomainManagerType 指定的类型>](appdomainmanagertype-element.md)元素，则引发该程序集;进程无法启动。</span><span class="sxs-lookup"><span data-stu-id="ffa65-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="ffa65-126">如果找到程序集但版本信息不匹配，则引发 。 <xref:System.IO.FileLoadException></span><span class="sxs-lookup"><span data-stu-id="ffa65-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ffa65-127">当您为默认应用程序域指定应用程序域管理器类型时，从默认应用程序域创建的其他应用程序域将继承应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="ffa65-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="ffa65-128">使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性为新的应用程序域指定不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="ffa65-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="ffa65-129">指定应用程序域管理器类型需要应用程序具有完全信任。</span><span class="sxs-lookup"><span data-stu-id="ffa65-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="ffa65-130">（例如，在桌面上运行的应用程序具有完全信任。如果应用程序没有完全信任，则引发 。 <xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="ffa65-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ffa65-131">有关程序集显示名称的格式，请参阅 属性<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ffa65-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ffa65-132">此配置元素仅在 .NET 框架 4 和更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="ffa65-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffa65-133">示例</span><span class="sxs-lookup"><span data-stu-id="ffa65-133">Example</span></span>  
 <span data-ttu-id="ffa65-134">下面的示例演示如何指定进程默认应用程序域的应用程序域管理器是程序集中`MyMgr``AdMgrExample`的类型。</span><span class="sxs-lookup"><span data-stu-id="ffa65-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffa65-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa65-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ffa65-136">\<应用域管理器类型>元素</span><span class="sxs-lookup"><span data-stu-id="ffa65-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="ffa65-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ffa65-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ffa65-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ffa65-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ffa65-139">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="ffa65-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
