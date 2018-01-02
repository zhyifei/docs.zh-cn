---
title: "&lt;developmentMode&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a77f93a0dff198821509c2c26f67caa137073ced
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdevelopmentmodegt-element"></a><span data-ttu-id="6e749-102">&lt;developmentMode&gt;元素</span><span class="sxs-lookup"><span data-stu-id="6e749-102">&lt;developmentMode&gt; Element</span></span>
<span data-ttu-id="6e749-103">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="6e749-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6e749-104">\<configuration></span></span>  
<span data-ttu-id="6e749-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="6e749-105">\<runtime></span></span>  
<span data-ttu-id="6e749-106">\<developmentMode ></span><span class="sxs-lookup"><span data-stu-id="6e749-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e749-107">语法</span><span class="sxs-lookup"><span data-stu-id="6e749-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e749-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e749-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e749-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6e749-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e749-110">特性</span><span class="sxs-lookup"><span data-stu-id="6e749-110">Attributes</span></span>  
  
|<span data-ttu-id="6e749-111">特性</span><span class="sxs-lookup"><span data-stu-id="6e749-111">Attribute</span></span>|<span data-ttu-id="6e749-112">描述</span><span class="sxs-lookup"><span data-stu-id="6e749-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e749-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="6e749-113">**developerInstallation**</span></span>|<span data-ttu-id="6e749-114">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="6e749-115">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="6e749-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="6e749-116">值</span><span class="sxs-lookup"><span data-stu-id="6e749-116">Value</span></span>|<span data-ttu-id="6e749-117">描述</span><span class="sxs-lookup"><span data-stu-id="6e749-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e749-118">**true**</span><span class="sxs-lookup"><span data-stu-id="6e749-118">**true**</span></span>|<span data-ttu-id="6e749-119">搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="6e749-120">**false**</span><span class="sxs-lookup"><span data-stu-id="6e749-120">**false**</span></span>|<span data-ttu-id="6e749-121">不会搜索 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="6e749-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="6e749-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e749-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6e749-123">Child Elements</span></span>  
 <span data-ttu-id="6e749-124">无。</span><span class="sxs-lookup"><span data-stu-id="6e749-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e749-125">父元素</span><span class="sxs-lookup"><span data-stu-id="6e749-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6e749-126">元素</span><span class="sxs-lookup"><span data-stu-id="6e749-126">Element</span></span>|<span data-ttu-id="6e749-127">说明</span><span class="sxs-lookup"><span data-stu-id="6e749-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e749-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6e749-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6e749-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="6e749-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e749-130">备注</span><span class="sxs-lookup"><span data-stu-id="6e749-130">Remarks</span></span>  
 <span data-ttu-id="6e749-131">仅在开发期间使用此设置。</span><span class="sxs-lookup"><span data-stu-id="6e749-131">Use this setting only at development time.</span></span> <span data-ttu-id="6e749-132">运行时不会检查上 DEVPATH 中找到的具有强名称的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="6e749-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="6e749-133">它只需使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e749-134">示例</span><span class="sxs-lookup"><span data-stu-id="6e749-134">Example</span></span>  
 <span data-ttu-id="6e749-135">下面的示例演示如何使运行时搜索 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="6e749-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e749-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e749-136">See Also</span></span>  
 [<span data-ttu-id="6e749-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="6e749-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6e749-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6e749-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6e749-139">如何：使用 DEVPATH 查找程序集</span><span class="sxs-lookup"><span data-stu-id="6e749-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
