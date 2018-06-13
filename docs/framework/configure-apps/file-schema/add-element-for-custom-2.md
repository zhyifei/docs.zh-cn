---
title: '&lt;添加&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: aeb3e3a4be201369ca2df8d231498dd2400d3c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361366"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b5fef-102">\<添加 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素</span><span class="sxs-lookup"><span data-stu-id="b5fef-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b5fef-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="b5fef-103">Adds custom application settings.</span></span> <span data-ttu-id="b5fef-104">每个**\<添加 >** 标记包含键/值对。</span><span class="sxs-lookup"><span data-stu-id="b5fef-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="b5fef-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b5fef-106">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="b5fef-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="b5fef-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b5fef-108">语法</span><span class="sxs-lookup"><span data-stu-id="b5fef-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="b5fef-109">特性</span><span class="sxs-lookup"><span data-stu-id="b5fef-109">Attributes</span></span>

| <span data-ttu-id="b5fef-110">特性</span><span class="sxs-lookup"><span data-stu-id="b5fef-110">Attribute</span></span> | <span data-ttu-id="b5fef-111">描述</span><span class="sxs-lookup"><span data-stu-id="b5fef-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b5fef-112">**key**</span><span class="sxs-lookup"><span data-stu-id="b5fef-112">**key**</span></span>   | <span data-ttu-id="b5fef-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b5fef-113">Required attribute.</span></span><br><br><span data-ttu-id="b5fef-114">指定设置的名称。</span><span class="sxs-lookup"><span data-stu-id="b5fef-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="b5fef-115">**value**</span><span class="sxs-lookup"><span data-stu-id="b5fef-115">**value**</span></span> | <span data-ttu-id="b5fef-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b5fef-116">Required attribute.</span></span><br><br><span data-ttu-id="b5fef-117">指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="b5fef-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b5fef-118">父元素</span><span class="sxs-lookup"><span data-stu-id="b5fef-118">Parent element</span></span>

| <span data-ttu-id="b5fef-119">元素</span><span class="sxs-lookup"><span data-stu-id="b5fef-119">Element</span></span> | <span data-ttu-id="b5fef-120">描述</span><span class="sxs-lookup"><span data-stu-id="b5fef-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="b5fef-121">**\<sectionName >** 元素</span><span class="sxs-lookup"><span data-stu-id="b5fef-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="b5fef-122">定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="b5fef-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b5fef-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b5fef-123">Child elements</span></span>

<span data-ttu-id="b5fef-124">无</span><span class="sxs-lookup"><span data-stu-id="b5fef-124">None</span></span>

## <a name="example"></a><span data-ttu-id="b5fef-125">示例</span><span class="sxs-lookup"><span data-stu-id="b5fef-125">Example</span></span>

<span data-ttu-id="b5fef-126">下面的示例演示如何定义自定义配置节以及如何使用**\<添加 >** 元素将设置放入部分：</span><span class="sxs-lookup"><span data-stu-id="b5fef-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b5fef-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="b5fef-127">Configuration file</span></span>

<span data-ttu-id="b5fef-128">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="b5fef-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5fef-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5fef-129">See also</span></span>

[<span data-ttu-id="b5fef-130">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b5fef-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
