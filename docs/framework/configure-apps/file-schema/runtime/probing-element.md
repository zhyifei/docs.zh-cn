---
title: <probing> 元素
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
ms.openlocfilehash: ae789e99a1306102c67f2252760e215989132406
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971627"
---
# <a name="probing-element"></a><span data-ttu-id="ee259-102">\<探测 > 元素</span><span class="sxs-lookup"><span data-stu-id="ee259-102">\<probing> Element</span></span>
<span data-ttu-id="ee259-103">指定加载程序集时要搜索的公共语言运行时的应用程序基子目录。</span><span class="sxs-lookup"><span data-stu-id="ee259-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="ee259-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee259-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ee259-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee259-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ee259-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="ee259-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="ee259-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<探测 >**</span><span class="sxs-lookup"><span data-stu-id="ee259-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee259-108">语法</span><span class="sxs-lookup"><span data-stu-id="ee259-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee259-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee259-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee259-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee259-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee259-111">特性</span><span class="sxs-lookup"><span data-stu-id="ee259-111">Attributes</span></span>  
  
|<span data-ttu-id="ee259-112">特性</span><span class="sxs-lookup"><span data-stu-id="ee259-112">Attribute</span></span>|<span data-ttu-id="ee259-113">描述</span><span class="sxs-lookup"><span data-stu-id="ee259-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="ee259-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ee259-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee259-115">指定可能包含程序集的应用程序基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="ee259-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="ee259-116">用分号分隔每个子目录。</span><span class="sxs-lookup"><span data-stu-id="ee259-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee259-117">子元素</span><span class="sxs-lookup"><span data-stu-id="ee259-117">Child Elements</span></span>  

<span data-ttu-id="ee259-118">无。</span><span class="sxs-lookup"><span data-stu-id="ee259-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee259-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ee259-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee259-120">元素</span><span class="sxs-lookup"><span data-stu-id="ee259-120">Element</span></span>|<span data-ttu-id="ee259-121">描述</span><span class="sxs-lookup"><span data-stu-id="ee259-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="ee259-122">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="ee259-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="ee259-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ee259-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ee259-124">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="ee259-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ee259-125">示例</span><span class="sxs-lookup"><span data-stu-id="ee259-125">Example</span></span>  
 <span data-ttu-id="ee259-126">下面的示例演示如何指定运行时应搜索程序集的应用程序基子目录。</span><span class="sxs-lookup"><span data-stu-id="ee259-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee259-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee259-127">See also</span></span>

- [<span data-ttu-id="ee259-128">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ee259-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="ee259-129">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ee259-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="ee259-130">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="ee259-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="ee259-131">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="ee259-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
