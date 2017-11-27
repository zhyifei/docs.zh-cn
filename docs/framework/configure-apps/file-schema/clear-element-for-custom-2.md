---
title: "&lt;清除&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e91c3d9693cf656a8c56c82d1997f74c2b3d64c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6031c-102">\<清除 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素</span><span class="sxs-lookup"><span data-stu-id="6031c-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6031c-103">清除节中的所有以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="6031c-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="6031c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6031c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6031c-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="6031c-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="6031c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="6031c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6031c-107">语法</span><span class="sxs-lookup"><span data-stu-id="6031c-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="6031c-108">特性</span><span class="sxs-lookup"><span data-stu-id="6031c-108">Attributes</span></span>

<span data-ttu-id="6031c-109">无</span><span class="sxs-lookup"><span data-stu-id="6031c-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6031c-110">父元素</span><span class="sxs-lookup"><span data-stu-id="6031c-110">Parent element</span></span>

|     | <span data-ttu-id="6031c-111">描述</span><span class="sxs-lookup"><span data-stu-id="6031c-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="6031c-112">**\<sectionName >**元素</span><span class="sxs-lookup"><span data-stu-id="6031c-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="6031c-113">定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="6031c-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6031c-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6031c-114">Child elements</span></span>

<span data-ttu-id="6031c-115">无</span><span class="sxs-lookup"><span data-stu-id="6031c-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6031c-116">备注</span><span class="sxs-lookup"><span data-stu-id="6031c-116">Remarks</span></span>

<span data-ttu-id="6031c-117">你可以使用**\<清除 >**元素从你在配置文件层次结构中较高级别定义的应用程序中删除所有设置。</span><span class="sxs-lookup"><span data-stu-id="6031c-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="6031c-118">示例</span><span class="sxs-lookup"><span data-stu-id="6031c-118">Example</span></span>

<span data-ttu-id="6031c-119">此示例定义计算机配置文件和应用程序配置文件，并演示如何使用**\<清除 >**清除以前中定义部分的应用程序配置文件中的元素计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="6031c-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="6031c-120">下面的计算机配置文件代码声明部分 **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="6031c-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="6031c-121">下面的应用程序配置文件代码移除中的所有设置 **\<mySection >**。</span><span class="sxs-lookup"><span data-stu-id="6031c-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="6031c-122">应用程序无法检索任何已声明中的设置中 **\<mySection >**的计算机配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="6031c-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6031c-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="6031c-123">Configuration file</span></span>

<span data-ttu-id="6031c-124">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="6031c-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6031c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6031c-125">See also</span></span>

[<span data-ttu-id="6031c-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6031c-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
