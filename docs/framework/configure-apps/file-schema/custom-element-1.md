---
title: 单一标签节处理程序的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 0d765a9789ad566428b1fbda6c0863b10b98c363
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345065"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="0cdab-102">单一标签节处理程序的自定义元素</span><span class="sxs-lookup"><span data-stu-id="0cdab-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="0cdab-103">在由\<节>元素定义的自定义配置部分中定义设置，并使用类<xref:System.Configuration.SingleTagSectionHandler>。</span><span class="sxs-lookup"><span data-stu-id="0cdab-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="0cdab-104">&nbsp;[**\<配置>**](configuration-element.md)&nbsp;*节名称>\<*</span><span class="sxs-lookup"><span data-stu-id="0cdab-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="0cdab-105">语法</span><span class="sxs-lookup"><span data-stu-id="0cdab-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="0cdab-106">特性</span><span class="sxs-lookup"><span data-stu-id="0cdab-106">Attributes</span></span>

<span data-ttu-id="0cdab-107">属性和属性值是用户定义的。</span><span class="sxs-lookup"><span data-stu-id="0cdab-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="0cdab-108">父元素</span><span class="sxs-lookup"><span data-stu-id="0cdab-108">Parent element</span></span>

|     | <span data-ttu-id="0cdab-109">描述</span><span class="sxs-lookup"><span data-stu-id="0cdab-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0cdab-110">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="0cdab-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="0cdab-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="0cdab-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0cdab-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0cdab-112">Child elements</span></span>

<span data-ttu-id="0cdab-113">无</span><span class="sxs-lookup"><span data-stu-id="0cdab-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0cdab-114">备注</span><span class="sxs-lookup"><span data-stu-id="0cdab-114">Remarks</span></span>

<span data-ttu-id="0cdab-115">**\<节名称>** 元素是由[**\<配置节>**](configsections-element-for-configuration.md)元素中[**\<>**](section-element.md)标记定义的自定义元素。</span><span class="sxs-lookup"><span data-stu-id="0cdab-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="0cdab-116">当您调用<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时，<xref:System.Collections.IDictionary>配置系统将返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="0cdab-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="0cdab-117">示例</span><span class="sxs-lookup"><span data-stu-id="0cdab-117">Example</span></span>

<span data-ttu-id="0cdab-118">以下示例声明一个称为**\<示例节>** 的自定义元素，其中包含类读取的<xref:System.Configuration.SingleTagSectionHandler>设置：</span><span class="sxs-lookup"><span data-stu-id="0cdab-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0cdab-119">配置文件</span><span class="sxs-lookup"><span data-stu-id="0cdab-119">Configuration file</span></span>

<span data-ttu-id="0cdab-120">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="0cdab-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cdab-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cdab-121">See also</span></span>

- [<span data-ttu-id="0cdab-122">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0cdab-122">Configuration file schema for the .NET Framework</span></span>](index.md)
