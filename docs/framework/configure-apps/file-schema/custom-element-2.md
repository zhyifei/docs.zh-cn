---
title: NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921043"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="9cd19-102">NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素</span><span class="sxs-lookup"><span data-stu-id="9cd19-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="9cd19-103">定义使用<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类的自定义配置节的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="9cd19-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9cd19-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="9cd19-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="9cd19-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="9cd19-106">特性</span><span class="sxs-lookup"><span data-stu-id="9cd19-106">Attributes</span></span>

<span data-ttu-id="9cd19-107">无</span><span class="sxs-lookup"><span data-stu-id="9cd19-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9cd19-108">父元素</span><span class="sxs-lookup"><span data-stu-id="9cd19-108">Parent element</span></span>

|     | <span data-ttu-id="9cd19-109">描述</span><span class="sxs-lookup"><span data-stu-id="9cd19-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9cd19-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9cd19-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="9cd19-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9cd19-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9cd19-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9cd19-112">Child elements</span></span>

|     | <span data-ttu-id="9cd19-113">描述</span><span class="sxs-lookup"><span data-stu-id="9cd19-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="9cd19-114">为和添加 > [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="9cd19-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="9cd19-115">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="9cd19-116">删除和的 > [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="9cd19-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="9cd19-117">删除以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="9cd19-118">清除和的 > [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="9cd19-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="9cd19-119">清除节中所有先前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9cd19-120">备注</span><span class="sxs-lookup"><span data-stu-id="9cd19-120">Remarks</span></span>

<span data-ttu-id="9cd19-121">**\<SectionName>** 元素是通过定义的自定义元素 **\<部分>** 标记中的 **\<configSections>** 元素。</span><span class="sxs-lookup"><span data-stu-id="9cd19-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="9cd19-122">下表显示 ConfigurationSettings. GetConfig 方法为每个配置节处理程序返回的对象类型:</span><span class="sxs-lookup"><span data-stu-id="9cd19-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="9cd19-123">配置节处理程序</span><span class="sxs-lookup"><span data-stu-id="9cd19-123">Configuration section handler</span></span>                        | <span data-ttu-id="9cd19-124">返回类型</span><span class="sxs-lookup"><span data-stu-id="9cd19-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="9cd19-125">示例</span><span class="sxs-lookup"><span data-stu-id="9cd19-125">Example</span></span>

<span data-ttu-id="9cd19-126">下面的示例演示如何声明使用<xref:System.Configuration.DictionarySectionHandler>和<xref:System.Configuration.NameValueSectionHandler>类的节。</span><span class="sxs-lookup"><span data-stu-id="9cd19-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="9cd19-127">第一个自定义元素是 **\<dictionarySample >** , 它包含由`System.dll`程序集中<xref:System.Configuration.DictionarySectionHandler>的类读取的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="9cd19-128">第二个自定义元素是 **\<mySection >** , 它包含由`System.dll`程序<xref:System.Configuration.NameValueSectionHandler>集中的类读取的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd19-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="9cd19-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="9cd19-129">Configuration file</span></span>

<span data-ttu-id="9cd19-130">此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="9cd19-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cd19-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cd19-131">See also</span></span>

- [<span data-ttu-id="9cd19-132">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9cd19-132">Configuration file schema for the .NET Framework</span></span>](index.md)
