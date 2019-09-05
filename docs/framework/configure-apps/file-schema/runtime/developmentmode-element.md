---
title: <developmentMode> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0253c3ced52b575097fe5d18abb8ce188c0164fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252686"
---
# <a name="developmentmode-element"></a><span data-ttu-id="b916a-102">\<developmentMode > 元素</span><span class="sxs-lookup"><span data-stu-id="b916a-102">\<developmentMode> Element</span></span>
<span data-ttu-id="b916a-103">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="b916a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b916a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b916a-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b916a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b916a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode>**</span><span class="sxs-lookup"><span data-stu-id="b916a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b916a-107">语法</span><span class="sxs-lookup"><span data-stu-id="b916a-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b916a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b916a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b916a-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b916a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b916a-110">特性</span><span class="sxs-lookup"><span data-stu-id="b916a-110">Attributes</span></span>  
  
|<span data-ttu-id="b916a-111">特性</span><span class="sxs-lookup"><span data-stu-id="b916a-111">Attribute</span></span>|<span data-ttu-id="b916a-112">描述</span><span class="sxs-lookup"><span data-stu-id="b916a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b916a-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="b916a-113">**developerInstallation**</span></span>|<span data-ttu-id="b916a-114">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="b916a-115">developerInstallation 特性</span><span class="sxs-lookup"><span data-stu-id="b916a-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="b916a-116">值</span><span class="sxs-lookup"><span data-stu-id="b916a-116">Value</span></span>|<span data-ttu-id="b916a-117">描述</span><span class="sxs-lookup"><span data-stu-id="b916a-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b916a-118">**true**</span><span class="sxs-lookup"><span data-stu-id="b916a-118">**true**</span></span>|<span data-ttu-id="b916a-119">在由 DEVPATH 环境变量指定的目录中搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="b916a-120">**false**</span><span class="sxs-lookup"><span data-stu-id="b916a-120">**false**</span></span>|<span data-ttu-id="b916a-121">不搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="b916a-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="b916a-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b916a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b916a-123">Child Elements</span></span>  
 <span data-ttu-id="b916a-124">无。</span><span class="sxs-lookup"><span data-stu-id="b916a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b916a-125">父元素</span><span class="sxs-lookup"><span data-stu-id="b916a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b916a-126">元素</span><span class="sxs-lookup"><span data-stu-id="b916a-126">Element</span></span>|<span data-ttu-id="b916a-127">描述</span><span class="sxs-lookup"><span data-stu-id="b916a-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b916a-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b916a-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b916a-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="b916a-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b916a-130">备注</span><span class="sxs-lookup"><span data-stu-id="b916a-130">Remarks</span></span>  
 <span data-ttu-id="b916a-131">仅在开发时使用此设置。</span><span class="sxs-lookup"><span data-stu-id="b916a-131">Use this setting only at development time.</span></span> <span data-ttu-id="b916a-132">运行时不检查在 DEVPATH 中找到的具有强名称的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="b916a-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="b916a-133">它只使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b916a-134">示例</span><span class="sxs-lookup"><span data-stu-id="b916a-134">Example</span></span>  
 <span data-ttu-id="b916a-135">下面的示例演示如何使运行时在由 DEVPATH 环境变量指定的目录中搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="b916a-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b916a-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="b916a-136">See also</span></span>

- [<span data-ttu-id="b916a-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="b916a-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b916a-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b916a-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b916a-139">如何：使用 DEVPATH 查找程序集</span><span class="sxs-lookup"><span data-stu-id="b916a-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
