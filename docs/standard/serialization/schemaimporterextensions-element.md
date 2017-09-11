---
title: "&lt;schemaImporterExtensions&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: cf9ef09f514f38c0250c288e347d28d73caab295
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="10af8-102">&lt;schemaImporterExtensions&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="10af8-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="10af8-103">包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="10af8-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="10af8-104">有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="10af8-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10af8-105">语法</span><span class="sxs-lookup"><span data-stu-id="10af8-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="10af8-106">子元素</span><span class="sxs-lookup"><span data-stu-id="10af8-106">Child Elements</span></span>  
  
|<span data-ttu-id="10af8-107">元素</span><span class="sxs-lookup"><span data-stu-id="10af8-107">Element</span></span>|<span data-ttu-id="10af8-108">描述</span><span class="sxs-lookup"><span data-stu-id="10af8-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10af8-109">\<xmlSchemaImporterExtensions> 的 \<add> 元素</span><span class="sxs-lookup"><span data-stu-id="10af8-109">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)|<span data-ttu-id="10af8-110">添加 <xref:System.Xml.Serialization.XmlSchemaImporter> 用来创建映射的类型。</span><span class="sxs-lookup"><span data-stu-id="10af8-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="10af8-111">父元素</span><span class="sxs-lookup"><span data-stu-id="10af8-111">Parent Elements</span></span>  
  
|<span data-ttu-id="10af8-112">元素</span><span class="sxs-lookup"><span data-stu-id="10af8-112">Element</span></span>|<span data-ttu-id="10af8-113">描述</span><span class="sxs-lookup"><span data-stu-id="10af8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10af8-114">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="10af8-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="10af8-115">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="10af8-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10af8-116">示例</span><span class="sxs-lookup"><span data-stu-id="10af8-116">Example</span></span>  
 <span data-ttu-id="10af8-117">下面的代码示例演示如何添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="10af8-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10af8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10af8-118">See Also</span></span>  
 <span data-ttu-id="10af8-119"><xref:System.Xml.Serialization.XmlSchemaImporter></span><span class="sxs-lookup"><span data-stu-id="10af8-119"><xref:System.Xml.Serialization.XmlSchemaImporter></span></span>   
 <span data-ttu-id="10af8-120"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span><span class="sxs-lookup"><span data-stu-id="10af8-120"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span></span>   
 <span data-ttu-id="10af8-121">[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md) </span><span class="sxs-lookup"><span data-stu-id="10af8-121">[Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) </span></span>  
 <span data-ttu-id="10af8-122">[\<dateTimeSerialization> 元素](../../../docs/standard/serialization/datetimeserialization-element.md) </span><span class="sxs-lookup"><span data-stu-id="10af8-122">[\<dateTimeSerialization> Element](../../../docs/standard/serialization/datetimeserialization-element.md) </span></span>  
 <span data-ttu-id="10af8-123">[\<xmlSchemaImporterExtensions> 的 \<add> 元素](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md) </span><span class="sxs-lookup"><span data-stu-id="10af8-123">[\<add> Element for \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md) </span></span>  
 [<span data-ttu-id="10af8-124">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="10af8-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)

