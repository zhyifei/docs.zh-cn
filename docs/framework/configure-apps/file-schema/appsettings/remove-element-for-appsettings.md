---
title: "&lt;删除&gt;元素&lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 10202a38d54e4c9744dbd20fb5f226fa41f5dab5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="9177f-102">\<删除 > 元素\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="9177f-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="9177f-103">删除自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="9177f-103">Removes custom application settings.</span></span>

<span data-ttu-id="9177f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="9177f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="9177f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9177f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="9177f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="9177f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9177f-107">语法</span><span class="sxs-lookup"><span data-stu-id="9177f-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="9177f-108">特性</span><span class="sxs-lookup"><span data-stu-id="9177f-108">Attribute</span></span>

|         | <span data-ttu-id="9177f-109">描述</span><span class="sxs-lookup"><span data-stu-id="9177f-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="9177f-110">**key**</span><span class="sxs-lookup"><span data-stu-id="9177f-110">**key**</span></span> | <span data-ttu-id="9177f-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="9177f-111">Required attribute.</span></span><br><br><span data-ttu-id="9177f-112">指定要移除的键的名称。</span><span class="sxs-lookup"><span data-stu-id="9177f-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="9177f-113">父元素</span><span class="sxs-lookup"><span data-stu-id="9177f-113">Parent element</span></span>

|     | <span data-ttu-id="9177f-114">描述</span><span class="sxs-lookup"><span data-stu-id="9177f-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9177f-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="9177f-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="9177f-116">包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="9177f-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9177f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="9177f-117">Child elements</span></span>

<span data-ttu-id="9177f-118">无</span><span class="sxs-lookup"><span data-stu-id="9177f-118">None</span></span>

## <a name="example"></a><span data-ttu-id="9177f-119">示例</span><span class="sxs-lookup"><span data-stu-id="9177f-119">Example</span></span>

<span data-ttu-id="9177f-120">下面的示例演示如何删除的自定义配置设置`ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="9177f-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="9177f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9177f-121">See also</span></span>

[<span data-ttu-id="9177f-122">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9177f-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
