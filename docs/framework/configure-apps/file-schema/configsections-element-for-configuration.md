---
title: <configSections> 的 <configuration> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214823"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="747ec-102">\<配置 \<configSections > 元素 ></span><span class="sxs-lookup"><span data-stu-id="747ec-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="747ec-103">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="747ec-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="747ec-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="747ec-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="747ec-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="747ec-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="747ec-106">属性</span><span class="sxs-lookup"><span data-stu-id="747ec-106">Attributes</span></span>

<span data-ttu-id="747ec-107">无</span><span class="sxs-lookup"><span data-stu-id="747ec-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="747ec-108">父元素</span><span class="sxs-lookup"><span data-stu-id="747ec-108">Parent element</span></span>

|     | <span data-ttu-id="747ec-109">说明</span><span class="sxs-lookup"><span data-stu-id="747ec-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="747ec-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="747ec-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="747ec-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="747ec-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="747ec-112">子元素</span><span class="sxs-lookup"><span data-stu-id="747ec-112">Child elements</span></span>

|     | <span data-ttu-id="747ec-113">说明</span><span class="sxs-lookup"><span data-stu-id="747ec-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="747ec-114"> **\<部分 >** </span><span class="sxs-lookup"><span data-stu-id="747ec-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="747ec-115">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="747ec-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="747ec-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="747ec-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="747ec-117">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="747ec-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="747ec-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="747ec-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="747ec-119">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="747ec-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="747ec-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="747ec-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="747ec-121">清除所有之前定义的部分和节组。</span><span class="sxs-lookup"><span data-stu-id="747ec-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="747ec-122">备注</span><span class="sxs-lookup"><span data-stu-id="747ec-122">Remarks</span></span>

<span data-ttu-id="747ec-123">如果此元素在配置文件中，则它必须是 **\<配置 >** 元素的第一个子元素。</span><span class="sxs-lookup"><span data-stu-id="747ec-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="747ec-124">示例</span><span class="sxs-lookup"><span data-stu-id="747ec-124">Example</span></span>

<span data-ttu-id="747ec-125">下面的示例演示如何定义配置节并定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="747ec-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="747ec-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="747ec-126">Configuration file</span></span>

<span data-ttu-id="747ec-127">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="747ec-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="747ec-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="747ec-128">See also</span></span>

- [<span data-ttu-id="747ec-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="747ec-129">Configuration file schema for the .NET Framework</span></span>](index.md)
