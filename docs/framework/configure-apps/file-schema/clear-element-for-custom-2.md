---
title: <clear>NameValueSectionHandler 和 DictionarySectionHandler 的元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927711"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="c0203-102">\<清除 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素</span><span class="sxs-lookup"><span data-stu-id="c0203-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="c0203-103">清除节中所有先前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="c0203-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="c0203-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c0203-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="c0203-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="c0203-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="c0203-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="c0203-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c0203-107">语法</span><span class="sxs-lookup"><span data-stu-id="c0203-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="c0203-108">特性</span><span class="sxs-lookup"><span data-stu-id="c0203-108">Attributes</span></span>

<span data-ttu-id="c0203-109">无</span><span class="sxs-lookup"><span data-stu-id="c0203-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="c0203-110">父元素</span><span class="sxs-lookup"><span data-stu-id="c0203-110">Parent element</span></span>

|     | <span data-ttu-id="c0203-111">描述</span><span class="sxs-lookup"><span data-stu-id="c0203-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="c0203-112"> **sectionName>\<** 元素</span><span class="sxs-lookup"><span data-stu-id="c0203-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="c0203-113">定义使用<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类的自定义配置节的设置。</span><span class="sxs-lookup"><span data-stu-id="c0203-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c0203-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c0203-114">Child elements</span></span>

<span data-ttu-id="c0203-115">无</span><span class="sxs-lookup"><span data-stu-id="c0203-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c0203-116">备注</span><span class="sxs-lookup"><span data-stu-id="c0203-116">Remarks</span></span>

<span data-ttu-id="c0203-117">你可以使用 **\<clear >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c0203-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="c0203-118">示例</span><span class="sxs-lookup"><span data-stu-id="c0203-118">Example</span></span>

<span data-ttu-id="c0203-119">此示例定义了计算机配置文件和应用程序配置文件, 并演示了如何使用应用程序配置文件中的 **\<clear >** 元素清除之前在计算机配置中定义的部分文件.</span><span class="sxs-lookup"><span data-stu-id="c0203-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="c0203-120">以下计算机配置文件代码声明了 **\<mySection >** 部分:</span><span class="sxs-lookup"><span data-stu-id="c0203-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="c0203-121">以下应用程序配置文件代码将从 **\<mySection >** 删除所有设置。</span><span class="sxs-lookup"><span data-stu-id="c0203-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="c0203-122">应用程序无法检索在计算机配置文件的 **\<mySection >** 部分中的中声明的任何设置。</span><span class="sxs-lookup"><span data-stu-id="c0203-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c0203-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="c0203-123">Configuration file</span></span>

<span data-ttu-id="c0203-124">此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c0203-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0203-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0203-125">See also</span></span>

- [<span data-ttu-id="c0203-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c0203-126">Configuration file schema for the .NET Framework</span></span>](index.md)
