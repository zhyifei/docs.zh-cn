---
title: "&lt;dateTimeSerialization&gt; 元素"
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
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 9ced207c17355cc9c1bd85bdada4208dea2ceb2f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="7d299-102">&lt;dateTimeSerialization&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="7d299-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="7d299-103">确定 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="7d299-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="7d299-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d299-104">\<configuration></span></span>  
<span data-ttu-id="7d299-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="7d299-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d299-106">语法</span><span class="sxs-lookup"><span data-stu-id="7d299-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d299-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d299-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7d299-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7d299-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d299-109">特性</span><span class="sxs-lookup"><span data-stu-id="7d299-109">Attributes</span></span>  
  
|<span data-ttu-id="7d299-110">特性</span><span class="sxs-lookup"><span data-stu-id="7d299-110">Attributes</span></span>|<span data-ttu-id="7d299-111">描述</span><span class="sxs-lookup"><span data-stu-id="7d299-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="7d299-112">可选。</span><span class="sxs-lookup"><span data-stu-id="7d299-112">Optional.</span></span> <span data-ttu-id="7d299-113">指定序列化模式。</span><span class="sxs-lookup"><span data-stu-id="7d299-113">Specifies the serialization mode.</span></span> <span data-ttu-id="7d299-114">设置为 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="7d299-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="7d299-115">默认值为 RoundTrip。</span><span class="sxs-lookup"><span data-stu-id="7d299-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d299-116">子元素</span><span class="sxs-lookup"><span data-stu-id="7d299-116">Child Elements</span></span>  
 <span data-ttu-id="7d299-117">无。</span><span class="sxs-lookup"><span data-stu-id="7d299-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d299-118">父元素</span><span class="sxs-lookup"><span data-stu-id="7d299-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7d299-119">元素</span><span class="sxs-lookup"><span data-stu-id="7d299-119">Element</span></span>|<span data-ttu-id="7d299-120">描述</span><span class="sxs-lookup"><span data-stu-id="7d299-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d299-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="7d299-121">system.xml.serialization</span></span>|<span data-ttu-id="7d299-122">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="7d299-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d299-123">备注</span><span class="sxs-lookup"><span data-stu-id="7d299-123">Remarks</span></span>  
 <span data-ttu-id="7d299-124">在 .NET Framework 1.0、1.1、2.0 以及更高版本中，将此属性设置为 Local 时，<xref:System.DateTime> 对象始终设置为本地时间格式。</span><span class="sxs-lookup"><span data-stu-id="7d299-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="7d299-125">即，序列化的数据中总是包含本地时区信息。</span><span class="sxs-lookup"><span data-stu-id="7d299-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="7d299-126">将此属性设置为 Local 可确保与较早版本的 .NET Framework 兼容。</span><span class="sxs-lookup"><span data-stu-id="7d299-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7d299-127">在 .NET Framework 2.0 及更高版本中，将此属性设置为 Roundtrip 时，系统会检查 <xref:System.DateTime> 对象以确定这些对象位于本地时区、UTC 时区还是未指定的时区中。</span><span class="sxs-lookup"><span data-stu-id="7d299-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="7d299-128">随后会序列化 <xref:System.DateTime> 对象并保留该信息。</span><span class="sxs-lookup"><span data-stu-id="7d299-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="7d299-129">这是默认行为，建议为所有不与 Framework 的较早版本通信的新应用程序使用此行为。</span><span class="sxs-lookup"><span data-stu-id="7d299-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d299-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d299-130">See Also</span></span>  
 <span data-ttu-id="7d299-131"><xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="7d299-131"><xref:System.DateTime></span></span>   
 <span data-ttu-id="7d299-132"><xref:System.Xml.Serialization.XmlSchemaImporter></span><span class="sxs-lookup"><span data-stu-id="7d299-132"><xref:System.Xml.Serialization.XmlSchemaImporter></span></span>   
 <span data-ttu-id="7d299-133"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span><span class="sxs-lookup"><span data-stu-id="7d299-133"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode></span></span>   
 <span data-ttu-id="7d299-134">[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d299-134">[Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) </span></span>  
 <span data-ttu-id="7d299-135">[\<schemaImporterExtensions> 元素](../../../docs/standard/serialization/schemaimporterextensions-element.md) </span><span class="sxs-lookup"><span data-stu-id="7d299-135">[\<schemaImporterExtensions> Element](../../../docs/standard/serialization/schemaimporterextensions-element.md) </span></span>  
 <span data-ttu-id="7d299-136">[\<xmlSchemaImporterExtensions> 的 \<add> 元素](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md) </span><span class="sxs-lookup"><span data-stu-id="7d299-136">[\<add> Element for \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md) </span></span>  
 [<span data-ttu-id="7d299-137">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="7d299-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)

