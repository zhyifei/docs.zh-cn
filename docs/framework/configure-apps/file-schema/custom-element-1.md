---
title: SingleTagSectionHandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac2d01121e81b545556fb082fa7b82c31cccf9da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118838"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="504ce-102">SingleTagSectionHandler 的自定义元素</span><span class="sxs-lookup"><span data-stu-id="504ce-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="504ce-103">定义自定义配置节中由 \<节 > 元素定义并使用 <xref:System.Configuration.SingleTagSectionHandler> 类的设置。</span><span class="sxs-lookup"><span data-stu-id="504ce-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="504ce-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="504ce-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="504ce-105">&nbsp;&nbsp; *\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="504ce-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="504ce-106">语法</span><span class="sxs-lookup"><span data-stu-id="504ce-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="504ce-107">特性</span><span class="sxs-lookup"><span data-stu-id="504ce-107">Attributes</span></span>

<span data-ttu-id="504ce-108">属性和属性值是用户定义的。</span><span class="sxs-lookup"><span data-stu-id="504ce-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="504ce-109">父元素</span><span class="sxs-lookup"><span data-stu-id="504ce-109">Parent element</span></span>

|     | <span data-ttu-id="504ce-110">描述</span><span class="sxs-lookup"><span data-stu-id="504ce-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="504ce-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="504ce-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="504ce-112">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="504ce-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="504ce-113">子元素</span><span class="sxs-lookup"><span data-stu-id="504ce-113">Child elements</span></span>

<span data-ttu-id="504ce-114">None</span><span class="sxs-lookup"><span data-stu-id="504ce-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="504ce-115">备注</span><span class="sxs-lookup"><span data-stu-id="504ce-115">Remarks</span></span>

<span data-ttu-id="504ce-116">**\<sectionName >** 元素是一个自定义元素，该元素由[ **\<节 >** ](section-element.md)标记在[ **\<configSections >** ](configsections-element-for-configuration.md)元素中定义。</span><span class="sxs-lookup"><span data-stu-id="504ce-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="504ce-117">调用 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时，配置系统将返回 <xref:System.Collections.IDictionary> 对象。</span><span class="sxs-lookup"><span data-stu-id="504ce-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="504ce-118">示例</span><span class="sxs-lookup"><span data-stu-id="504ce-118">Example</span></span>

<span data-ttu-id="504ce-119">下面的示例声明一个名为 **\<sampleSection >** 的自定义元素，该元素包含由 <xref:System.Configuration.SingleTagSectionHandler> 类读取的设置：</span><span class="sxs-lookup"><span data-stu-id="504ce-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="504ce-120">配置文件</span><span class="sxs-lookup"><span data-stu-id="504ce-120">Configuration file</span></span>

<span data-ttu-id="504ce-121">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="504ce-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="504ce-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="504ce-122">See also</span></span>

- [<span data-ttu-id="504ce-123">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="504ce-123">Configuration file schema for the .NET Framework</span></span>](index.md)
