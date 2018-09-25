---
title: '&lt;添加&gt;元素&lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bcdac76528e7a8b07b56b6fd1d827c3c8072c371
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081547"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="d8025-102">\<添加 > 元素\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="d8025-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="d8025-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="d8025-103">Adds a custom application setting.</span></span>

<span data-ttu-id="d8025-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d8025-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d8025-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d8025-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="d8025-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="d8025-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d8025-107">语法</span><span class="sxs-lookup"><span data-stu-id="d8025-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="d8025-108">特性</span><span class="sxs-lookup"><span data-stu-id="d8025-108">Attributes</span></span>

|           | <span data-ttu-id="d8025-109">描述</span><span class="sxs-lookup"><span data-stu-id="d8025-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d8025-110">**key**</span><span class="sxs-lookup"><span data-stu-id="d8025-110">**key**</span></span>   | <span data-ttu-id="d8025-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d8025-111">Required attribute.</span></span><br><br><span data-ttu-id="d8025-112">指定要添加的键的名称。</span><span class="sxs-lookup"><span data-stu-id="d8025-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="d8025-113">**value**</span><span class="sxs-lookup"><span data-stu-id="d8025-113">**value**</span></span> | <span data-ttu-id="d8025-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d8025-114">Required attribute.</span></span><br><br><span data-ttu-id="d8025-115">指定要添加的键的值。</span><span class="sxs-lookup"><span data-stu-id="d8025-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d8025-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d8025-116">Parent element</span></span>

|     | <span data-ttu-id="d8025-117">描述</span><span class="sxs-lookup"><span data-stu-id="d8025-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d8025-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="d8025-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="d8025-119">包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="d8025-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d8025-120">子元素</span><span class="sxs-lookup"><span data-stu-id="d8025-120">Child elements</span></span>

<span data-ttu-id="d8025-121">无</span><span class="sxs-lookup"><span data-stu-id="d8025-121">None</span></span>

## <a name="example"></a><span data-ttu-id="d8025-122">示例</span><span class="sxs-lookup"><span data-stu-id="d8025-122">Example</span></span>

<span data-ttu-id="d8025-123">下面的示例演示如何添加应用程序的名称的自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="d8025-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="d8025-124">下面的示例使用`<add>`元素在 ASP.NET 应用程序中定义两个兼容性设置：</span><span class="sxs-lookup"><span data-stu-id="d8025-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="d8025-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8025-125">See also</span></span>

[<span data-ttu-id="d8025-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d8025-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
