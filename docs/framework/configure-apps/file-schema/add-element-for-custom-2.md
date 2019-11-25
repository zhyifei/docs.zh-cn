---
title: NameValueSectionHandler 和 DictionarySectionHandler 的 <add> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac07fc9ba6f030209a5e0d0160689fab95bc1b4a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088768"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6a6d9-102">\<添加 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素</span><span class="sxs-lookup"><span data-stu-id="6a6d9-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6a6d9-103">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-103">Adds custom application settings.</span></span> <span data-ttu-id="6a6d9-104">每个 **\<添加 >** 标记包含一个键/值对。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="6a6d9-105">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a6d9-105">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="6a6d9-106">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="6a6d9-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="6a6d9-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6a6d9-108">语法</span><span class="sxs-lookup"><span data-stu-id="6a6d9-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="6a6d9-109">特性</span><span class="sxs-lookup"><span data-stu-id="6a6d9-109">Attributes</span></span>

| <span data-ttu-id="6a6d9-110">特性</span><span class="sxs-lookup"><span data-stu-id="6a6d9-110">Attribute</span></span> | <span data-ttu-id="6a6d9-111">描述</span><span class="sxs-lookup"><span data-stu-id="6a6d9-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6a6d9-112">**key**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-112">**key**</span></span>   | <span data-ttu-id="6a6d9-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-113">Required attribute.</span></span><br><br><span data-ttu-id="6a6d9-114">指定设置的名称。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="6a6d9-115">**value**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-115">**value**</span></span> | <span data-ttu-id="6a6d9-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-116">Required attribute.</span></span><br><br><span data-ttu-id="6a6d9-117">指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6a6d9-118">父元素</span><span class="sxs-lookup"><span data-stu-id="6a6d9-118">Parent element</span></span>

| <span data-ttu-id="6a6d9-119">元素</span><span class="sxs-lookup"><span data-stu-id="6a6d9-119">Element</span></span> | <span data-ttu-id="6a6d9-120">描述</span><span class="sxs-lookup"><span data-stu-id="6a6d9-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="6a6d9-121"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="6a6d9-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="6a6d9-122">定义使用 <xref:System.Configuration.NameValueSectionHandler> 和 <xref:System.Configuration.DictionarySectionHandler> 类的自定义配置节的设置。</span><span class="sxs-lookup"><span data-stu-id="6a6d9-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6a6d9-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6a6d9-123">Child elements</span></span>

<span data-ttu-id="6a6d9-124">None</span><span class="sxs-lookup"><span data-stu-id="6a6d9-124">None</span></span>

## <a name="example"></a><span data-ttu-id="6a6d9-125">示例</span><span class="sxs-lookup"><span data-stu-id="6a6d9-125">Example</span></span>

<span data-ttu-id="6a6d9-126">下面的示例演示如何定义自定义配置节，并使用 **\<添加 >** 元素将设置放入部分：</span><span class="sxs-lookup"><span data-stu-id="6a6d9-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="6a6d9-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="6a6d9-127">Configuration file</span></span>

<span data-ttu-id="6a6d9-128">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="6a6d9-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a6d9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a6d9-129">See also</span></span>

- [<span data-ttu-id="6a6d9-130">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6a6d9-130">Configuration file schema for the .NET Framework</span></span>](index.md)
