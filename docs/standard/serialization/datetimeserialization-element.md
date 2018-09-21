---
title: '&lt;dateTimeSerialization&gt; 元素'
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: cd275cdbc51c86b1d774058db839c38349b319a6
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532394"
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="3bbb7-102">&lt;dateTimeSerialization&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="3bbb7-103">确定 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="3bbb7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3bbb7-104">\<configuration></span></span>  
<span data-ttu-id="3bbb7-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="3bbb7-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bbb7-106">语法</span><span class="sxs-lookup"><span data-stu-id="3bbb7-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bbb7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3bbb7-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bbb7-109">特性</span><span class="sxs-lookup"><span data-stu-id="3bbb7-109">Attributes</span></span>  
  
|<span data-ttu-id="3bbb7-110">特性</span><span class="sxs-lookup"><span data-stu-id="3bbb7-110">Attributes</span></span>|<span data-ttu-id="3bbb7-111">描述</span><span class="sxs-lookup"><span data-stu-id="3bbb7-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="3bbb7-112">可选。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-112">Optional.</span></span> <span data-ttu-id="3bbb7-113">指定序列化模式。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-113">Specifies the serialization mode.</span></span> <span data-ttu-id="3bbb7-114">设置为 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="3bbb7-115">默认值为 RoundTrip。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bbb7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-116">Child Elements</span></span>  
 <span data-ttu-id="3bbb7-117">无。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3bbb7-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3bbb7-119">元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-119">Element</span></span>|<span data-ttu-id="3bbb7-120">描述</span><span class="sxs-lookup"><span data-stu-id="3bbb7-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bbb7-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="3bbb7-121">system.xml.serialization</span></span>|<span data-ttu-id="3bbb7-122">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bbb7-123">备注</span><span class="sxs-lookup"><span data-stu-id="3bbb7-123">Remarks</span></span>  
 <span data-ttu-id="3bbb7-124">在 .NET Framework 1.0、1.1、2.0 以及更高版本中，将此属性设置为 Local 时，<xref:System.DateTime> 对象始终设置为本地时间格式。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="3bbb7-125">即，序列化的数据中总是包含本地时区信息。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="3bbb7-126">将此属性设置为 Local 可确保与较早版本的 .NET Framework 兼容。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3bbb7-127">在 .NET Framework 2.0 及更高版本中，将此属性设置为 Roundtrip 时，系统会检查 <xref:System.DateTime> 对象以确定这些对象位于本地时区、UTC 时区还是未指定的时区中。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="3bbb7-128">随后会序列化 <xref:System.DateTime> 对象并保留该信息。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="3bbb7-129">这是默认行为，建议为所有不与 Framework 的较早版本通信的新应用程序使用此行为。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbb7-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bbb7-130">See also</span></span>

- <xref:System.DateTime>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="3bbb7-131">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="3bbb7-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="3bbb7-132">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="3bbb7-133">\<添加 > 元素\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="3bbb7-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="3bbb7-134">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="3bbb7-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
