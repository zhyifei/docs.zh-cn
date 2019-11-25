---
title: <appSettings> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088737"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="a6253-102">\<清除 \<appSettings > 元素 ></span><span class="sxs-lookup"><span data-stu-id="a6253-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="a6253-103">清除自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="a6253-103">Clears custom application settings.</span></span>

<span data-ttu-id="a6253-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a6253-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a6253-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a6253-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="a6253-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="a6253-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a6253-107">语法</span><span class="sxs-lookup"><span data-stu-id="a6253-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="a6253-108">特性</span><span class="sxs-lookup"><span data-stu-id="a6253-108">Attributes</span></span>

<span data-ttu-id="a6253-109">None</span><span class="sxs-lookup"><span data-stu-id="a6253-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="a6253-110">父元素</span><span class="sxs-lookup"><span data-stu-id="a6253-110">Parent element</span></span>

|     | <span data-ttu-id="a6253-111">描述</span><span class="sxs-lookup"><span data-stu-id="a6253-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a6253-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="a6253-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="a6253-113">包含自定义应用程序设置，如文件路径、XML Web service Url 或任何其他自定义应用程序配置信息。</span><span class="sxs-lookup"><span data-stu-id="a6253-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a6253-114">子元素</span><span class="sxs-lookup"><span data-stu-id="a6253-114">Child elements</span></span>

<span data-ttu-id="a6253-115">None</span><span class="sxs-lookup"><span data-stu-id="a6253-115">None</span></span>

## <a name="example"></a><span data-ttu-id="a6253-116">示例</span><span class="sxs-lookup"><span data-stu-id="a6253-116">Example</span></span>

<span data-ttu-id="a6253-117">下面的示例演示如何清除自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="a6253-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="a6253-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6253-118">See also</span></span>

- [<span data-ttu-id="a6253-119">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a6253-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
