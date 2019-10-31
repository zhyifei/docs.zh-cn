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
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117629"
---
# <a name="developmentmode-element"></a><span data-ttu-id="a0d4e-102">\<developmentMode > 元素</span><span class="sxs-lookup"><span data-stu-id="a0d4e-102">\<developmentMode> Element</span></span>
<span data-ttu-id="a0d4e-103">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="a0d4e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0d4e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0d4e-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="a0d4e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a0d4e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode >**</span><span class="sxs-lookup"><span data-stu-id="a0d4e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d4e-107">语法</span><span class="sxs-lookup"><span data-stu-id="a0d4e-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0d4e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0d4e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0d4e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0d4e-110">特性</span><span class="sxs-lookup"><span data-stu-id="a0d4e-110">Attributes</span></span>  
  
|<span data-ttu-id="a0d4e-111">特性</span><span class="sxs-lookup"><span data-stu-id="a0d4e-111">Attribute</span></span>|<span data-ttu-id="a0d4e-112">描述</span><span class="sxs-lookup"><span data-stu-id="a0d4e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0d4e-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="a0d4e-113">**developerInstallation**</span></span>|<span data-ttu-id="a0d4e-114">指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="a0d4e-115">developerInstallation 特性</span><span class="sxs-lookup"><span data-stu-id="a0d4e-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="a0d4e-116">“值”</span><span class="sxs-lookup"><span data-stu-id="a0d4e-116">Value</span></span>|<span data-ttu-id="a0d4e-117">描述</span><span class="sxs-lookup"><span data-stu-id="a0d4e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0d4e-118">**true**</span><span class="sxs-lookup"><span data-stu-id="a0d4e-118">**true**</span></span>|<span data-ttu-id="a0d4e-119">在由 DEVPATH 环境变量指定的目录中搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="a0d4e-120">**false**</span><span class="sxs-lookup"><span data-stu-id="a0d4e-120">**false**</span></span>|<span data-ttu-id="a0d4e-121">不搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="a0d4e-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="a0d4e-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0d4e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a0d4e-123">Child Elements</span></span>  
 <span data-ttu-id="a0d4e-124">无。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0d4e-125">父元素</span><span class="sxs-lookup"><span data-stu-id="a0d4e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a0d4e-126">元素</span><span class="sxs-lookup"><span data-stu-id="a0d4e-126">Element</span></span>|<span data-ttu-id="a0d4e-127">描述</span><span class="sxs-lookup"><span data-stu-id="a0d4e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a0d4e-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a0d4e-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0d4e-130">备注</span><span class="sxs-lookup"><span data-stu-id="a0d4e-130">Remarks</span></span>  
 <span data-ttu-id="a0d4e-131">仅在开发时使用此设置。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-131">Use this setting only at development time.</span></span> <span data-ttu-id="a0d4e-132">运行时不检查在 DEVPATH 中找到的具有强名称的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="a0d4e-133">它只使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0d4e-134">示例</span><span class="sxs-lookup"><span data-stu-id="a0d4e-134">Example</span></span>  
 <span data-ttu-id="a0d4e-135">下面的示例演示如何使运行时在由 DEVPATH 环境变量指定的目录中搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="a0d4e-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0d4e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d4e-136">See also</span></span>

- [<span data-ttu-id="a0d4e-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a0d4e-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a0d4e-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a0d4e-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a0d4e-139">如何：使用 DEVPATH 查找程序集</span><span class="sxs-lookup"><span data-stu-id="a0d4e-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
