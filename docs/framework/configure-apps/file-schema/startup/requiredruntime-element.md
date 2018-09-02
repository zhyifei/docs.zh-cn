---
title: '&lt;requiredRuntime&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ac1e1f7bc36d8d2b12b99de2794bb0ba31ddbd7a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398727"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="ba6e9-102">&lt;requiredRuntime&gt;元素</span><span class="sxs-lookup"><span data-stu-id="ba6e9-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="ba6e9-103">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ba6e9-104">此元素已弃用，应不再使用。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="ba6e9-105">[ `supportedRuntime` ](supportedruntime-element.md)元素应改为使用。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="ba6e9-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba6e9-106">\<configuration></span></span>  
<span data-ttu-id="ba6e9-107">\<启动 ></span><span class="sxs-lookup"><span data-stu-id="ba6e9-107">\<startup></span></span>  
<span data-ttu-id="ba6e9-108">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="ba6e9-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba6e9-109">语法</span><span class="sxs-lookup"><span data-stu-id="ba6e9-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba6e9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba6e9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba6e9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba6e9-112">特性</span><span class="sxs-lookup"><span data-stu-id="ba6e9-112">Attributes</span></span>  
  
|<span data-ttu-id="ba6e9-113">特性</span><span class="sxs-lookup"><span data-stu-id="ba6e9-113">Attribute</span></span>|<span data-ttu-id="ba6e9-114">描述</span><span class="sxs-lookup"><span data-stu-id="ba6e9-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="ba6e9-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba6e9-116">一个字符串值，该值指定此应用程序支持的.NET framework 版本。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="ba6e9-117">字符串值必须与.NET Framework 安装根目录下找到的目录名称匹配。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="ba6e9-118">未分析的字符串值的内容。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="ba6e9-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba6e9-120">指定是否在运行时启动代码搜索注册表，以确定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="ba6e9-121">安全模式属性</span><span class="sxs-lookup"><span data-stu-id="ba6e9-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="ba6e9-122">“值”</span><span class="sxs-lookup"><span data-stu-id="ba6e9-122">Value</span></span>|<span data-ttu-id="ba6e9-123">描述</span><span class="sxs-lookup"><span data-stu-id="ba6e9-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ba6e9-124">在注册表中查找运行时启动代码。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="ba6e9-125">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="ba6e9-126">运行时启动代码不会在注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba6e9-127">子元素</span><span class="sxs-lookup"><span data-stu-id="ba6e9-127">Child Elements</span></span>  
 <span data-ttu-id="ba6e9-128">无。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba6e9-129">父元素</span><span class="sxs-lookup"><span data-stu-id="ba6e9-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ba6e9-130">元素</span><span class="sxs-lookup"><span data-stu-id="ba6e9-130">Element</span></span>|<span data-ttu-id="ba6e9-131">描述</span><span class="sxs-lookup"><span data-stu-id="ba6e9-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba6e9-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="ba6e9-133">包含`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba6e9-134">备注</span><span class="sxs-lookup"><span data-stu-id="ba6e9-134">Remarks</span></span>  
 <span data-ttu-id="ba6e9-135">仅支持 1.0 版的运行时生成的应用程序必须使用`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="ba6e9-136">构建使用 1.1 版或更高版本的运行时版本的应用程序必须使用`<supportedRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba6e9-137">如果您使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数以指定配置文件，则必须使用`<requiredRuntime>`所有版本的运行时的元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="ba6e9-138">`<supportedRuntime>`使用时，将忽略元素[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="ba6e9-139">`version`属性字符串必须匹配指定版本的.NET framework 的安装文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="ba6e9-140">此字符串不解释。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-140">This string is not interpreted.</span></span> <span data-ttu-id="ba6e9-141">如果运行时启动代码没有找到匹配的文件夹，则不会加载运行时;启动代码显示了一条错误消息并退出。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba6e9-142">Microsoft Internet Explorer 中承载的应用程序的启动代码将忽略`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba6e9-143">示例</span><span class="sxs-lookup"><span data-stu-id="ba6e9-143">Example</span></span>  
 <span data-ttu-id="ba6e9-144">下面的示例演示如何在配置文件中指定的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="ba6e9-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba6e9-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba6e9-145">See Also</span></span>  
 [<span data-ttu-id="ba6e9-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="ba6e9-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="ba6e9-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ba6e9-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ba6e9-148">\<PaveOver> 指定要使用的运行时版本</span><span class="sxs-lookup"><span data-stu-id="ba6e9-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
