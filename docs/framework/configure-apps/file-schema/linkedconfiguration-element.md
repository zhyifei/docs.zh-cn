---
title: "&lt;linkedConfiguration&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bfea438ec19303c35ad9d7a2816cb7b9473a00c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="54126-102">\<linkedConfiguration > 元素</span><span class="sxs-lookup"><span data-stu-id="54126-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="54126-103">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="54126-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="54126-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="54126-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="54126-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="54126-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="54126-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="54126-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="54126-107">语法</span><span class="sxs-lookup"><span data-stu-id="54126-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="54126-108">特性</span><span class="sxs-lookup"><span data-stu-id="54126-108">Attribute</span></span>

|           | <span data-ttu-id="54126-109">描述</span><span class="sxs-lookup"><span data-stu-id="54126-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="54126-110">**href**</span><span class="sxs-lookup"><span data-stu-id="54126-110">**href**</span></span>  | <span data-ttu-id="54126-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="54126-111">Required attribute.</span></span><br><br><span data-ttu-id="54126-112">要包括的配置文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="54126-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="54126-113">有关支持的唯一格式**href**属性是`file://`。</span><span class="sxs-lookup"><span data-stu-id="54126-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="54126-114">支持本地文件和 UNC 文件。</span><span class="sxs-lookup"><span data-stu-id="54126-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="54126-115">父元素</span><span class="sxs-lookup"><span data-stu-id="54126-115">Parent element</span></span>

|     | <span data-ttu-id="54126-116">描述</span><span class="sxs-lookup"><span data-stu-id="54126-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="54126-117">**\<assemblyBinding >**元素</span><span class="sxs-lookup"><span data-stu-id="54126-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="54126-118">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="54126-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="54126-119">子元素</span><span class="sxs-lookup"><span data-stu-id="54126-119">Child elements</span></span>

<span data-ttu-id="54126-120">无</span><span class="sxs-lookup"><span data-stu-id="54126-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="54126-121">备注</span><span class="sxs-lookup"><span data-stu-id="54126-121">Remarks</span></span>

<span data-ttu-id="54126-122">**\<LinkedConfiguration >**元素简化了维护的组件程序集。</span><span class="sxs-lookup"><span data-stu-id="54126-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="54126-123">如果一个或多个应用程序使用具有配置文件中的已知位置的程序集，可以使用的应用程序使用的程序集的配置文件 **\<linkedConfiguration >**元素以包含程序集配置文件，而不是直接包含配置信息。</span><span class="sxs-lookup"><span data-stu-id="54126-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="54126-124">组件程序集已维修，更新常见的配置文件提供所有应用程序使用的程序集的更新的配置的信息。</span><span class="sxs-lookup"><span data-stu-id="54126-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="54126-125">**\<LinkedConfiguration >**与 Windows 并排显示清单的应用程序中不支持元素。</span><span class="sxs-lookup"><span data-stu-id="54126-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="54126-126">以下规则控制的链接的配置文件的使用：</span><span class="sxs-lookup"><span data-stu-id="54126-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="54126-127">包含的配置文件中的设置仅影响加载程序绑定策略，并只由加载程序。</span><span class="sxs-lookup"><span data-stu-id="54126-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="54126-128">包含的配置文件可以设置而非绑定策略，但这些设置不产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="54126-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="54126-129">有关支持的唯一格式`href`属性是`file://`。</span><span class="sxs-lookup"><span data-stu-id="54126-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="54126-130">支持本地文件和 UNC 文件。</span><span class="sxs-lookup"><span data-stu-id="54126-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="54126-131">不没有链接配置每个配置文件数受任何约束。</span><span class="sxs-lookup"><span data-stu-id="54126-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="54126-132">所有链接的配置文件合并，以形成一个文件的行为类似`#include`C/c + + 中的指令。</span><span class="sxs-lookup"><span data-stu-id="54126-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="54126-133">**\<LinkedConfiguration >**元素允许仅在应用程序配置文件中; 在将被忽略*Machine.config*。</span><span class="sxs-lookup"><span data-stu-id="54126-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="54126-134">检测和终止循环引用。</span><span class="sxs-lookup"><span data-stu-id="54126-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="54126-135">也就是说，如果 **\<linkedConfiguration >**的一系列的配置文件的元素形成循环，循环是检测到，并已停止。</span><span class="sxs-lookup"><span data-stu-id="54126-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="54126-136">示例</span><span class="sxs-lookup"><span data-stu-id="54126-136">Example</span></span>

<span data-ttu-id="54126-137">下面的示例演示如何将从本地硬盘上的配置文件包括：</span><span class="sxs-lookup"><span data-stu-id="54126-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="54126-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="54126-138">See also</span></span>

<span data-ttu-id="54126-139">[**\<assemblyBinding >**元素](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="54126-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="54126-140">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="54126-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
