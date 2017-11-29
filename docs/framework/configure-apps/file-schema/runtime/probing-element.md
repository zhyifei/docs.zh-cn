---
title: "&lt;探测&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7dd829fbbfbaa6f26b59e26d5a8b1d2b36593f57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="f9f71-102">&lt;探测&gt;元素</span><span class="sxs-lookup"><span data-stu-id="f9f71-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="f9f71-103">指定应用程序基公共语言运行时，在加载程序集时要搜索子目录。</span><span class="sxs-lookup"><span data-stu-id="f9f71-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="f9f71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f9f71-104">\<configuration></span></span>  
<span data-ttu-id="f9f71-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="f9f71-105">\<runtime></span></span>  
<span data-ttu-id="f9f71-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="f9f71-106">\<assemblyBinding></span></span>  
<span data-ttu-id="f9f71-107">\<探测 ></span><span class="sxs-lookup"><span data-stu-id="f9f71-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f71-108">语法</span><span class="sxs-lookup"><span data-stu-id="f9f71-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9f71-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f9f71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f9f71-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f9f71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9f71-111">特性</span><span class="sxs-lookup"><span data-stu-id="f9f71-111">Attributes</span></span>  
  
|<span data-ttu-id="f9f71-112">特性</span><span class="sxs-lookup"><span data-stu-id="f9f71-112">Attribute</span></span>|<span data-ttu-id="f9f71-113">描述</span><span class="sxs-lookup"><span data-stu-id="f9f71-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="f9f71-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f9f71-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9f71-115">指定可能包含程序集的应用程序的基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="f9f71-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="f9f71-116">分隔每个以分号的子目录。</span><span class="sxs-lookup"><span data-stu-id="f9f71-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9f71-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f9f71-117">Child Elements</span></span>  
 <span data-ttu-id="f9f71-118">无。</span><span class="sxs-lookup"><span data-stu-id="f9f71-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9f71-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f9f71-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f9f71-120">元素</span><span class="sxs-lookup"><span data-stu-id="f9f71-120">Element</span></span>|<span data-ttu-id="f9f71-121">描述</span><span class="sxs-lookup"><span data-stu-id="f9f71-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f9f71-122">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="f9f71-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f9f71-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f9f71-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f9f71-124">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="f9f71-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f9f71-125">示例</span><span class="sxs-lookup"><span data-stu-id="f9f71-125">Example</span></span>  
 <span data-ttu-id="f9f71-126">下面的示例演示如何指定运行时应搜索程序集的应用程序基子目录。</span><span class="sxs-lookup"><span data-stu-id="f9f71-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9f71-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9f71-127">See Also</span></span>  
 [<span data-ttu-id="f9f71-128">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="f9f71-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f9f71-129">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f9f71-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f9f71-130">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="f9f71-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="f9f71-131">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="f9f71-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
