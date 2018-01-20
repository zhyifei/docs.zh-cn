---
title: "&lt;requiredRuntime&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2e864eec2ddf51d5cc88110654f6c23f146938d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="733ce-102">&lt;requiredRuntime&gt;元素</span><span class="sxs-lookup"><span data-stu-id="733ce-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="733ce-103">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="733ce-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="733ce-104">此元素已弃用，并应不再使用。</span><span class="sxs-lookup"><span data-stu-id="733ce-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="733ce-105">[ `supportedRuntime` ](supportedruntime-element.md)元素应改为使用。</span><span class="sxs-lookup"><span data-stu-id="733ce-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="733ce-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="733ce-106">\<configuration></span></span>  
<span data-ttu-id="733ce-107">\<startup></span><span class="sxs-lookup"><span data-stu-id="733ce-107">\<startup></span></span>  
<span data-ttu-id="733ce-108">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="733ce-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="733ce-109">语法</span><span class="sxs-lookup"><span data-stu-id="733ce-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="733ce-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="733ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="733ce-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="733ce-112">特性</span><span class="sxs-lookup"><span data-stu-id="733ce-112">Attributes</span></span>  
  
|<span data-ttu-id="733ce-113">特性</span><span class="sxs-lookup"><span data-stu-id="733ce-113">Attribute</span></span>|<span data-ttu-id="733ce-114">描述</span><span class="sxs-lookup"><span data-stu-id="733ce-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="733ce-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="733ce-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="733ce-116">一个字符串值，指定此应用程序支持的.NET framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="733ce-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="733ce-117">字符串值必须与在.NET Framework 安装根目录下找到的目录名称匹配。</span><span class="sxs-lookup"><span data-stu-id="733ce-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="733ce-118">未分析的字符串值的内容。</span><span class="sxs-lookup"><span data-stu-id="733ce-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="733ce-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="733ce-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="733ce-120">指定运行时启动代码是否搜索注册表项以确定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="733ce-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="733ce-121">安全模式属性</span><span class="sxs-lookup"><span data-stu-id="733ce-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="733ce-122">“值”</span><span class="sxs-lookup"><span data-stu-id="733ce-122">Value</span></span>|<span data-ttu-id="733ce-123">描述</span><span class="sxs-lookup"><span data-stu-id="733ce-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="733ce-124">在注册表中查找运行时启动代码。</span><span class="sxs-lookup"><span data-stu-id="733ce-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="733ce-125">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="733ce-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="733ce-126">运行时启动代码不会在注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="733ce-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="733ce-127">子元素</span><span class="sxs-lookup"><span data-stu-id="733ce-127">Child Elements</span></span>  
 <span data-ttu-id="733ce-128">无。</span><span class="sxs-lookup"><span data-stu-id="733ce-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="733ce-129">父元素</span><span class="sxs-lookup"><span data-stu-id="733ce-129">Parent Elements</span></span>  
  
|<span data-ttu-id="733ce-130">元素</span><span class="sxs-lookup"><span data-stu-id="733ce-130">Element</span></span>|<span data-ttu-id="733ce-131">描述</span><span class="sxs-lookup"><span data-stu-id="733ce-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="733ce-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="733ce-133">包含`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="733ce-134">备注</span><span class="sxs-lookup"><span data-stu-id="733ce-134">Remarks</span></span>  
 <span data-ttu-id="733ce-135">为支持仅运行时 1.0 版而生成的应用程序必须使用`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="733ce-136">使用版本 1.1 或更高版本的运行时生成的应用程序必须使用`<supportedRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="733ce-137">如果你使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数来指定配置文件，必须使用`<requiredRuntime>`所有的运行时版本的元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="733ce-138">`<supportedRuntime>`元素将被忽略，当你使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。</span><span class="sxs-lookup"><span data-stu-id="733ce-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="733ce-139">`version`属性字符串必须匹配的指定版本的.NET framework 的安装文件夹名。</span><span class="sxs-lookup"><span data-stu-id="733ce-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="733ce-140">此字符串不会被解释。</span><span class="sxs-lookup"><span data-stu-id="733ce-140">This string is not interpreted.</span></span> <span data-ttu-id="733ce-141">如果运行时启动代码未找到匹配的文件夹，则不会加载运行时;启动代码将显示一条错误消息并退出。</span><span class="sxs-lookup"><span data-stu-id="733ce-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="733ce-142">Microsoft Internet Explorer 中承载的应用程序的启动代码将忽略`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="733ce-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="733ce-143">示例</span><span class="sxs-lookup"><span data-stu-id="733ce-143">Example</span></span>  
 <span data-ttu-id="733ce-144">下面的示例演示如何在配置文件中指定的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="733ce-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="733ce-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="733ce-145">See Also</span></span>  
 [<span data-ttu-id="733ce-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="733ce-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="733ce-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="733ce-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="733ce-148">\<PaveOver> 指定要使用的运行时版本</span><span class="sxs-lookup"><span data-stu-id="733ce-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
