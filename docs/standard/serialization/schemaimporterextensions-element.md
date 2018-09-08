---
title: '&lt;schemaImporterExtensions&gt; 元素'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: b5696c593fdeaabab66ea7c286c6e1309e6e8e38
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204794"
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="edf0d-102">&lt;schemaImporterExtensions&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="edf0d-103">包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="edf0d-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="edf0d-104">有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="edf0d-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf0d-105">语法</span><span class="sxs-lookup"><span data-stu-id="edf0d-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="edf0d-106">子元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-106">Child Elements</span></span>  
  
|<span data-ttu-id="edf0d-107">元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-107">Element</span></span>|<span data-ttu-id="edf0d-108">描述</span><span class="sxs-lookup"><span data-stu-id="edf0d-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edf0d-109">\<添加 > 元素\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="edf0d-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="edf0d-110">添加 <xref:System.Xml.Serialization.XmlSchemaImporter> 用来创建映射的类型。</span><span class="sxs-lookup"><span data-stu-id="edf0d-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="edf0d-111">父元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="edf0d-112">元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-112">Element</span></span>|<span data-ttu-id="edf0d-113">描述</span><span class="sxs-lookup"><span data-stu-id="edf0d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edf0d-114">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="edf0d-115">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="edf0d-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="edf0d-116">示例</span><span class="sxs-lookup"><span data-stu-id="edf0d-116">Example</span></span>  
 <span data-ttu-id="edf0d-117">下面的代码示例演示如何添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="edf0d-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edf0d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="edf0d-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="edf0d-119">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="edf0d-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="edf0d-120">\<dateTimeSerialization> 元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
- [<span data-ttu-id="edf0d-121">\<添加 > 元素\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="edf0d-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="edf0d-122">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="edf0d-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
