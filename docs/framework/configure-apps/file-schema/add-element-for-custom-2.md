---
title: "&lt;添加&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e29d0007820bb0218338394fe199e7acfd66344e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="19f69-102">\<添加 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素</span><span class="sxs-lookup"><span data-stu-id="19f69-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="19f69-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="19f69-103">Adds custom application settings.</span></span> <span data-ttu-id="19f69-104">每个**\<添加 >**标记包含键/值对。</span><span class="sxs-lookup"><span data-stu-id="19f69-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="19f69-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="19f69-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="19f69-106">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="19f69-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="19f69-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="19f69-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="19f69-108">语法</span><span class="sxs-lookup"><span data-stu-id="19f69-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="19f69-109">特性</span><span class="sxs-lookup"><span data-stu-id="19f69-109">Attributes</span></span>

| <span data-ttu-id="19f69-110">特性</span><span class="sxs-lookup"><span data-stu-id="19f69-110">Attribute</span></span> | <span data-ttu-id="19f69-111">描述</span><span class="sxs-lookup"><span data-stu-id="19f69-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="19f69-112">**key**</span><span class="sxs-lookup"><span data-stu-id="19f69-112">**key**</span></span>   | <span data-ttu-id="19f69-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="19f69-113">Required attribute.</span></span><br><br><span data-ttu-id="19f69-114">指定设置的名称。</span><span class="sxs-lookup"><span data-stu-id="19f69-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="19f69-115">**值**</span><span class="sxs-lookup"><span data-stu-id="19f69-115">**value**</span></span> | <span data-ttu-id="19f69-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="19f69-116">Required attribute.</span></span><br><br><span data-ttu-id="19f69-117">指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="19f69-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="19f69-118">父元素</span><span class="sxs-lookup"><span data-stu-id="19f69-118">Parent element</span></span>

| <span data-ttu-id="19f69-119">元素</span><span class="sxs-lookup"><span data-stu-id="19f69-119">Element</span></span> | <span data-ttu-id="19f69-120">描述</span><span class="sxs-lookup"><span data-stu-id="19f69-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="19f69-121">**\<sectionName >**元素</span><span class="sxs-lookup"><span data-stu-id="19f69-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="19f69-122">定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="19f69-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="19f69-123">子元素</span><span class="sxs-lookup"><span data-stu-id="19f69-123">Child elements</span></span>

<span data-ttu-id="19f69-124">无</span><span class="sxs-lookup"><span data-stu-id="19f69-124">None</span></span>

## <a name="example"></a><span data-ttu-id="19f69-125">示例</span><span class="sxs-lookup"><span data-stu-id="19f69-125">Example</span></span>

<span data-ttu-id="19f69-126">下面的示例演示如何定义自定义配置节以及如何使用**\<添加 >**元素将设置放入部分：</span><span class="sxs-lookup"><span data-stu-id="19f69-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="19f69-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="19f69-127">Configuration file</span></span>

<span data-ttu-id="19f69-128">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="19f69-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="19f69-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="19f69-129">See also</span></span>

[<span data-ttu-id="19f69-130">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="19f69-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
