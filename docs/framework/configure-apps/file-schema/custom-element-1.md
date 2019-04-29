---
title: Singletagsectionhandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bfc2a916e37ac27d45746eb268912b3752f4d80f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705293"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="f77a7-102">Singletagsectionhandler 的自定义元素</span><span class="sxs-lookup"><span data-stu-id="f77a7-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="f77a7-103">在定义的自定义配置节中定义设置\<部分 > 元素，并使用<xref:System.Configuration.SingleTagSectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="f77a7-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="f77a7-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f77a7-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f77a7-105">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="f77a7-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="f77a7-106">语法</span><span class="sxs-lookup"><span data-stu-id="f77a7-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="f77a7-107">特性</span><span class="sxs-lookup"><span data-stu-id="f77a7-107">Attributes</span></span>

<span data-ttu-id="f77a7-108">属性和属性值是用户定义的。</span><span class="sxs-lookup"><span data-stu-id="f77a7-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="f77a7-109">父元素</span><span class="sxs-lookup"><span data-stu-id="f77a7-109">Parent element</span></span>

|     | <span data-ttu-id="f77a7-110">描述</span><span class="sxs-lookup"><span data-stu-id="f77a7-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f77a7-111">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="f77a7-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="f77a7-112">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f77a7-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f77a7-113">子元素</span><span class="sxs-lookup"><span data-stu-id="f77a7-113">Child elements</span></span>

<span data-ttu-id="f77a7-114">None</span><span class="sxs-lookup"><span data-stu-id="f77a7-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f77a7-115">备注</span><span class="sxs-lookup"><span data-stu-id="f77a7-115">Remarks</span></span>

<span data-ttu-id="f77a7-116"> *\*\<SectionName >** 元素是通过定义的自定义元素[ *\*\<部分 >** ](~/docs/framework/configure-apps/file-schema/section-element.md)标记中的[ *\*\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f77a7-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="f77a7-117">配置系统返回<xref:System.Collections.IDictionary>对象在调用时<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f77a7-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="f77a7-118">示例</span><span class="sxs-lookup"><span data-stu-id="f77a7-118">Example</span></span>

<span data-ttu-id="f77a7-119">下面的示例声明一个名为自定义元素 **\<sampleSection >** ，其中包含通过读取设置<xref:System.Configuration.SingleTagSectionHandler>类：</span><span class="sxs-lookup"><span data-stu-id="f77a7-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="f77a7-120">配置文件</span><span class="sxs-lookup"><span data-stu-id="f77a7-120">Configuration file</span></span>

<span data-ttu-id="f77a7-121">在应用程序配置文件中，计算机配置文件可以使用此元素 (*Machine.config*)，并*Web.config*不在应用程序目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="f77a7-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f77a7-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f77a7-122">See also</span></span>

- [<span data-ttu-id="f77a7-123">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f77a7-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
