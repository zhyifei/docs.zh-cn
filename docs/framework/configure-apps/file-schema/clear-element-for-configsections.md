---
title: '&lt;清除&gt;元素&lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 42a44d66a3f70d0572484adf4c8dd946edf2297f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752242"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="fc087-102">\<清除 > 元素\<configSections ></span><span class="sxs-lookup"><span data-stu-id="fc087-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="fc087-103">清除所有以前定义的节和节组。</span><span class="sxs-lookup"><span data-stu-id="fc087-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="fc087-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fc087-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fc087-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fc087-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="fc087-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="fc087-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fc087-107">语法</span><span class="sxs-lookup"><span data-stu-id="fc087-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="fc087-108">特性</span><span class="sxs-lookup"><span data-stu-id="fc087-108">Attribute</span></span>

|           | <span data-ttu-id="fc087-109">描述</span><span class="sxs-lookup"><span data-stu-id="fc087-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="fc087-110">**name**</span><span class="sxs-lookup"><span data-stu-id="fc087-110">**name**</span></span>  | <span data-ttu-id="fc087-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="fc087-111">Required attribute.</span></span><br><br><span data-ttu-id="fc087-112">指定的节或要删除的部分组的名称。</span><span class="sxs-lookup"><span data-stu-id="fc087-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="fc087-113">父元素</span><span class="sxs-lookup"><span data-stu-id="fc087-113">Parent element</span></span>

|     | <span data-ttu-id="fc087-114">描述</span><span class="sxs-lookup"><span data-stu-id="fc087-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc087-115">**\<configSections >** 元素</span><span class="sxs-lookup"><span data-stu-id="fc087-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="fc087-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="fc087-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="fc087-117">子元素</span><span class="sxs-lookup"><span data-stu-id="fc087-117">Child elements</span></span>

<span data-ttu-id="fc087-118">无</span><span class="sxs-lookup"><span data-stu-id="fc087-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="fc087-119">备注</span><span class="sxs-lookup"><span data-stu-id="fc087-119">Remarks</span></span>

<span data-ttu-id="fc087-120">**\<清除 >** 元素从你当前的配置文件中或在配置文件层次结构中较高级别前面定义的应用程序中删除所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="fc087-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="fc087-121">示例</span><span class="sxs-lookup"><span data-stu-id="fc087-121">Example</span></span>

<span data-ttu-id="fc087-122">此示例定义计算机配置文件和应用程序配置文件，并演示如何使用**\<清除 >** 清除以前中定义部分的应用程序配置文件中的元素计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="fc087-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="fc087-123">下面的计算机配置文件代码声明两个部分，  **\<sampleSection >** 和 **\<anotherSampleSection >**，这应用程序之前，读取配置文件：</span><span class="sxs-lookup"><span data-stu-id="fc087-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="fc087-124">下面的应用程序配置文件代码清除所有以前声明的节。</span><span class="sxs-lookup"><span data-stu-id="fc087-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="fc087-125">应用程序不能使用或检索中的各个部分的计算机配置文件中声明的设置。</span><span class="sxs-lookup"><span data-stu-id="fc087-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="fc087-126">但是，它可以使用从设置 **\<anotherSection >** 因为它之后**\<清除 >** 元素。</span><span class="sxs-lookup"><span data-stu-id="fc087-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="fc087-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="fc087-127">Configuration file</span></span>

<span data-ttu-id="fc087-128">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="fc087-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc087-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc087-129">See also</span></span>

[<span data-ttu-id="fc087-130">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="fc087-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
