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
ms.openlocfilehash: fdf840035150f08c894c984213af9a0abe6e95af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192047"
---
# <a name="developmentmode-element"></a><span data-ttu-id="f6f23-102">\<developmentMode > 元素</span><span class="sxs-lookup"><span data-stu-id="f6f23-102">\<developmentMode> Element</span></span>
<span data-ttu-id="f6f23-103">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="f6f23-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f6f23-104">\<configuration></span></span>  
<span data-ttu-id="f6f23-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="f6f23-105">\<runtime></span></span>  
<span data-ttu-id="f6f23-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="f6f23-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f23-107">语法</span><span class="sxs-lookup"><span data-stu-id="f6f23-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6f23-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f6f23-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f6f23-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f6f23-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6f23-110">特性</span><span class="sxs-lookup"><span data-stu-id="f6f23-110">Attributes</span></span>  
  
|<span data-ttu-id="f6f23-111">特性</span><span class="sxs-lookup"><span data-stu-id="f6f23-111">Attribute</span></span>|<span data-ttu-id="f6f23-112">描述</span><span class="sxs-lookup"><span data-stu-id="f6f23-112">Description</span></span>|  
|---------------|-----------------|  
|**<span data-ttu-id="f6f23-113">developerInstallation</span><span class="sxs-lookup"><span data-stu-id="f6f23-113">developerInstallation</span></span>**|<span data-ttu-id="f6f23-114">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="f6f23-115">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="f6f23-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="f6f23-116">“值”</span><span class="sxs-lookup"><span data-stu-id="f6f23-116">Value</span></span>|<span data-ttu-id="f6f23-117">描述</span><span class="sxs-lookup"><span data-stu-id="f6f23-117">Description</span></span>|  
|-----------|-----------------|  
|**<span data-ttu-id="f6f23-118">true</span><span class="sxs-lookup"><span data-stu-id="f6f23-118">true</span></span>**|<span data-ttu-id="f6f23-119">搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|**<span data-ttu-id="f6f23-120">False</span><span class="sxs-lookup"><span data-stu-id="f6f23-120">false</span></span>**|<span data-ttu-id="f6f23-121">不会搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="f6f23-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="f6f23-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6f23-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f6f23-123">Child Elements</span></span>  
 <span data-ttu-id="f6f23-124">无。</span><span class="sxs-lookup"><span data-stu-id="f6f23-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6f23-125">父元素</span><span class="sxs-lookup"><span data-stu-id="f6f23-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f6f23-126">元素</span><span class="sxs-lookup"><span data-stu-id="f6f23-126">Element</span></span>|<span data-ttu-id="f6f23-127">描述</span><span class="sxs-lookup"><span data-stu-id="f6f23-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f6f23-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f6f23-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f6f23-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="f6f23-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6f23-130">备注</span><span class="sxs-lookup"><span data-stu-id="f6f23-130">Remarks</span></span>  
 <span data-ttu-id="f6f23-131">仅在开发期间使用此设置。</span><span class="sxs-lookup"><span data-stu-id="f6f23-131">Use this setting only at development time.</span></span> <span data-ttu-id="f6f23-132">在运行时不会检查位于 devpath 查找程序集强名称的程序集上的版本。</span><span class="sxs-lookup"><span data-stu-id="f6f23-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="f6f23-133">它只需使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f23-134">示例</span><span class="sxs-lookup"><span data-stu-id="f6f23-134">Example</span></span>  
 <span data-ttu-id="f6f23-135">下面的示例演示如何会导致运行时用于搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6f23-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6f23-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6f23-136">See also</span></span>

- [<span data-ttu-id="f6f23-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="f6f23-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f6f23-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f6f23-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f6f23-139">如何：使用 DEVPATH 查找程序集</span><span class="sxs-lookup"><span data-stu-id="f6f23-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
