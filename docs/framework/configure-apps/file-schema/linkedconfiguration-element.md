---
title: <linkedConfiguration> 元素
ms.date: 03/30/2017
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087966"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="554b2-102">\<linkedConfiguration > 元素</span><span class="sxs-lookup"><span data-stu-id="554b2-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="554b2-103">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="554b2-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="554b2-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="554b2-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="554b2-105">&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="554b2-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="554b2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="554b2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="554b2-107">语法</span><span class="sxs-lookup"><span data-stu-id="554b2-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="554b2-108">特性</span><span class="sxs-lookup"><span data-stu-id="554b2-108">Attribute</span></span>

|           | <span data-ttu-id="554b2-109">描述</span><span class="sxs-lookup"><span data-stu-id="554b2-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="554b2-110">**href**</span><span class="sxs-lookup"><span data-stu-id="554b2-110">**href**</span></span>  | <span data-ttu-id="554b2-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="554b2-111">Required attribute.</span></span><br><br><span data-ttu-id="554b2-112">要包含的配置文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="554b2-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="554b2-113">**Href**特性支持的唯一格式是 `file://`。</span><span class="sxs-lookup"><span data-stu-id="554b2-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="554b2-114">支持本地文件和 UNC 文件。</span><span class="sxs-lookup"><span data-stu-id="554b2-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="554b2-115">父元素</span><span class="sxs-lookup"><span data-stu-id="554b2-115">Parent element</span></span>

|     | <span data-ttu-id="554b2-116">描述</span><span class="sxs-lookup"><span data-stu-id="554b2-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="554b2-117"> **\<assemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="554b2-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="554b2-118">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="554b2-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="554b2-119">子元素</span><span class="sxs-lookup"><span data-stu-id="554b2-119">Child elements</span></span>

<span data-ttu-id="554b2-120">None</span><span class="sxs-lookup"><span data-stu-id="554b2-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="554b2-121">备注</span><span class="sxs-lookup"><span data-stu-id="554b2-121">Remarks</span></span>

<span data-ttu-id="554b2-122">**\<linkedConfiguration >** 元素简化了组件程序集的服务。</span><span class="sxs-lookup"><span data-stu-id="554b2-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="554b2-123">如果一个或多个应用程序使用的程序集具有驻留在众所周知位置的配置文件，则使用该程序集的应用程序的配置文件可以使用 **\<linkedConfiguration >** 元素来包含程序集配置文件，而不是直接包含配置信息。</span><span class="sxs-lookup"><span data-stu-id="554b2-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="554b2-124">处理组件程序集时，更新公共配置文件会为使用该程序集的所有应用程序提供更新的配置信息。</span><span class="sxs-lookup"><span data-stu-id="554b2-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="554b2-125">具有 Windows 并行清单的应用程序不支持 **\<linkedConfiguration >** 元素。</span><span class="sxs-lookup"><span data-stu-id="554b2-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="554b2-126">以下规则控制链接配置文件的使用：</span><span class="sxs-lookup"><span data-stu-id="554b2-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="554b2-127">包含的配置文件中的设置只会影响加载程序绑定策略并仅由加载程序使用。</span><span class="sxs-lookup"><span data-stu-id="554b2-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="554b2-128">包含的配置文件可以包含绑定策略以外的设置，但这些设置不会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="554b2-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="554b2-129">`href` 特性支持的唯一格式为 `file://`。</span><span class="sxs-lookup"><span data-stu-id="554b2-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="554b2-130">支持本地文件和 UNC 文件。</span><span class="sxs-lookup"><span data-stu-id="554b2-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="554b2-131">每个配置文件的链接配置数没有限制。</span><span class="sxs-lookup"><span data-stu-id="554b2-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="554b2-132">所有链接的配置文件合并到一个文件中，这与 C/C++中的 `#include` 指令的行为类似。</span><span class="sxs-lookup"><span data-stu-id="554b2-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="554b2-133">仅在应用程序配置文件中允许 **\<linkedConfiguration >** 元素;它在*machine.config*中被忽略。</span><span class="sxs-lookup"><span data-stu-id="554b2-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="554b2-134">检测和终止循环引用。</span><span class="sxs-lookup"><span data-stu-id="554b2-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="554b2-135">也就是说，如果 **\<** 一系列配置文件的元素形成循环，则检测并停止循环。</span><span class="sxs-lookup"><span data-stu-id="554b2-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="554b2-136">示例</span><span class="sxs-lookup"><span data-stu-id="554b2-136">Example</span></span>

<span data-ttu-id="554b2-137">下面的示例演示如何包括本地硬盘中的配置文件：</span><span class="sxs-lookup"><span data-stu-id="554b2-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="554b2-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="554b2-138">See also</span></span>

- [<span data-ttu-id="554b2-139"> **\<assemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="554b2-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="554b2-140">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="554b2-140">Configuration file schema for the .NET Framework</span></span>](index.md)
