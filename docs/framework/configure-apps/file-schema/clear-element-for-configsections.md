---
title: <clear> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: e8c9b0479bba839a74dff300f0766838b5d99c8d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214842"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="0cde5-102">\<清除 \<configSections > 元素 ></span><span class="sxs-lookup"><span data-stu-id="0cde5-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="0cde5-103">清除所有之前定义的部分和节组。</span><span class="sxs-lookup"><span data-stu-id="0cde5-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="0cde5-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0cde5-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="0cde5-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0cde5-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0cde5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="0cde5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0cde5-107">语法</span><span class="sxs-lookup"><span data-stu-id="0cde5-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="0cde5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="0cde5-108">Attribute</span></span>

|           | <span data-ttu-id="0cde5-109">说明</span><span class="sxs-lookup"><span data-stu-id="0cde5-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0cde5-110">name</span><span class="sxs-lookup"><span data-stu-id="0cde5-110">**name**</span></span>  | <span data-ttu-id="0cde5-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0cde5-111">Required attribute.</span></span><br><br><span data-ttu-id="0cde5-112">指定要删除的节或节组的名称。</span><span class="sxs-lookup"><span data-stu-id="0cde5-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0cde5-113">父元素</span><span class="sxs-lookup"><span data-stu-id="0cde5-113">Parent element</span></span>

|     | <span data-ttu-id="0cde5-114">说明</span><span class="sxs-lookup"><span data-stu-id="0cde5-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0cde5-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="0cde5-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="0cde5-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="0cde5-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0cde5-117">子元素</span><span class="sxs-lookup"><span data-stu-id="0cde5-117">Child elements</span></span>

<span data-ttu-id="0cde5-118">无</span><span class="sxs-lookup"><span data-stu-id="0cde5-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0cde5-119">备注</span><span class="sxs-lookup"><span data-stu-id="0cde5-119">Remarks</span></span>

<span data-ttu-id="0cde5-120">**\<clear >** 元素将从应用程序中删除之前在当前配置文件中或在配置文件层次结构中更高级别定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="0cde5-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="0cde5-121">示例</span><span class="sxs-lookup"><span data-stu-id="0cde5-121">Example</span></span>

<span data-ttu-id="0cde5-122">此示例定义了计算机配置文件和应用程序配置文件，并演示了如何使用应用程序配置文件中 **\<clear >** 元素清除之前在计算机配置文件中定义的部分。</span><span class="sxs-lookup"><span data-stu-id="0cde5-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="0cde5-123">以下计算机配置文件代码声明了两部分， **\<sampleSection >** 和 **\<anotherSampleSection >** ，它们将在应用程序配置文件之前读取：</span><span class="sxs-lookup"><span data-stu-id="0cde5-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="0cde5-124">以下应用程序配置文件代码将清除以前声明的所有部分。</span><span class="sxs-lookup"><span data-stu-id="0cde5-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="0cde5-125">应用程序不能使用或检索在计算机配置文件中声明的任一部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="0cde5-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="0cde5-126">但是，它可以使用 **\<anotherSection >** 中的设置，因为它位于 **\<clear >** 元素之后。</span><span class="sxs-lookup"><span data-stu-id="0cde5-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0cde5-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="0cde5-127">Configuration file</span></span>

<span data-ttu-id="0cde5-128">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="0cde5-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cde5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cde5-129">See also</span></span>

- [<span data-ttu-id="0cde5-130">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0cde5-130">Configuration file schema for the .NET Framework</span></span>](index.md)
