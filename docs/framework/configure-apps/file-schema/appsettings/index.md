---
title: "应用设置架构"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d51d06895e61be60bbe9153eacb2028cb32a1fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="app-settings-schema"></a><span data-ttu-id="b389c-102">应用设置架构</span><span class="sxs-lookup"><span data-stu-id="b389c-102">App Settings schema</span></span>

<span data-ttu-id="b389c-103">包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="b389c-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="b389c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b389c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b389c-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b389c-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="b389c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="b389c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="b389c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="b389c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="b389c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="b389c-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="b389c-109">元素</span><span class="sxs-lookup"><span data-stu-id="b389c-109">Element</span></span> | <span data-ttu-id="b389c-110">描述</span><span class="sxs-lookup"><span data-stu-id="b389c-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="b389c-111">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="b389c-111">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="b389c-112">包含 **\<add>**、**\<clear>** 和 **\<remove>** 标记，用于控制应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="b389c-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="b389c-113">具有可选的“file”属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="b389c-114">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="b389c-114">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="b389c-115">定义设置。</span><span class="sxs-lookup"><span data-stu-id="b389c-115">Defines a setting.</span></span> <span data-ttu-id="b389c-116">**\<appSettings>** 的子级。</span><span class="sxs-lookup"><span data-stu-id="b389c-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="b389c-117">需要“key”和“value”属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="b389c-118">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="b389c-118">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="b389c-119">清除所有设置。</span><span class="sxs-lookup"><span data-stu-id="b389c-119">Clears all settings.</span></span> <span data-ttu-id="b389c-120">**\<appSettings>** 的子级。</span><span class="sxs-lookup"><span data-stu-id="b389c-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="b389c-121">不具有属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-121">Has no attributes.</span></span> |
| [<span data-ttu-id="b389c-122">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="b389c-122">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="b389c-123">删除设置。</span><span class="sxs-lookup"><span data-stu-id="b389c-123">Removes a setting.</span></span> <span data-ttu-id="b389c-124">**\<appSettings>** 的子级。</span><span class="sxs-lookup"><span data-stu-id="b389c-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="b389c-125">需要“key”属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="b389c-126">\<appSettings> 元素</span><span class="sxs-lookup"><span data-stu-id="b389c-126">\<appSettings> element</span></span>

<span data-ttu-id="b389c-127">此元素包含 **\<add>**、**\<clear>** 和 **\<remove>** 标记，用于控制应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="b389c-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="b389c-128">它定义“file”的一个可选属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="b389c-129">\<add> 元素</span><span class="sxs-lookup"><span data-stu-id="b389c-129">\<add> element</span></span>

<span data-ttu-id="b389c-130">将自定义应用程序设置作为名称/值对添加到应用程序设置集合。</span><span class="sxs-lookup"><span data-stu-id="b389c-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="b389c-131">它定义“key”和“value”的属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="b389c-132">\<clear> 元素</span><span class="sxs-lookup"><span data-stu-id="b389c-132">\<clear> element</span></span>

<span data-ttu-id="b389c-133">删除对继承的自定义应用程序设置的所有引用，并仅允许由 **\<add>** 元素（位于 **\<clear>** 元素后）添加的引用。</span><span class="sxs-lookup"><span data-stu-id="b389c-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="b389c-134">未定义任何属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="b389c-135">\<remove> 元素</span><span class="sxs-lookup"><span data-stu-id="b389c-135">\<remove> element</span></span>

<span data-ttu-id="b389c-136">删除对应用程序设置集合中继承的自定义应用程序设置的引用。</span><span class="sxs-lookup"><span data-stu-id="b389c-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="b389c-137">定义“key”的属性。</span><span class="sxs-lookup"><span data-stu-id="b389c-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="b389c-138">示例</span><span class="sxs-lookup"><span data-stu-id="b389c-138">Example</span></span>

<span data-ttu-id="b389c-139">下面的示例演示外部应用程序设置文件 (custom.config)，该文件定义自定义应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="b389c-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="b389c-140">下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：</span><span class="sxs-lookup"><span data-stu-id="b389c-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b389c-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b389c-141">See also</span></span>

<span data-ttu-id="b389c-142">[应用程序设置概述](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b389c-142">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="b389c-143">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="b389c-143">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
