---
title: <appSettings> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301298"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="a501b-102">\<清除 > 元素\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="a501b-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="a501b-103">清除自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="a501b-103">Clears custom application settings.</span></span>

<span data-ttu-id="a501b-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a501b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a501b-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="a501b-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="a501b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="a501b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a501b-107">语法</span><span class="sxs-lookup"><span data-stu-id="a501b-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="a501b-108">特性</span><span class="sxs-lookup"><span data-stu-id="a501b-108">Attributes</span></span>

<span data-ttu-id="a501b-109">None</span><span class="sxs-lookup"><span data-stu-id="a501b-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="a501b-110">父元素</span><span class="sxs-lookup"><span data-stu-id="a501b-110">Parent element</span></span>

|     | <span data-ttu-id="a501b-111">描述</span><span class="sxs-lookup"><span data-stu-id="a501b-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a501b-112"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="a501b-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="a501b-113">包含自定义应用程序设置，如文件路径、 XML Web service Url 或任何其他自定义应用程序配置信息。</span><span class="sxs-lookup"><span data-stu-id="a501b-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a501b-114">子元素</span><span class="sxs-lookup"><span data-stu-id="a501b-114">Child elements</span></span>

<span data-ttu-id="a501b-115">None</span><span class="sxs-lookup"><span data-stu-id="a501b-115">None</span></span>

## <a name="example"></a><span data-ttu-id="a501b-116">示例</span><span class="sxs-lookup"><span data-stu-id="a501b-116">Example</span></span>

<span data-ttu-id="a501b-117">下面的示例演示如何清除自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="a501b-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="a501b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a501b-118">See also</span></span>

- [<span data-ttu-id="a501b-119">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a501b-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
