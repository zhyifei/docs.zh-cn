---
title: '&lt;删除&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="d4e88-102">\<删除 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素</span><span class="sxs-lookup"><span data-stu-id="d4e88-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="d4e88-103">删除以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="d4e88-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="d4e88-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d4e88-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d4e88-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="d4e88-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="d4e88-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="d4e88-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d4e88-107">语法</span><span class="sxs-lookup"><span data-stu-id="d4e88-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="d4e88-108">特性</span><span class="sxs-lookup"><span data-stu-id="d4e88-108">Attribute</span></span>

|           | <span data-ttu-id="d4e88-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4e88-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d4e88-110">**key**</span><span class="sxs-lookup"><span data-stu-id="d4e88-110">**key**</span></span>   | <span data-ttu-id="d4e88-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d4e88-111">Required attribute.</span></span><br><br><span data-ttu-id="d4e88-112">指定要删除的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="d4e88-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d4e88-113">父元素</span><span class="sxs-lookup"><span data-stu-id="d4e88-113">Parent element</span></span>

| <span data-ttu-id="d4e88-114">元素</span><span class="sxs-lookup"><span data-stu-id="d4e88-114">Element</span></span> | <span data-ttu-id="d4e88-115">描述</span><span class="sxs-lookup"><span data-stu-id="d4e88-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="d4e88-116">**\<sectionName >** 元素</span><span class="sxs-lookup"><span data-stu-id="d4e88-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="d4e88-117">定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="d4e88-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d4e88-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d4e88-118">Child elements</span></span>

<span data-ttu-id="d4e88-119">无</span><span class="sxs-lookup"><span data-stu-id="d4e88-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d4e88-120">备注</span><span class="sxs-lookup"><span data-stu-id="d4e88-120">Remarks</span></span>

<span data-ttu-id="d4e88-121">你可以使用**\<删除 >** 元素以删除从应用程序在配置文件层次结构中较高级别定义的设置。</span><span class="sxs-lookup"><span data-stu-id="d4e88-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="d4e88-122">示例</span><span class="sxs-lookup"><span data-stu-id="d4e88-122">Example</span></span>

<span data-ttu-id="d4e88-123">下面的示例演示如何使用**\<删除 >** 删除先前在计算机配置文件中定义的设置的应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="d4e88-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="d4e88-124">下面的计算机配置文件代码声明部分 **\<mySection >** 并添加两个设置`key1`和`key2`，到它：</span><span class="sxs-lookup"><span data-stu-id="d4e88-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="d4e88-125">下面的应用程序配置文件代码移除`key2`设置从 **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="d4e88-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="d4e88-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="d4e88-126">Configuration file</span></span>

<span data-ttu-id="d4e88-127">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="d4e88-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4e88-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4e88-128">See also</span></span>

[<span data-ttu-id="d4e88-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d4e88-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
