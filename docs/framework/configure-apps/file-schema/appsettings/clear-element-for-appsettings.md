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
ms.openlocfilehash: c3e1c3a3cfd61a9fa8e7abdae9a25ec1bc674492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119233"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="89256-102">\<清除 \<appSettings > 元素 ></span><span class="sxs-lookup"><span data-stu-id="89256-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="89256-103">清除自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="89256-103">Clears custom application settings.</span></span>

<span data-ttu-id="89256-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="89256-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="89256-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="89256-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="89256-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="89256-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="89256-107">语法</span><span class="sxs-lookup"><span data-stu-id="89256-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="89256-108">特性</span><span class="sxs-lookup"><span data-stu-id="89256-108">Attributes</span></span>

<span data-ttu-id="89256-109">None</span><span class="sxs-lookup"><span data-stu-id="89256-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="89256-110">父元素</span><span class="sxs-lookup"><span data-stu-id="89256-110">Parent element</span></span>

|     | <span data-ttu-id="89256-111">描述</span><span class="sxs-lookup"><span data-stu-id="89256-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="89256-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="89256-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="89256-113">包含自定义应用程序设置，如文件路径、XML Web service Url 或任何其他自定义应用程序配置信息。</span><span class="sxs-lookup"><span data-stu-id="89256-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="89256-114">子元素</span><span class="sxs-lookup"><span data-stu-id="89256-114">Child elements</span></span>

<span data-ttu-id="89256-115">None</span><span class="sxs-lookup"><span data-stu-id="89256-115">None</span></span>

## <a name="example"></a><span data-ttu-id="89256-116">示例</span><span class="sxs-lookup"><span data-stu-id="89256-116">Example</span></span>

<span data-ttu-id="89256-117">下面的示例演示如何清除自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="89256-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="89256-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="89256-118">See also</span></span>

- [<span data-ttu-id="89256-119">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="89256-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
