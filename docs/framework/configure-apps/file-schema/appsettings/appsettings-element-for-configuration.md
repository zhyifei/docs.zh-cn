---
title: "&lt;appSettings&gt;元素&lt;配置&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cebb9ba7ebeb483233276324289a4ddc5a0bc381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="18853-102">\<appSettings > 元素\<配置 ></span><span class="sxs-lookup"><span data-stu-id="18853-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="18853-103">包含自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="18853-103">Contains custom application settings.</span></span> <span data-ttu-id="18853-104">这是.NET Framework 提供的预定义的配置节。</span><span class="sxs-lookup"><span data-stu-id="18853-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="18853-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="18853-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="18853-106">&nbsp;&nbsp;**\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="18853-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="18853-107">语法</span><span class="sxs-lookup"><span data-stu-id="18853-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="18853-108">特性</span><span class="sxs-lookup"><span data-stu-id="18853-108">Attribute</span></span>

|           | <span data-ttu-id="18853-109">描述</span><span class="sxs-lookup"><span data-stu-id="18853-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="18853-110">文件</span><span class="sxs-lookup"><span data-stu-id="18853-110">**file**</span></span>  | <span data-ttu-id="18853-111">可选特性。</span><span class="sxs-lookup"><span data-stu-id="18853-111">Optional attribute.</span></span><br><br><span data-ttu-id="18853-112">指定包含自定义应用程序配置设置的外部文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="18853-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="18853-113">指定的文件包含设置中指定的是同一种**\<添加 >**， **\<删除 >**，和**\<清除 >**元素，并使用相同的键/值对的格式设置为这些元素。</span><span class="sxs-lookup"><span data-stu-id="18853-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="18853-114">指定的路径是相对于主要配置文件。</span><span class="sxs-lookup"><span data-stu-id="18853-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="18853-115">对于 Windows 窗体应用程序，这是二进制文件夹 (如*/bin/debug*)，不应用程序配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="18853-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="18853-116">对于 Web 窗体应用程序，该路径是相对的应用程序根目录位置，其中*web.config*文件的位置。</span><span class="sxs-lookup"><span data-stu-id="18853-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="18853-117">请注意，运行时将忽略该属性，是否找不到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="18853-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="18853-118">父元素</span><span class="sxs-lookup"><span data-stu-id="18853-118">Parent element</span></span>

|     | <span data-ttu-id="18853-119">描述</span><span class="sxs-lookup"><span data-stu-id="18853-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="18853-120">**\<配置 >**元素</span><span class="sxs-lookup"><span data-stu-id="18853-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="18853-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="18853-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="18853-122">子元素</span><span class="sxs-lookup"><span data-stu-id="18853-122">Child elements</span></span>

|     | <span data-ttu-id="18853-123">描述</span><span class="sxs-lookup"><span data-stu-id="18853-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="18853-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="18853-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="18853-125">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="18853-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="18853-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="18853-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="18853-127">清除所有以前定义的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="18853-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="18853-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="18853-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="18853-129">删除以前定义的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="18853-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="18853-130">备注</span><span class="sxs-lookup"><span data-stu-id="18853-130">Remarks</span></span>

<span data-ttu-id="18853-131"> **\<AppSettings >**元素存储自定义应用程序配置信息，如数据库连接字符串、 文件路径、 XML Web 服务 Url 或任何其他自定义配置信息应用程序。</span><span class="sxs-lookup"><span data-stu-id="18853-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="18853-132">中指定的键/值对 **\<appSettings >**元素访问在代码中使用<xref:System.Configuration.ConfigurationSettings>类。</span><span class="sxs-lookup"><span data-stu-id="18853-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="18853-133">你可以使用**文件**属性中 **\<appSettings >**元素*Web.config*和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="18853-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="18853-134">此属性指定的配置文件来提供额外的设置或重写中指定的设置 **\<appSettings >**元素。</span><span class="sxs-lookup"><span data-stu-id="18853-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="18853-135">**文件**属性可以在源代码管理团队开发方案，例如当用户希望重写应用程序配置文件中指定的项目设置中使用。</span><span class="sxs-lookup"><span data-stu-id="18853-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="18853-136">指定的配置文件**文件**属性必须具有的根节点 **\<appSettings >**而非**\<配置 >**.</span><span class="sxs-lookup"><span data-stu-id="18853-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="18853-137">示例</span><span class="sxs-lookup"><span data-stu-id="18853-137">Example</span></span>

<span data-ttu-id="18853-138">下面的示例演示外部应用程序设置文件 (custom.config)，该文件定义自定义应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="18853-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="18853-139">下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：</span><span class="sxs-lookup"><span data-stu-id="18853-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="18853-140">配置文件</span><span class="sxs-lookup"><span data-stu-id="18853-140">Configuration file</span></span>

<span data-ttu-id="18853-141">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="18853-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="18853-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="18853-142">See also</span></span>

[<span data-ttu-id="18853-143">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="18853-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
