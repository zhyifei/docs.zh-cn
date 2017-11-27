---
title: "&lt;添加&gt;元素&lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b00af6f7d735d5db8fd746205ba225253cad133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="31cf6-102">\<添加 > 元素\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="31cf6-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="31cf6-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="31cf6-103">Adds a custom application setting.</span></span>

<span data-ttu-id="31cf6-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="31cf6-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="31cf6-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="31cf6-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="31cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="31cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="31cf6-107">语法</span><span class="sxs-lookup"><span data-stu-id="31cf6-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="31cf6-108">特性</span><span class="sxs-lookup"><span data-stu-id="31cf6-108">Attributes</span></span>

|           | <span data-ttu-id="31cf6-109">描述</span><span class="sxs-lookup"><span data-stu-id="31cf6-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="31cf6-110">**key**</span><span class="sxs-lookup"><span data-stu-id="31cf6-110">**key**</span></span>   | <span data-ttu-id="31cf6-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="31cf6-111">Required attribute.</span></span><br><br><span data-ttu-id="31cf6-112">指定要添加的键的名称。</span><span class="sxs-lookup"><span data-stu-id="31cf6-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="31cf6-113">**值**</span><span class="sxs-lookup"><span data-stu-id="31cf6-113">**value**</span></span> | <span data-ttu-id="31cf6-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="31cf6-114">Required attribute.</span></span><br><br><span data-ttu-id="31cf6-115">指定要添加的键的值。</span><span class="sxs-lookup"><span data-stu-id="31cf6-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="31cf6-116">父元素</span><span class="sxs-lookup"><span data-stu-id="31cf6-116">Parent element</span></span>

|     | <span data-ttu-id="31cf6-117">描述</span><span class="sxs-lookup"><span data-stu-id="31cf6-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="31cf6-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="31cf6-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="31cf6-119">包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="31cf6-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="31cf6-120">子元素</span><span class="sxs-lookup"><span data-stu-id="31cf6-120">Child elements</span></span>

<span data-ttu-id="31cf6-121">无</span><span class="sxs-lookup"><span data-stu-id="31cf6-121">None</span></span>

## <a name="example"></a><span data-ttu-id="31cf6-122">示例</span><span class="sxs-lookup"><span data-stu-id="31cf6-122">Example</span></span>

<span data-ttu-id="31cf6-123">下面的示例演示如何添加自定义配置设置应用程序的名称：</span><span class="sxs-lookup"><span data-stu-id="31cf6-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="31cf6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="31cf6-124">See also</span></span>

[<span data-ttu-id="31cf6-125">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="31cf6-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
