---
title: <appDomainManagerAssembly> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 7ba52cdf0102af05954509a11fa90e9b8a337876
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118319"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="2dda6-102">\<B l y > 元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="2dda6-103">指定为过程中的默认应用程序域提供应用程序域管理器的程序集。</span><span class="sxs-lookup"><span data-stu-id="2dda6-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="2dda6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2dda6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2dda6-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="2dda6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2dda6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<b l y >**</span><span class="sxs-lookup"><span data-stu-id="2dda6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dda6-107">语法</span><span class="sxs-lookup"><span data-stu-id="2dda6-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dda6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2dda6-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2dda6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dda6-110">特性</span><span class="sxs-lookup"><span data-stu-id="2dda6-110">Attributes</span></span>  
  
|<span data-ttu-id="2dda6-111">特性</span><span class="sxs-lookup"><span data-stu-id="2dda6-111">Attribute</span></span>|<span data-ttu-id="2dda6-112">描述</span><span class="sxs-lookup"><span data-stu-id="2dda6-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="2dda6-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2dda6-113">Required attribute.</span></span> <span data-ttu-id="2dda6-114">指定为进程中的默认应用程序域提供应用程序域管理器的程序集的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2dda6-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dda6-115">子元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-115">Child Elements</span></span>  
 <span data-ttu-id="2dda6-116">无。</span><span class="sxs-lookup"><span data-stu-id="2dda6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dda6-117">父元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2dda6-118">元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-118">Element</span></span>|<span data-ttu-id="2dda6-119">描述</span><span class="sxs-lookup"><span data-stu-id="2dda6-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2dda6-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2dda6-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2dda6-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="2dda6-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dda6-122">备注</span><span class="sxs-lookup"><span data-stu-id="2dda6-122">Remarks</span></span>  
 <span data-ttu-id="2dda6-123">若要指定应用程序域管理器的类型，必须同时指定此元素和[\<y p e >](appdomainmanagertype-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="2dda6-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="2dda6-124">如果未指定这些元素中的任何一个，则会忽略另一个。</span><span class="sxs-lookup"><span data-stu-id="2dda6-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="2dda6-125">在加载默认应用程序域时，如果指定的程序集不存在，或者如果程序集不包含由[\<y p e >](appdomainmanagertype-element.md)元素指定的类型，则会引发 <xref:System.TypeLoadException>;并且进程无法启动。</span><span class="sxs-lookup"><span data-stu-id="2dda6-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="2dda6-126">如果找到程序集，但版本信息不匹配，则会引发 <xref:System.IO.FileLoadException>。</span><span class="sxs-lookup"><span data-stu-id="2dda6-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="2dda6-127">指定默认应用程序域的应用程序域管理器类型时，从默认应用程序域创建的其他应用程序域将继承应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="2dda6-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="2dda6-128">使用 "<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>" 和 "<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>" 属性为新的应用程序域指定不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="2dda6-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="2dda6-129">指定应用程序域管理器类型要求应用程序具有完全信任。</span><span class="sxs-lookup"><span data-stu-id="2dda6-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="2dda6-130">（例如，在桌面上运行的应用程序具有完全信任。）如果应用程序不具有完全信任，则会引发 <xref:System.TypeLoadException>。</span><span class="sxs-lookup"><span data-stu-id="2dda6-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="2dda6-131">有关程序集显示名称的格式，请参见 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="2dda6-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="2dda6-132">此配置元素仅在 .NET Framework 4 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="2dda6-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dda6-133">示例</span><span class="sxs-lookup"><span data-stu-id="2dda6-133">Example</span></span>  
 <span data-ttu-id="2dda6-134">下面的示例演示如何指定进程的默认应用程序域的应用程序域管理器是 `AdMgrExample` 程序集中的 `MyMgr` 类型。</span><span class="sxs-lookup"><span data-stu-id="2dda6-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dda6-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dda6-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2dda6-136">\<Y p e > 元素</span><span class="sxs-lookup"><span data-stu-id="2dda6-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="2dda6-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="2dda6-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2dda6-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2dda6-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2dda6-139">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="2dda6-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
