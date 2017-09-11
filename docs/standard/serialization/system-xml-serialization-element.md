---
title: "&lt;system.xml.serialization&gt; 元素"
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
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 68d2b7385ce492c52de41abe50e00b1438fe52b6
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="7a31d-102">&lt;system.xml.serialization&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="7a31d-103">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="7a31d-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="7a31d-104">有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7a31d-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7a31d-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7a31d-105">\<configuration></span></span>  
<span data-ttu-id="7a31d-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7a31d-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a31d-107">语法</span><span class="sxs-lookup"><span data-stu-id="7a31d-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a31d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7a31d-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7a31d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a31d-110">特性</span><span class="sxs-lookup"><span data-stu-id="7a31d-110">Attributes</span></span>  
 <span data-ttu-id="7a31d-111">无。</span><span class="sxs-lookup"><span data-stu-id="7a31d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a31d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-112">Child Elements</span></span>  
  
|<span data-ttu-id="7a31d-113">元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-113">Element</span></span>|<span data-ttu-id="7a31d-114">描述</span><span class="sxs-lookup"><span data-stu-id="7a31d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a31d-115">\<dateTimeSerialization> 元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="7a31d-116">确定 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="7a31d-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="7a31d-117">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="7a31d-118">包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="7a31d-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a31d-119">父元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7a31d-120">元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-120">Element</span></span>|<span data-ttu-id="7a31d-121">描述</span><span class="sxs-lookup"><span data-stu-id="7a31d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a31d-122">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="7a31d-123">公共语言运行库和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7a31d-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a31d-124">示例</span><span class="sxs-lookup"><span data-stu-id="7a31d-124">Example</span></span>  
 <span data-ttu-id="7a31d-125">下面的代码示例演示如何指定 <xref:System.DateTime> 对象的序列化模式，以及将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的其他类型。</span><span class="sxs-lookup"><span data-stu-id="7a31d-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a31d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a31d-126">See Also</span></span>  
 <span data-ttu-id="7a31d-127"><xref:System.Xml.Serialization.XmlSchemaImporter></span><span class="sxs-lookup"><span data-stu-id="7a31d-127"><xref:System.Xml.Serialization.XmlSchemaImporter></span></span>   
 <span data-ttu-id="7a31d-128"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span><span class="sxs-lookup"><span data-stu-id="7a31d-128"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span></span>   
 <span data-ttu-id="7a31d-129">[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a31d-129">[Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) </span></span>  
 <span data-ttu-id="7a31d-130">[\<dateTimeSerialization> 元素](../../../docs/standard/serialization/datetimeserialization-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a31d-130">[\<dateTimeSerialization> Element](../../../docs/standard/serialization/datetimeserialization-element.md) </span></span>  
 <span data-ttu-id="7a31d-131">[\<schemaImporterExtensions> 元素](../../../docs/standard/serialization/schemaimporterextensions-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a31d-131">[\<schemaImporterExtensions> Element](../../../docs/standard/serialization/schemaimporterextensions-element.md) </span></span>  
 [<span data-ttu-id="7a31d-132">\<xmlSchemaImporterExtensions> 的 \<add> 元素</span><span class="sxs-lookup"><span data-stu-id="7a31d-132">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)

