---
title: <configuration> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d522d004630dee942e24c39a936feae7dc957bd5
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300791"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="2b56c-102">\<configSections > 元素\<配置 ></span><span class="sxs-lookup"><span data-stu-id="2b56c-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="2b56c-103">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="2b56c-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="2b56c-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2b56c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2b56c-105">&nbsp;&nbsp; **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="2b56c-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="2b56c-106">特性</span><span class="sxs-lookup"><span data-stu-id="2b56c-106">Attributes</span></span>

<span data-ttu-id="2b56c-107">None</span><span class="sxs-lookup"><span data-stu-id="2b56c-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2b56c-108">父元素</span><span class="sxs-lookup"><span data-stu-id="2b56c-108">Parent element</span></span>

|     | <span data-ttu-id="2b56c-109">描述</span><span class="sxs-lookup"><span data-stu-id="2b56c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2b56c-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2b56c-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="2b56c-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2b56c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2b56c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b56c-112">Child elements</span></span>

|     | <span data-ttu-id="2b56c-113">描述</span><span class="sxs-lookup"><span data-stu-id="2b56c-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2b56c-114"> *\*\<section>** </span><span class="sxs-lookup"><span data-stu-id="2b56c-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="2b56c-115">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="2b56c-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="2b56c-116"> *\*\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="2b56c-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="2b56c-117">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="2b56c-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="2b56c-118"> *\*\<remove>** </span><span class="sxs-lookup"><span data-stu-id="2b56c-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="2b56c-119">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="2b56c-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="2b56c-120"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="2b56c-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="2b56c-121">清除所有以前定义的节和节组。</span><span class="sxs-lookup"><span data-stu-id="2b56c-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2b56c-122">备注</span><span class="sxs-lookup"><span data-stu-id="2b56c-122">Remarks</span></span>

<span data-ttu-id="2b56c-123">如果此元素是在配置文件中，它必须是第一个子元素 **\<配置 >** 元素。</span><span class="sxs-lookup"><span data-stu-id="2b56c-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="2b56c-124">示例</span><span class="sxs-lookup"><span data-stu-id="2b56c-124">Example</span></span>

<span data-ttu-id="2b56c-125">下面的示例演示如何定义配置节和定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="2b56c-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2b56c-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="2b56c-126">Configuration file</span></span>

<span data-ttu-id="2b56c-127">在应用程序配置文件中，计算机配置文件可以使用此元素 (*Machine.config*)，并*Web.config*不在应用程序目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="2b56c-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b56c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b56c-128">See also</span></span>

- [<span data-ttu-id="2b56c-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2b56c-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
