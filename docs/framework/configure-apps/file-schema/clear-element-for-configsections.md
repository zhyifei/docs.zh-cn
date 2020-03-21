---
title: <configSections> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155422"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="eed03-102">\<用于\<配置>的透明>元素</span><span class="sxs-lookup"><span data-stu-id="eed03-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="eed03-103">清除以前定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="eed03-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="eed03-104">&nbsp;[**\<配置>**](configuration-element.md)&nbsp;&nbsp;**配置>\<清晰的>** [\*\* \<\*\*](configsections-element-for-configuration.md) &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="eed03-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="eed03-105">语法</span><span class="sxs-lookup"><span data-stu-id="eed03-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="eed03-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="eed03-106">Attribute</span></span>

|           | <span data-ttu-id="eed03-107">说明</span><span class="sxs-lookup"><span data-stu-id="eed03-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="eed03-108">**name**</span><span class="sxs-lookup"><span data-stu-id="eed03-108">**name**</span></span>  | <span data-ttu-id="eed03-109">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="eed03-109">Required attribute.</span></span><br><br><span data-ttu-id="eed03-110">指定要删除的节或节组的名称。</span><span class="sxs-lookup"><span data-stu-id="eed03-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="eed03-111">父元素</span><span class="sxs-lookup"><span data-stu-id="eed03-111">Parent element</span></span>

|     | <span data-ttu-id="eed03-112">说明</span><span class="sxs-lookup"><span data-stu-id="eed03-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="eed03-113">**\<配置部分>** 元素</span><span class="sxs-lookup"><span data-stu-id="eed03-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="eed03-114">包含配置部分和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="eed03-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="eed03-115">子元素</span><span class="sxs-lookup"><span data-stu-id="eed03-115">Child elements</span></span>

<span data-ttu-id="eed03-116">无</span><span class="sxs-lookup"><span data-stu-id="eed03-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="eed03-117">备注</span><span class="sxs-lookup"><span data-stu-id="eed03-117">Remarks</span></span>

<span data-ttu-id="eed03-118">**\<清除>** 元素从应用程序中删除当前配置文件前面或配置文件层次结构中较高级别定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="eed03-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="eed03-119">示例</span><span class="sxs-lookup"><span data-stu-id="eed03-119">Example</span></span>

<span data-ttu-id="eed03-120">本示例定义计算机配置文件和应用程序配置文件，并演示如何在应用程序配置文件中使用**\<清除>** 元素来清除以前在计算机配置文件中定义的部分。</span><span class="sxs-lookup"><span data-stu-id="eed03-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="eed03-121">以下计算机配置文件代码声明两个部分，**\<示例节>\*\*\*\*\<和另一个Sample节>**，在应用程序配置文件之前读取：</span><span class="sxs-lookup"><span data-stu-id="eed03-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="eed03-122">以下应用程序配置文件代码清除以前声明的所有部分。</span><span class="sxs-lookup"><span data-stu-id="eed03-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="eed03-123">应用程序无法使用或检索在计算机配置文件中声明的任一部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="eed03-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="eed03-124">但是，它可以使用**\<另一节>** 设置，因为它在**\<明确>** 元素之后出现。</span><span class="sxs-lookup"><span data-stu-id="eed03-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="eed03-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="eed03-125">Configuration file</span></span>

<span data-ttu-id="eed03-126">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="eed03-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="eed03-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eed03-127">See also</span></span>

- [<span data-ttu-id="eed03-128">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="eed03-128">Configuration file schema for the .NET Framework</span></span>](index.md)
