---
title: "&lt;configSections&gt;元素&lt;配置&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7bcf425f345a3153a83cc60e76d87b3c32d83dbe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="4294a-102">\<configSections > 元素\<配置 ></span><span class="sxs-lookup"><span data-stu-id="4294a-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="4294a-103">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="4294a-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="4294a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4294a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4294a-105">&nbsp;&nbsp;**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="4294a-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="4294a-106">特性</span><span class="sxs-lookup"><span data-stu-id="4294a-106">Attributes</span></span>

<span data-ttu-id="4294a-107">无</span><span class="sxs-lookup"><span data-stu-id="4294a-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="4294a-108">父元素</span><span class="sxs-lookup"><span data-stu-id="4294a-108">Parent element</span></span>

|     | <span data-ttu-id="4294a-109">描述</span><span class="sxs-lookup"><span data-stu-id="4294a-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4294a-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="4294a-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="4294a-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4294a-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4294a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4294a-112">Child elements</span></span>

|     | <span data-ttu-id="4294a-113">描述</span><span class="sxs-lookup"><span data-stu-id="4294a-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4294a-114">**\<部分 >**</span><span class="sxs-lookup"><span data-stu-id="4294a-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="4294a-115">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="4294a-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="4294a-116">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="4294a-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="4294a-117">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4294a-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="4294a-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="4294a-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="4294a-119">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="4294a-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="4294a-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="4294a-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="4294a-121">清除所有以前定义的节和节组。</span><span class="sxs-lookup"><span data-stu-id="4294a-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4294a-122">备注</span><span class="sxs-lookup"><span data-stu-id="4294a-122">Remarks</span></span>

<span data-ttu-id="4294a-123">如果此元素是在配置文件中，它必须是第一个子元素**\<配置 >**元素。</span><span class="sxs-lookup"><span data-stu-id="4294a-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="4294a-124">示例</span><span class="sxs-lookup"><span data-stu-id="4294a-124">Example</span></span>

<span data-ttu-id="4294a-125">下面的示例演示如何定义一个配置节和定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="4294a-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="4294a-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="4294a-126">Configuration file</span></span>

<span data-ttu-id="4294a-127">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="4294a-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4294a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4294a-128">See also</span></span>

[<span data-ttu-id="4294a-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="4294a-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
