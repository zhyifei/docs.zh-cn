---
title: <dateTimeSerialization> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: af0d8eeb36e023b4d38f9ad5831de3d392a487fd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288257"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="dfa93-102">\<dateTimeSerialization > 元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="dfa93-103">确定 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="dfa93-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="dfa93-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dfa93-104">\<configuration></span></span>  
<span data-ttu-id="dfa93-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="dfa93-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfa93-106">语法</span><span class="sxs-lookup"><span data-stu-id="dfa93-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfa93-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dfa93-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dfa93-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfa93-109">特性</span><span class="sxs-lookup"><span data-stu-id="dfa93-109">Attributes</span></span>  
  
|<span data-ttu-id="dfa93-110">特性</span><span class="sxs-lookup"><span data-stu-id="dfa93-110">Attributes</span></span>|<span data-ttu-id="dfa93-111">描述</span><span class="sxs-lookup"><span data-stu-id="dfa93-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="dfa93-112">可选。</span><span class="sxs-lookup"><span data-stu-id="dfa93-112">Optional.</span></span> <span data-ttu-id="dfa93-113">指定序列化模式。</span><span class="sxs-lookup"><span data-stu-id="dfa93-113">Specifies the serialization mode.</span></span> <span data-ttu-id="dfa93-114">设置为 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="dfa93-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="dfa93-115">默认值为 RoundTrip。</span><span class="sxs-lookup"><span data-stu-id="dfa93-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfa93-116">子元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-116">Child Elements</span></span>  
 <span data-ttu-id="dfa93-117">无。</span><span class="sxs-lookup"><span data-stu-id="dfa93-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfa93-118">父元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dfa93-119">元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-119">Element</span></span>|<span data-ttu-id="dfa93-120">描述</span><span class="sxs-lookup"><span data-stu-id="dfa93-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dfa93-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="dfa93-121">system.xml.serialization</span></span>|<span data-ttu-id="dfa93-122">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="dfa93-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfa93-123">备注</span><span class="sxs-lookup"><span data-stu-id="dfa93-123">Remarks</span></span>  
 <span data-ttu-id="dfa93-124">在 .NET Framework 1.0、1.1、2.0 以及更高版本中，将此属性设置为 Local 时，<xref:System.DateTime> 对象始终设置为本地时间格式。</span><span class="sxs-lookup"><span data-stu-id="dfa93-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="dfa93-125">即，序列化的数据中总是包含本地时区信息。</span><span class="sxs-lookup"><span data-stu-id="dfa93-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="dfa93-126">将此属性设置为 Local 可确保与较早版本的 .NET Framework 兼容。</span><span class="sxs-lookup"><span data-stu-id="dfa93-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dfa93-127">在 .NET Framework 2.0 及更高版本中，将此属性设置为 Roundtrip 时，系统会检查 <xref:System.DateTime> 对象以确定这些对象位于本地时区、UTC 时区还是未指定的时区中。</span><span class="sxs-lookup"><span data-stu-id="dfa93-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="dfa93-128">随后会序列化 <xref:System.DateTime> 对象并保留该信息。</span><span class="sxs-lookup"><span data-stu-id="dfa93-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="dfa93-129">这是默认行为，建议为所有不与 Framework 的较早版本通信的新应用程序使用此行为。</span><span class="sxs-lookup"><span data-stu-id="dfa93-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa93-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa93-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="dfa93-131">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="dfa93-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="dfa93-132">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="dfa93-133">\<添加 > 元素\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="dfa93-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="dfa93-134">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="dfa93-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
