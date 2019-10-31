---
title: <configuration> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6112d87afcca8b2f54508d03d3ea4c0781d7e475
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119271"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="091d4-102">\<配置 \<appSettings > 元素 ></span><span class="sxs-lookup"><span data-stu-id="091d4-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="091d4-103">包含自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="091d4-103">Contains custom application settings.</span></span> <span data-ttu-id="091d4-104">这是 .NET Framework 提供的预定义的配置节。</span><span class="sxs-lookup"><span data-stu-id="091d4-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="091d4-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="091d4-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="091d4-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="091d4-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="091d4-107">语法</span><span class="sxs-lookup"><span data-stu-id="091d4-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="091d4-108">特性</span><span class="sxs-lookup"><span data-stu-id="091d4-108">Attribute</span></span>

|           | <span data-ttu-id="091d4-109">描述</span><span class="sxs-lookup"><span data-stu-id="091d4-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="091d4-110">文件</span><span class="sxs-lookup"><span data-stu-id="091d4-110">**file**</span></span>  | <span data-ttu-id="091d4-111">可选特性。</span><span class="sxs-lookup"><span data-stu-id="091d4-111">Optional attribute.</span></span><br><br><span data-ttu-id="091d4-112">指定包含自定义应用程序配置设置的外部文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="091d4-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="091d4-113">指定的文件包含相同类型的设置，这些设置在 **\<添加 >** 中指定， **\<删除 >** ， **\<明文 >** 元素，并使用与这些元素相同的键/值对格式。</span><span class="sxs-lookup"><span data-stu-id="091d4-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="091d4-114">指定的路径相对于主配置文件。</span><span class="sxs-lookup"><span data-stu-id="091d4-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="091d4-115">对于 Windows 窗体应用程序，这是二进制文件夹（如 */bin/debug*），而不是应用程序配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="091d4-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="091d4-116">对于 Web 窗体应用程序，该路径相对于在其中找到*web.config*文件的应用程序根目录。</span><span class="sxs-lookup"><span data-stu-id="091d4-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="091d4-117">请注意，如果找不到指定的文件，则运行时将忽略属性。</span><span class="sxs-lookup"><span data-stu-id="091d4-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="091d4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="091d4-118">Parent element</span></span>

|     | <span data-ttu-id="091d4-119">描述</span><span class="sxs-lookup"><span data-stu-id="091d4-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="091d4-120"> **\<配置 >** Element</span><span class="sxs-lookup"><span data-stu-id="091d4-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="091d4-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="091d4-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="091d4-122">子元素</span><span class="sxs-lookup"><span data-stu-id="091d4-122">Child elements</span></span>

|     | <span data-ttu-id="091d4-123">描述</span><span class="sxs-lookup"><span data-stu-id="091d4-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="091d4-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="091d4-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="091d4-125">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="091d4-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="091d4-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="091d4-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="091d4-127">清除以前定义的所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="091d4-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="091d4-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="091d4-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="091d4-129">删除以前定义的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="091d4-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="091d4-130">备注</span><span class="sxs-lookup"><span data-stu-id="091d4-130">Remarks</span></span>

<span data-ttu-id="091d4-131">**\<AppSettings >** 元素将自定义应用程序配置信息，如数据库连接字符串、 文件路径、 XML Web service Url 或任何其他自定义配置信息存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="091d4-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="091d4-132">**\<appSettings >** 元素中指定的键/值对是使用 <xref:System.Configuration.ConfigurationSettings> 类在代码中访问的。</span><span class="sxs-lookup"><span data-stu-id="091d4-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="091d4-133">您可以使用*web.config 和应用*程序配置文件的 **\<appSettings >** 元素中的**文件**属性。</span><span class="sxs-lookup"><span data-stu-id="091d4-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="091d4-134">此属性指定一个配置文件，该配置文件提供其他设置或替代 **\<appSettings >** 元素中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="091d4-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="091d4-135">**文件**属性可用于源代码管理团队开发方案，例如当用户想要重写应用程序配置文件中指定的项目设置时。</span><span class="sxs-lookup"><span data-stu-id="091d4-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="091d4-136">**文件**属性指定的配置文件必须具有 **\<appSettings >** 的根节点，而不是 **\<配置 >** 。</span><span class="sxs-lookup"><span data-stu-id="091d4-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="091d4-137">示例</span><span class="sxs-lookup"><span data-stu-id="091d4-137">Example</span></span>

<span data-ttu-id="091d4-138">下面的示例演示外部应用程序设置文件 (custom.config)，该文件定义自定义应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="091d4-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="091d4-139">下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：</span><span class="sxs-lookup"><span data-stu-id="091d4-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="091d4-140">配置文件</span><span class="sxs-lookup"><span data-stu-id="091d4-140">Configuration file</span></span>

<span data-ttu-id="091d4-141">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="091d4-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="091d4-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="091d4-142">See also</span></span>

- [<span data-ttu-id="091d4-143">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="091d4-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
