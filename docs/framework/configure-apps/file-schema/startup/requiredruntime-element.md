---
title: <requiredRuntime> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697486"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="f5973-102">\<requiredRuntime > 元素</span><span class="sxs-lookup"><span data-stu-id="f5973-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="f5973-103">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="f5973-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="f5973-104">此元素已弃用，不应再使用。</span><span class="sxs-lookup"><span data-stu-id="f5973-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="f5973-105">应改为使用[`supportedRuntime`](supportedruntime-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="f5973-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f5973-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f5973-107">&nbsp; @ no__t-1[ **\<startup >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5973-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="f5973-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="f5973-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f5973-109">语法</span><span class="sxs-lookup"><span data-stu-id="f5973-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5973-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f5973-110">Attributes and elements</span></span>

<span data-ttu-id="f5973-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5973-112">特性</span><span class="sxs-lookup"><span data-stu-id="f5973-112">Attributes</span></span>

|<span data-ttu-id="f5973-113">特性</span><span class="sxs-lookup"><span data-stu-id="f5973-113">Attribute</span></span>|<span data-ttu-id="f5973-114">描述</span><span class="sxs-lookup"><span data-stu-id="f5973-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="f5973-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="f5973-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f5973-116">一个字符串值，该值指定此应用程序支持的 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="f5973-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="f5973-117">字符串值必须与 .NET Framework 安装根下的目录名称匹配。</span><span class="sxs-lookup"><span data-stu-id="f5973-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="f5973-118">不分析字符串值的内容。</span><span class="sxs-lookup"><span data-stu-id="f5973-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="f5973-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="f5973-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f5973-120">指定运行时启动代码是否在注册表中搜索以确定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f5973-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="f5973-121">安全模式特性</span><span class="sxs-lookup"><span data-stu-id="f5973-121">safemode attribute</span></span>

|<span data-ttu-id="f5973-122">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="f5973-122">Value</span></span>|<span data-ttu-id="f5973-123">描述</span><span class="sxs-lookup"><span data-stu-id="f5973-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f5973-124">运行时启动代码在注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="f5973-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="f5973-125">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="f5973-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="f5973-126">运行时启动代码不会在注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="f5973-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f5973-127">子元素</span><span class="sxs-lookup"><span data-stu-id="f5973-127">Child elements</span></span>

<span data-ttu-id="f5973-128">无。</span><span class="sxs-lookup"><span data-stu-id="f5973-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5973-129">父元素</span><span class="sxs-lookup"><span data-stu-id="f5973-129">Parent elements</span></span>

|<span data-ttu-id="f5973-130">元素</span><span class="sxs-lookup"><span data-stu-id="f5973-130">Element</span></span>|<span data-ttu-id="f5973-131">描述</span><span class="sxs-lookup"><span data-stu-id="f5973-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f5973-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="f5973-133">`<requiredRuntime>`包含元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f5973-134">备注</span><span class="sxs-lookup"><span data-stu-id="f5973-134">Remarks</span></span>
 <span data-ttu-id="f5973-135">构建为仅支持1.0 版运行时的应用程序必须使用 `<requiredRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="f5973-136">使用版本1.1 或更高版本的运行时生成的应用程序必须使用 `<supportedRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="f5973-137">如果使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数来指定配置文件，则必须对所有版本的运行时使用 `<requiredRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="f5973-138">当使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)时，将忽略 `<supportedRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="f5973-139">@No__t 的 .NET Framework 属性字符串必须与指定版本的的安装文件夹名称匹配。</span><span class="sxs-lookup"><span data-stu-id="f5973-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="f5973-140">不解释此字符串。</span><span class="sxs-lookup"><span data-stu-id="f5973-140">This string is not interpreted.</span></span> <span data-ttu-id="f5973-141">如果运行时启动代码找不到匹配的文件夹，则不加载运行时;启动代码将显示一条错误消息并退出。</span><span class="sxs-lookup"><span data-stu-id="f5973-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="f5973-142">在 Microsoft Internet Explorer 中托管的应用程序的启动代码将忽略 `<requiredRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5973-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="f5973-143">示例</span><span class="sxs-lookup"><span data-stu-id="f5973-143">Example</span></span>

<span data-ttu-id="f5973-144">下面的示例演示如何在配置文件中指定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f5973-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f5973-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5973-145">See also</span></span>

- [<span data-ttu-id="f5973-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="f5973-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f5973-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f5973-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f5973-148">如何：将应用配置为支持 .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="f5973-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
