---
title: '&lt;探测&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b9be3050da21c0a99931ca70cf990b0b8bf1fe
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612294"
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="cc2fd-102">&lt;探测&gt;元素</span><span class="sxs-lookup"><span data-stu-id="cc2fd-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="cc2fd-103">指定公共语言运行时在加载程序集时要搜索的应用程序基子目录。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="cc2fd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cc2fd-104">\<configuration></span></span>  
<span data-ttu-id="cc2fd-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="cc2fd-105">\<runtime></span></span>  
<span data-ttu-id="cc2fd-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="cc2fd-106">\<assemblyBinding></span></span>  
<span data-ttu-id="cc2fd-107">\<探测 ></span><span class="sxs-lookup"><span data-stu-id="cc2fd-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2fd-108">语法</span><span class="sxs-lookup"><span data-stu-id="cc2fd-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc2fd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc2fd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc2fd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc2fd-111">特性</span><span class="sxs-lookup"><span data-stu-id="cc2fd-111">Attributes</span></span>  
  
|<span data-ttu-id="cc2fd-112">特性</span><span class="sxs-lookup"><span data-stu-id="cc2fd-112">Attribute</span></span>|<span data-ttu-id="cc2fd-113">描述</span><span class="sxs-lookup"><span data-stu-id="cc2fd-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="cc2fd-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cc2fd-115">指定可能包含程序集的应用程序的基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="cc2fd-116">分隔每个子目录以分号结尾。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc2fd-117">子元素</span><span class="sxs-lookup"><span data-stu-id="cc2fd-117">Child Elements</span></span>  
 <span data-ttu-id="cc2fd-118">无。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc2fd-119">父元素</span><span class="sxs-lookup"><span data-stu-id="cc2fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cc2fd-120">元素</span><span class="sxs-lookup"><span data-stu-id="cc2fd-120">Element</span></span>|<span data-ttu-id="cc2fd-121">描述</span><span class="sxs-lookup"><span data-stu-id="cc2fd-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="cc2fd-122">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="cc2fd-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cc2fd-124">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cc2fd-125">示例</span><span class="sxs-lookup"><span data-stu-id="cc2fd-125">Example</span></span>  
 <span data-ttu-id="cc2fd-126">下面的示例演示如何指定运行时应搜索程序集的应用程序基子目录。</span><span class="sxs-lookup"><span data-stu-id="cc2fd-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc2fd-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc2fd-127">See Also</span></span>  
- [<span data-ttu-id="cc2fd-128">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="cc2fd-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="cc2fd-129">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="cc2fd-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="cc2fd-130">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="cc2fd-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
- [<span data-ttu-id="cc2fd-131">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="cc2fd-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
