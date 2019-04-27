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
ms.openlocfilehash: 5e528a8b81fa3d9abc4f345d18f01e33f483a4a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673831"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="33adc-102">\<requiredRuntime > 元素</span><span class="sxs-lookup"><span data-stu-id="33adc-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="33adc-103">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="33adc-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="33adc-104">此元素已弃用，应不再使用。</span><span class="sxs-lookup"><span data-stu-id="33adc-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="33adc-105">[ `supportedRuntime` ](supportedruntime-element.md)元素应改为使用。</span><span class="sxs-lookup"><span data-stu-id="33adc-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="33adc-106">\<configuration> \<startup> \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="33adc-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="33adc-107">语法</span><span class="sxs-lookup"><span data-stu-id="33adc-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33adc-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="33adc-108">Attributes and elements</span></span>

<span data-ttu-id="33adc-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="33adc-110">特性</span><span class="sxs-lookup"><span data-stu-id="33adc-110">Attributes</span></span>

|<span data-ttu-id="33adc-111">特性</span><span class="sxs-lookup"><span data-stu-id="33adc-111">Attribute</span></span>|<span data-ttu-id="33adc-112">描述</span><span class="sxs-lookup"><span data-stu-id="33adc-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="33adc-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="33adc-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="33adc-114">一个字符串值，该值指定此应用程序支持的.NET framework 版本。</span><span class="sxs-lookup"><span data-stu-id="33adc-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="33adc-115">字符串值必须与.NET Framework 安装根目录下找到的目录名称匹配。</span><span class="sxs-lookup"><span data-stu-id="33adc-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="33adc-116">未分析的字符串值的内容。</span><span class="sxs-lookup"><span data-stu-id="33adc-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="33adc-117">可选特性。</span><span class="sxs-lookup"><span data-stu-id="33adc-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="33adc-118">指定是否在运行时启动代码搜索注册表，以确定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="33adc-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="33adc-119">安全模式属性</span><span class="sxs-lookup"><span data-stu-id="33adc-119">safemode attribute</span></span>

|<span data-ttu-id="33adc-120">“值”</span><span class="sxs-lookup"><span data-stu-id="33adc-120">Value</span></span>|<span data-ttu-id="33adc-121">描述</span><span class="sxs-lookup"><span data-stu-id="33adc-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="33adc-122">在注册表中查找运行时启动代码。</span><span class="sxs-lookup"><span data-stu-id="33adc-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="33adc-123">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="33adc-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="33adc-124">运行时启动代码不会在注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="33adc-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="33adc-125">子元素</span><span class="sxs-lookup"><span data-stu-id="33adc-125">Child elements</span></span>

<span data-ttu-id="33adc-126">无。</span><span class="sxs-lookup"><span data-stu-id="33adc-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="33adc-127">父元素</span><span class="sxs-lookup"><span data-stu-id="33adc-127">Parent elements</span></span>

|<span data-ttu-id="33adc-128">元素</span><span class="sxs-lookup"><span data-stu-id="33adc-128">Element</span></span>|<span data-ttu-id="33adc-129">描述</span><span class="sxs-lookup"><span data-stu-id="33adc-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="33adc-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="33adc-131">包含`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33adc-132">备注</span><span class="sxs-lookup"><span data-stu-id="33adc-132">Remarks</span></span>
 <span data-ttu-id="33adc-133">仅支持 1.0 版的运行时生成的应用程序必须使用`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="33adc-134">构建使用 1.1 版或更高版本的运行时版本的应用程序必须使用`<supportedRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="33adc-135">如果您使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数以指定配置文件，则必须使用`<requiredRuntime>`所有版本的运行时的元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="33adc-136">`<supportedRuntime>`使用时，将忽略元素[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。</span><span class="sxs-lookup"><span data-stu-id="33adc-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="33adc-137">`version`属性字符串必须匹配指定版本的.NET framework 的安装文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="33adc-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="33adc-138">此字符串不解释。</span><span class="sxs-lookup"><span data-stu-id="33adc-138">This string is not interpreted.</span></span> <span data-ttu-id="33adc-139">如果运行时启动代码没有找到匹配的文件夹，则不会加载运行时;启动代码显示了一条错误消息并退出。</span><span class="sxs-lookup"><span data-stu-id="33adc-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="33adc-140">Microsoft Internet Explorer 中承载的应用程序的启动代码将忽略`<requiredRuntime>`元素。</span><span class="sxs-lookup"><span data-stu-id="33adc-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="33adc-141">示例</span><span class="sxs-lookup"><span data-stu-id="33adc-141">Example</span></span>

<span data-ttu-id="33adc-142">下面的示例演示如何在配置文件中指定的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="33adc-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="33adc-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="33adc-143">See also</span></span>

- [<span data-ttu-id="33adc-144">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="33adc-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="33adc-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="33adc-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="33adc-146">如何：将应用配置为支持 .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="33adc-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)