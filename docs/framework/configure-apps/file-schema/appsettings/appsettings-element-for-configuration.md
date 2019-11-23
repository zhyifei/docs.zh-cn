---
title: <appSettings> 的 <configuration> 元素
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
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="688af-102">\<配置 \<appSettings > 元素 ></span><span class="sxs-lookup"><span data-stu-id="688af-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="688af-103">包含自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="688af-103">Contains custom application settings.</span></span> <span data-ttu-id="688af-104">这是 .NET Framework 提供的预定义的配置节。</span><span class="sxs-lookup"><span data-stu-id="688af-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="688af-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="688af-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="688af-106">&nbsp;&nbsp; **\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="688af-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="688af-107">语法</span><span class="sxs-lookup"><span data-stu-id="688af-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="688af-108">属性</span><span class="sxs-lookup"><span data-stu-id="688af-108">Attribute</span></span>

|           | <span data-ttu-id="688af-109">说明</span><span class="sxs-lookup"><span data-stu-id="688af-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="688af-110">文件</span><span class="sxs-lookup"><span data-stu-id="688af-110">**file**</span></span>  | <span data-ttu-id="688af-111">可选特性。</span><span class="sxs-lookup"><span data-stu-id="688af-111">Optional attribute.</span></span><br><br><span data-ttu-id="688af-112">指定包含自定义应用程序配置设置的外部文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="688af-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="688af-113">指定的文件是否包含相同类型的设置中指定 **\<添加 >** ， **\<删除 >** ，以及 **\<清除 >** 元素，并使用同一个键/值对的格式设置为这些元素。</span><span class="sxs-lookup"><span data-stu-id="688af-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="688af-114">指定的路径相对于主配置文件。</span><span class="sxs-lookup"><span data-stu-id="688af-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="688af-115">对于 Windows 窗体应用程序，这是二进制文件夹（如 */bin/debug*），而不是应用程序配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="688af-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="688af-116">对于 Web 窗体应用程序，该路径相对于在其中找到*web.config*文件的应用程序根目录。</span><span class="sxs-lookup"><span data-stu-id="688af-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="688af-117">请注意，如果找不到指定的文件，则运行时将忽略属性。</span><span class="sxs-lookup"><span data-stu-id="688af-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="688af-118">父元素</span><span class="sxs-lookup"><span data-stu-id="688af-118">Parent element</span></span>

|     | <span data-ttu-id="688af-119">说明</span><span class="sxs-lookup"><span data-stu-id="688af-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="688af-120"> **\<配置 >** Element</span><span class="sxs-lookup"><span data-stu-id="688af-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="688af-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="688af-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="688af-122">子元素</span><span class="sxs-lookup"><span data-stu-id="688af-122">Child elements</span></span>

|     | <span data-ttu-id="688af-123">说明</span><span class="sxs-lookup"><span data-stu-id="688af-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="688af-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="688af-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="688af-125">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="688af-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="688af-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="688af-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="688af-127">清除以前定义的所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="688af-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="688af-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="688af-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="688af-129">删除以前定义的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="688af-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="688af-130">备注</span><span class="sxs-lookup"><span data-stu-id="688af-130">Remarks</span></span>

<span data-ttu-id="688af-131">**\<AppSettings >** 元素将自定义应用程序配置信息，如数据库连接字符串、 文件路径、 XML Web service Url 或任何其他自定义配置信息存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="688af-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="688af-132">**\<appSettings >** 元素中指定的键/值对是使用 <xref:System.Configuration.ConfigurationSettings> 类在代码中访问的。</span><span class="sxs-lookup"><span data-stu-id="688af-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="688af-133">您可以使用*web.config 和应用*程序配置文件的 **\<appSettings >** 元素中的**文件**属性。</span><span class="sxs-lookup"><span data-stu-id="688af-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="688af-134">此属性指定一个配置文件，该配置文件提供其他设置或替代 **\<appSettings >** 元素中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="688af-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="688af-135">**文件**属性可用于源代码管理团队开发方案，例如当用户想要重写应用程序配置文件中指定的项目设置时。</span><span class="sxs-lookup"><span data-stu-id="688af-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="688af-136">指定的配置文件 **文件** 属性必须具有的根节点 **\<appSettings >** 而非 **\<配置 >** .</span><span class="sxs-lookup"><span data-stu-id="688af-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="688af-137">示例</span><span class="sxs-lookup"><span data-stu-id="688af-137">Example</span></span>

<span data-ttu-id="688af-138">下面的示例演示外部应用程序设置文件 (custom.config)，该文件定义自定义应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="688af-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="688af-139">下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：</span><span class="sxs-lookup"><span data-stu-id="688af-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="688af-140">配置文件</span><span class="sxs-lookup"><span data-stu-id="688af-140">Configuration file</span></span>

<span data-ttu-id="688af-141">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="688af-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="688af-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="688af-142">See also</span></span>

- [<span data-ttu-id="688af-143">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="688af-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
