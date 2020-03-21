---
title: <appDomainManagerType> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154417"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="86d54-102">\<应用域管理器类型>元素</span><span class="sxs-lookup"><span data-stu-id="86d54-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="86d54-103">指定用作默认应用程序域的应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="86d54-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="86d54-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86d54-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86d54-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="86d54-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="86d54-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<应用域管理器类型>**</span><span class="sxs-lookup"><span data-stu-id="86d54-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d54-107">语法</span><span class="sxs-lookup"><span data-stu-id="86d54-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86d54-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="86d54-108">Attributes and Elements</span></span>  
 <span data-ttu-id="86d54-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="86d54-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86d54-110">属性</span><span class="sxs-lookup"><span data-stu-id="86d54-110">Attributes</span></span>  
  
|<span data-ttu-id="86d54-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="86d54-111">Attribute</span></span>|<span data-ttu-id="86d54-112">说明</span><span class="sxs-lookup"><span data-stu-id="86d54-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="86d54-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="86d54-113">Required attribute.</span></span> <span data-ttu-id="86d54-114">指定作为进程中默认应用程序域的应用程序域管理器的类型的名称（包括命名空间）。</span><span class="sxs-lookup"><span data-stu-id="86d54-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86d54-115">子元素</span><span class="sxs-lookup"><span data-stu-id="86d54-115">Child Elements</span></span>  
 <span data-ttu-id="86d54-116">无。</span><span class="sxs-lookup"><span data-stu-id="86d54-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86d54-117">父元素</span><span class="sxs-lookup"><span data-stu-id="86d54-117">Parent Elements</span></span>  
  
|<span data-ttu-id="86d54-118">元素</span><span class="sxs-lookup"><span data-stu-id="86d54-118">Element</span></span>|<span data-ttu-id="86d54-119">说明</span><span class="sxs-lookup"><span data-stu-id="86d54-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="86d54-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="86d54-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="86d54-121">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="86d54-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86d54-122">备注</span><span class="sxs-lookup"><span data-stu-id="86d54-122">Remarks</span></span>  
 <span data-ttu-id="86d54-123">要指定应用程序域管理器的类型，必须同时指定此元素和[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="86d54-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="86d54-124">如果未指定其中任一元素，则忽略另一个元素。</span><span class="sxs-lookup"><span data-stu-id="86d54-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="86d54-125">加载默认应用程序域时，<xref:System.TypeLoadException>如果[\<应用域管理器组件>](appdomainmanagerassembly-element.md)元素指定的程序集中不存在指定的类型，则引发该类型;进程无法启动。</span><span class="sxs-lookup"><span data-stu-id="86d54-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="86d54-126">当您为默认应用程序域指定应用程序域管理器类型时，从默认应用程序域创建的其他应用程序域将继承应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="86d54-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="86d54-127">使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性为新的应用程序域指定不同的应用程序域管理器类型。</span><span class="sxs-lookup"><span data-stu-id="86d54-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="86d54-128">指定应用程序域管理器类型需要应用程序具有完全信任。</span><span class="sxs-lookup"><span data-stu-id="86d54-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="86d54-129">（例如，在桌面上运行的应用程序具有完全信任。如果应用程序没有完全信任，则引发 。 <xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="86d54-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="86d54-130">类型和命名空间的格式与用于属性的<xref:System.Type.FullName%2A?displayProperty=nameWithType>格式相同。</span><span class="sxs-lookup"><span data-stu-id="86d54-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="86d54-131">此配置元素仅在 .NET 框架 4 和更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="86d54-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d54-132">示例</span><span class="sxs-lookup"><span data-stu-id="86d54-132">Example</span></span>  
 <span data-ttu-id="86d54-133">下面的示例演示如何指定进程默认应用程序域的应用程序域管理器是程序集中`MyMgr``AdMgrExample`的类型。</span><span class="sxs-lookup"><span data-stu-id="86d54-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86d54-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86d54-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="86d54-135">\<应用程序域管理器程序集>元素</span><span class="sxs-lookup"><span data-stu-id="86d54-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="86d54-136">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="86d54-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="86d54-137">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="86d54-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="86d54-138">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="86d54-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
