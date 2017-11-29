---
title: "NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9722493ec62952d7cbc07d478687b8495d24f95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="97c66-102">NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素</span><span class="sxs-lookup"><span data-stu-id="97c66-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="97c66-103">定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="97c66-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="97c66-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="97c66-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="97c66-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="97c66-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="97c66-106">特性</span><span class="sxs-lookup"><span data-stu-id="97c66-106">Attributes</span></span>

<span data-ttu-id="97c66-107">无</span><span class="sxs-lookup"><span data-stu-id="97c66-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="97c66-108">父元素</span><span class="sxs-lookup"><span data-stu-id="97c66-108">Parent element</span></span>

|     | <span data-ttu-id="97c66-109">描述</span><span class="sxs-lookup"><span data-stu-id="97c66-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="97c66-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="97c66-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="97c66-111">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="97c66-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="97c66-112">子元素</span><span class="sxs-lookup"><span data-stu-id="97c66-112">Child elements</span></span>

|     | <span data-ttu-id="97c66-113">描述</span><span class="sxs-lookup"><span data-stu-id="97c66-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="97c66-114">[**\<添加 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md)为<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="97c66-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="97c66-115">添加自定义应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="97c66-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="97c66-116">[**\<删除 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md)为<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="97c66-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="97c66-117">删除以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="97c66-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="97c66-118">[**\<清除 >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md)为<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="97c66-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="97c66-119">清除节中的所有以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="97c66-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="97c66-120">备注</span><span class="sxs-lookup"><span data-stu-id="97c66-120">Remarks</span></span>

<span data-ttu-id="97c66-121">**\<SectionName >**元素是由定义的自定义元素**\<部分 >**中标记 **\<configSections >**元素。</span><span class="sxs-lookup"><span data-stu-id="97c66-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="97c66-122">下表显示每个配置节处理程序返回的对象 ConfigurationSettings.GetConfig 方法的类型：</span><span class="sxs-lookup"><span data-stu-id="97c66-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="97c66-123">配置节处理程序</span><span class="sxs-lookup"><span data-stu-id="97c66-123">Configuration section handler</span></span>                        | <span data-ttu-id="97c66-124">返回类型</span><span class="sxs-lookup"><span data-stu-id="97c66-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="97c66-125">示例</span><span class="sxs-lookup"><span data-stu-id="97c66-125">Example</span></span>

<span data-ttu-id="97c66-126">下面的示例演示如何声明使用的部分<xref:System.Configuration.DictionarySectionHandler>和<xref:System.Configuration.NameValueSectionHandler>类。</span><span class="sxs-lookup"><span data-stu-id="97c66-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="97c66-127">第一个自定义元素是 **\<dictionarySample >**，其中包含设置读取<xref:System.Configuration.DictionarySectionHandler>类`System.dll`程序集。</span><span class="sxs-lookup"><span data-stu-id="97c66-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="97c66-128">第二个自定义元素是 **\<mySection >**，其中包含设置读取<xref:System.Configuration.NameValueSectionHandler>类`System.dll`程序集。</span><span class="sxs-lookup"><span data-stu-id="97c66-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="97c66-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="97c66-129">Configuration file</span></span>

<span data-ttu-id="97c66-130">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="97c66-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="97c66-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="97c66-131">See also</span></span>

[<span data-ttu-id="97c66-132">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="97c66-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
