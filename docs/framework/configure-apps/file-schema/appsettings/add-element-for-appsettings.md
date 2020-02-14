---
title: <add> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214811"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="bfcaa-102">\<为 \<appSettings 添加 > 元素 ></span><span class="sxs-lookup"><span data-stu-id="bfcaa-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="bfcaa-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-103">Adds a custom application setting.</span></span>

<span data-ttu-id="bfcaa-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bfcaa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bfcaa-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="bfcaa-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="bfcaa-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="bfcaa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bfcaa-107">语法</span><span class="sxs-lookup"><span data-stu-id="bfcaa-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="bfcaa-108">属性</span><span class="sxs-lookup"><span data-stu-id="bfcaa-108">Attributes</span></span>

|           | <span data-ttu-id="bfcaa-109">说明</span><span class="sxs-lookup"><span data-stu-id="bfcaa-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="bfcaa-110">**键**</span><span class="sxs-lookup"><span data-stu-id="bfcaa-110">**key**</span></span>   | <span data-ttu-id="bfcaa-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-111">Required attribute.</span></span><br><br><span data-ttu-id="bfcaa-112">指定要添加的密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="bfcaa-113">**value**</span><span class="sxs-lookup"><span data-stu-id="bfcaa-113">**value**</span></span> | <span data-ttu-id="bfcaa-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-114">Required attribute.</span></span><br><br><span data-ttu-id="bfcaa-115">指定要添加的键的值。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="bfcaa-116">父元素</span><span class="sxs-lookup"><span data-stu-id="bfcaa-116">Parent element</span></span>

|     | <span data-ttu-id="bfcaa-117">说明</span><span class="sxs-lookup"><span data-stu-id="bfcaa-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bfcaa-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="bfcaa-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="bfcaa-119">包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="bfcaa-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bfcaa-120">子元素</span><span class="sxs-lookup"><span data-stu-id="bfcaa-120">Child elements</span></span>

<span data-ttu-id="bfcaa-121">无</span><span class="sxs-lookup"><span data-stu-id="bfcaa-121">None</span></span>

## <a name="example"></a><span data-ttu-id="bfcaa-122">示例</span><span class="sxs-lookup"><span data-stu-id="bfcaa-122">Example</span></span>

<span data-ttu-id="bfcaa-123">下面的示例演示如何为应用程序名称添加自定义配置设置：</span><span class="sxs-lookup"><span data-stu-id="bfcaa-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="bfcaa-124">下面的示例使用 `<add>` 元素定义 ASP.NET 应用程序中的两个兼容性设置：</span><span class="sxs-lookup"><span data-stu-id="bfcaa-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="bfcaa-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfcaa-125">See also</span></span>

- [<span data-ttu-id="bfcaa-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="bfcaa-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
