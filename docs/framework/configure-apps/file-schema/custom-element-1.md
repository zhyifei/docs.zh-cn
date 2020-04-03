---
title: 单一标签节处理程序的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635402"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="596c5-102">单一标签节处理程序的自定义元素</span><span class="sxs-lookup"><span data-stu-id="596c5-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="596c5-103">在由\<节>元素定义的自定义配置部分中定义设置，并使用类<xref:System.Configuration.SingleTagSectionHandler>。</span><span class="sxs-lookup"><span data-stu-id="596c5-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="596c5-104">&nbsp;[**\<配置>**](configuration-element.md)&nbsp;*节名称>\<*</span><span class="sxs-lookup"><span data-stu-id="596c5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="596c5-105">语法</span><span class="sxs-lookup"><span data-stu-id="596c5-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="596c5-106">特性</span><span class="sxs-lookup"><span data-stu-id="596c5-106">Attributes</span></span>

<span data-ttu-id="596c5-107">属性和属性值是用户定义的。</span><span class="sxs-lookup"><span data-stu-id="596c5-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="596c5-108">父元素</span><span class="sxs-lookup"><span data-stu-id="596c5-108">Parent element</span></span>

|     | <span data-ttu-id="596c5-109">说明</span><span class="sxs-lookup"><span data-stu-id="596c5-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="596c5-110">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="596c5-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="596c5-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="596c5-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="596c5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="596c5-112">Child elements</span></span>

<span data-ttu-id="596c5-113">无</span><span class="sxs-lookup"><span data-stu-id="596c5-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="596c5-114">备注</span><span class="sxs-lookup"><span data-stu-id="596c5-114">Remarks</span></span>

<span data-ttu-id="596c5-115">**\<节名称>** 元素是由[**\<配置节>**](configsections-element-for-configuration.md)元素中[**\<>**](section-element.md)标记定义的自定义元素。</span><span class="sxs-lookup"><span data-stu-id="596c5-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="596c5-116">当您调用<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时，<xref:System.Collections.IDictionary>配置系统将返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="596c5-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="596c5-117">示例</span><span class="sxs-lookup"><span data-stu-id="596c5-117">Example</span></span>

<span data-ttu-id="596c5-118">以下示例声明一个称为**\<示例节>** 的自定义元素，其中包含类读取的<xref:System.Configuration.SingleTagSectionHandler>设置：</span><span class="sxs-lookup"><span data-stu-id="596c5-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="596c5-119">配置文件</span><span class="sxs-lookup"><span data-stu-id="596c5-119">Configuration file</span></span>

<span data-ttu-id="596c5-120">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="596c5-120">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="596c5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="596c5-121">See also</span></span>

- [<span data-ttu-id="596c5-122">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="596c5-122">Configuration file schema for the .NET Framework</span></span>](index.md)
