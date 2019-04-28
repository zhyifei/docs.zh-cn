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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704760"
---
# <a name="developmentmode-element"></a><span data-ttu-id="9897b-102">\<developmentMode > 元素</span><span class="sxs-lookup"><span data-stu-id="9897b-102">\<developmentMode> Element</span></span>
<span data-ttu-id="9897b-103">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="9897b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9897b-104">\<configuration></span></span>  
<span data-ttu-id="9897b-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="9897b-105">\<runtime></span></span>  
<span data-ttu-id="9897b-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="9897b-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9897b-107">语法</span><span class="sxs-lookup"><span data-stu-id="9897b-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9897b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9897b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9897b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9897b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9897b-110">特性</span><span class="sxs-lookup"><span data-stu-id="9897b-110">Attributes</span></span>  
  
|<span data-ttu-id="9897b-111">特性</span><span class="sxs-lookup"><span data-stu-id="9897b-111">Attribute</span></span>|<span data-ttu-id="9897b-112">描述</span><span class="sxs-lookup"><span data-stu-id="9897b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9897b-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="9897b-113">**developerInstallation**</span></span>|<span data-ttu-id="9897b-114">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="9897b-115">developerInstallation 属性</span><span class="sxs-lookup"><span data-stu-id="9897b-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="9897b-116">“值”</span><span class="sxs-lookup"><span data-stu-id="9897b-116">Value</span></span>|<span data-ttu-id="9897b-117">描述</span><span class="sxs-lookup"><span data-stu-id="9897b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9897b-118">**true**</span><span class="sxs-lookup"><span data-stu-id="9897b-118">**true**</span></span>|<span data-ttu-id="9897b-119">搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="9897b-120">**false**</span><span class="sxs-lookup"><span data-stu-id="9897b-120">**false**</span></span>|<span data-ttu-id="9897b-121">不会搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="9897b-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="9897b-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9897b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9897b-123">Child Elements</span></span>  
 <span data-ttu-id="9897b-124">无。</span><span class="sxs-lookup"><span data-stu-id="9897b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9897b-125">父元素</span><span class="sxs-lookup"><span data-stu-id="9897b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9897b-126">元素</span><span class="sxs-lookup"><span data-stu-id="9897b-126">Element</span></span>|<span data-ttu-id="9897b-127">描述</span><span class="sxs-lookup"><span data-stu-id="9897b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9897b-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9897b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9897b-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="9897b-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9897b-130">备注</span><span class="sxs-lookup"><span data-stu-id="9897b-130">Remarks</span></span>  
 <span data-ttu-id="9897b-131">仅在开发期间使用此设置。</span><span class="sxs-lookup"><span data-stu-id="9897b-131">Use this setting only at development time.</span></span> <span data-ttu-id="9897b-132">在运行时不会检查位于 devpath 查找程序集强名称的程序集上的版本。</span><span class="sxs-lookup"><span data-stu-id="9897b-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="9897b-133">它只需使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9897b-134">示例</span><span class="sxs-lookup"><span data-stu-id="9897b-134">Example</span></span>  
 <span data-ttu-id="9897b-135">下面的示例演示如何会导致运行时用于搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="9897b-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9897b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="9897b-136">See also</span></span>

- [<span data-ttu-id="9897b-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="9897b-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9897b-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9897b-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9897b-139">如何：通过使用 devpath 查找程序集查找程序集</span><span class="sxs-lookup"><span data-stu-id="9897b-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
