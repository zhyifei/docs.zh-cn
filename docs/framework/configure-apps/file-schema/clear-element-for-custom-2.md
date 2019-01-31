---
title: <clear> NameValueSectionHandler 和 DictionarySectionHandler 的元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ad3ac93b2a7f92cd33787620fc0caa2b632aa072
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281870"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5cc19-102">\<清除 > NameValueSectionHandler 和 DictionarySectionHandler 的元素</span><span class="sxs-lookup"><span data-stu-id="5cc19-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5cc19-103">清除部分中的所有以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="5cc19-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="5cc19-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5cc19-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5cc19-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="5cc19-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="5cc19-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="5cc19-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5cc19-107">语法</span><span class="sxs-lookup"><span data-stu-id="5cc19-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="5cc19-108">特性</span><span class="sxs-lookup"><span data-stu-id="5cc19-108">Attributes</span></span>

<span data-ttu-id="5cc19-109">无</span><span class="sxs-lookup"><span data-stu-id="5cc19-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="5cc19-110">父元素</span><span class="sxs-lookup"><span data-stu-id="5cc19-110">Parent element</span></span>

|     | <span data-ttu-id="5cc19-111">描述</span><span class="sxs-lookup"><span data-stu-id="5cc19-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="5cc19-112">**\<sectionName >** 元素</span><span class="sxs-lookup"><span data-stu-id="5cc19-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="5cc19-113">定义使用的自定义配置部分设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="5cc19-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5cc19-114">子元素</span><span class="sxs-lookup"><span data-stu-id="5cc19-114">Child elements</span></span>

<span data-ttu-id="5cc19-115">无</span><span class="sxs-lookup"><span data-stu-id="5cc19-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5cc19-116">备注</span><span class="sxs-lookup"><span data-stu-id="5cc19-116">Remarks</span></span>

<span data-ttu-id="5cc19-117">可以使用**\<清除 >** 元素从你在配置文件层次结构中较高级别定义的应用程序中删除所有设置。</span><span class="sxs-lookup"><span data-stu-id="5cc19-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5cc19-118">示例</span><span class="sxs-lookup"><span data-stu-id="5cc19-118">Example</span></span>

<span data-ttu-id="5cc19-119">此示例定义了计算机配置文件和应用程序配置文件，演示如何使用**\<清除 >** 清除以前在中定义的部分应用程序配置文件中的元素计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="5cc19-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5cc19-120">下面的计算机配置文件代码声明部分 **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="5cc19-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="5cc19-121">下面的应用程序配置文件代码删除所有设置从 **\<mySection >**。</span><span class="sxs-lookup"><span data-stu-id="5cc19-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="5cc19-122">应用程序无法检索的任何声明，因此在设置中 **\<mySection >** 部分中的计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="5cc19-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5cc19-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="5cc19-123">Configuration file</span></span>

<span data-ttu-id="5cc19-124">在应用程序配置文件中，计算机配置文件可以使用此元素 (*Machine.config*)，并*Web.config*不在应用程序目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="5cc19-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cc19-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cc19-125">See also</span></span>

- [<span data-ttu-id="5cc19-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="5cc19-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
