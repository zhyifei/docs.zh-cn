---
title: <appSettings> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 0b6a48d1fdab3cbccf40aaa77731a658f533eeba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705397"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="7aa6d-102">\<清除 > 元素\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="7aa6d-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="7aa6d-103">清除自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="7aa6d-103">Clears custom application settings.</span></span>

<span data-ttu-id="7aa6d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7aa6d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7aa6d-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7aa6d-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="7aa6d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="7aa6d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7aa6d-107">语法</span><span class="sxs-lookup"><span data-stu-id="7aa6d-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="7aa6d-108">特性</span><span class="sxs-lookup"><span data-stu-id="7aa6d-108">Attributes</span></span>

<span data-ttu-id="7aa6d-109">None</span><span class="sxs-lookup"><span data-stu-id="7aa6d-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7aa6d-110">父元素</span><span class="sxs-lookup"><span data-stu-id="7aa6d-110">Parent element</span></span>

|     | <span data-ttu-id="7aa6d-111">描述</span><span class="sxs-lookup"><span data-stu-id="7aa6d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7aa6d-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="7aa6d-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="7aa6d-113">包含自定义应用程序设置，如文件路径、 XML Web service Url 或任何其他自定义应用程序配置信息。</span><span class="sxs-lookup"><span data-stu-id="7aa6d-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7aa6d-114">子元素</span><span class="sxs-lookup"><span data-stu-id="7aa6d-114">Child elements</span></span>

<span data-ttu-id="7aa6d-115">None</span><span class="sxs-lookup"><span data-stu-id="7aa6d-115">None</span></span>

## <a name="example"></a><span data-ttu-id="7aa6d-116">示例</span><span class="sxs-lookup"><span data-stu-id="7aa6d-116">Example</span></span>

<span data-ttu-id="7aa6d-117">下面的示例演示如何清除自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="7aa6d-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="7aa6d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa6d-118">See also</span></span>

- [<span data-ttu-id="7aa6d-119">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7aa6d-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
