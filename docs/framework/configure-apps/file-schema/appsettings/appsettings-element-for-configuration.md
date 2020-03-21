---
title: <configuration> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155526"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="410fc-102">\<用于\<配置>的应用设置>元素</span><span class="sxs-lookup"><span data-stu-id="410fc-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="410fc-103">包含自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="410fc-103">Contains custom application settings.</span></span> <span data-ttu-id="410fc-104">这是由 .NET 框架提供的预定义配置部分。</span><span class="sxs-lookup"><span data-stu-id="410fc-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="410fc-105">&nbsp;[**\<配置>**](../configuration-element.md)&nbsp;**应用设置>\<**</span><span class="sxs-lookup"><span data-stu-id="410fc-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="410fc-106">语法</span><span class="sxs-lookup"><span data-stu-id="410fc-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="410fc-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="410fc-107">Attribute</span></span>

|           | <span data-ttu-id="410fc-108">说明</span><span class="sxs-lookup"><span data-stu-id="410fc-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="410fc-109">**文件**</span><span class="sxs-lookup"><span data-stu-id="410fc-109">**file**</span></span>  | <span data-ttu-id="410fc-110">可选特性。</span><span class="sxs-lookup"><span data-stu-id="410fc-110">Optional attribute.</span></span><br><br><span data-ttu-id="410fc-111">指定包含自定义应用程序配置设置的外部文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="410fc-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="410fc-112">指定的文件包含在**\<添加>、\*\*\*\*\<删除>** 和**\<清除>** 元素中指定的相同类型的设置，并使用与这些元素相同的键/值对格式。</span><span class="sxs-lookup"><span data-stu-id="410fc-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="410fc-113">指定的路径与主配置文件相关。</span><span class="sxs-lookup"><span data-stu-id="410fc-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="410fc-114">对于 Windows 窗体应用程序，这是二进制文件夹（如 */bin/调试*），而不是应用程序配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="410fc-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="410fc-115">对于 Web 窗体应用程序，路径相对于*Web.config*文件所在的应用程序根。</span><span class="sxs-lookup"><span data-stu-id="410fc-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="410fc-116">如果找不到指定的文件，运行时将忽略该属性。</span><span class="sxs-lookup"><span data-stu-id="410fc-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="410fc-117">父元素</span><span class="sxs-lookup"><span data-stu-id="410fc-117">Parent element</span></span>

|     | <span data-ttu-id="410fc-118">说明</span><span class="sxs-lookup"><span data-stu-id="410fc-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="410fc-119">**\<配置>** 元素</span><span class="sxs-lookup"><span data-stu-id="410fc-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="410fc-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="410fc-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="410fc-121">子元素</span><span class="sxs-lookup"><span data-stu-id="410fc-121">Child elements</span></span>

|     | <span data-ttu-id="410fc-122">说明</span><span class="sxs-lookup"><span data-stu-id="410fc-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="410fc-123">**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="410fc-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="410fc-124">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="410fc-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="410fc-125">**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="410fc-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="410fc-126">清除以前定义的所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="410fc-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="410fc-127">**\<删除>**</span><span class="sxs-lookup"><span data-stu-id="410fc-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="410fc-128">删除以前定义的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="410fc-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="410fc-129">备注</span><span class="sxs-lookup"><span data-stu-id="410fc-129">Remarks</span></span>

<span data-ttu-id="410fc-130">appSettings>元素存储自定义应用程序配置信息，如数据库连接字符串、文件路径、XML Web 服务 URL 或应用程序的任何其他自定义配置信息。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="410fc-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="410fc-131">使用<xref:System.Configuration.ConfigurationSettings>类在代码中访问**\<appSettings>** 元素中指定的键/值对。</span><span class="sxs-lookup"><span data-stu-id="410fc-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="410fc-132">您可以在**\<AppSettings>** *Web.config*和应用程序配置文件的元素中使用**文件**属性。</span><span class="sxs-lookup"><span data-stu-id="410fc-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="410fc-133">此属性指定提供其他设置或覆盖**\<appSettings>** 元素中指定的设置的配置文件。</span><span class="sxs-lookup"><span data-stu-id="410fc-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="410fc-134">**文件**属性可用于源代码管理团队开发方案，例如当用户想要覆盖应用程序配置文件中指定的项目设置时。</span><span class="sxs-lookup"><span data-stu-id="410fc-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="410fc-135">**文件**属性指定的配置文件必须具有**\<appSettings>** 的根节点，而不是\*\*\<配置>。 \*\*</span><span class="sxs-lookup"><span data-stu-id="410fc-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="410fc-136">示例</span><span class="sxs-lookup"><span data-stu-id="410fc-136">Example</span></span>

<span data-ttu-id="410fc-137">下面的示例演示外部应用程序设置文件 (custom.config\*\*)，该文件定义自定义应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="410fc-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="410fc-138">下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：</span><span class="sxs-lookup"><span data-stu-id="410fc-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="410fc-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="410fc-139">Configuration file</span></span>

<span data-ttu-id="410fc-140">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="410fc-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="410fc-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="410fc-141">See also</span></span>

- [<span data-ttu-id="410fc-142">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="410fc-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
