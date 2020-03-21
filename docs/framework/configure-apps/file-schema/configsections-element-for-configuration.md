---
title: <configuration> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155344"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="764aa-102">\<配置>元素，用于\<配置></span><span class="sxs-lookup"><span data-stu-id="764aa-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="764aa-103">包含配置部分和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="764aa-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="764aa-104">&nbsp;[**\<配置>**](configuration-element.md)&nbsp;**配置>\<**</span><span class="sxs-lookup"><span data-stu-id="764aa-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="764aa-105">属性</span><span class="sxs-lookup"><span data-stu-id="764aa-105">Attributes</span></span>

<span data-ttu-id="764aa-106">无</span><span class="sxs-lookup"><span data-stu-id="764aa-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="764aa-107">父元素</span><span class="sxs-lookup"><span data-stu-id="764aa-107">Parent element</span></span>

|     | <span data-ttu-id="764aa-108">说明</span><span class="sxs-lookup"><span data-stu-id="764aa-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="764aa-109">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="764aa-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="764aa-110">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="764aa-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="764aa-111">子元素</span><span class="sxs-lookup"><span data-stu-id="764aa-111">Child elements</span></span>

|     | <span data-ttu-id="764aa-112">说明</span><span class="sxs-lookup"><span data-stu-id="764aa-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="764aa-113">**\<第>节**</span><span class="sxs-lookup"><span data-stu-id="764aa-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="764aa-114">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="764aa-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="764aa-115">**\<部分组>**</span><span class="sxs-lookup"><span data-stu-id="764aa-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="764aa-116">为配置部分定义命名空间。</span><span class="sxs-lookup"><span data-stu-id="764aa-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="764aa-117">**\<删除>**</span><span class="sxs-lookup"><span data-stu-id="764aa-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="764aa-118">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="764aa-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="764aa-119">**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="764aa-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="764aa-120">清除以前定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="764aa-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="764aa-121">备注</span><span class="sxs-lookup"><span data-stu-id="764aa-121">Remarks</span></span>

<span data-ttu-id="764aa-122">如果此元素位于配置文件中，则它必须是**\<配置>** 元素的第一个子元素。</span><span class="sxs-lookup"><span data-stu-id="764aa-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="764aa-123">示例</span><span class="sxs-lookup"><span data-stu-id="764aa-123">Example</span></span>

<span data-ttu-id="764aa-124">下面的示例演示如何定义配置部分并定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="764aa-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="764aa-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="764aa-125">Configuration file</span></span>

<span data-ttu-id="764aa-126">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="764aa-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="764aa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="764aa-127">See also</span></span>

- [<span data-ttu-id="764aa-128">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="764aa-128">Configuration file schema for the .NET Framework</span></span>](index.md)
