---
title: <xmlSerializer> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 2919e8d4c1af858973ff3d2b58b4d3bc4f925527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018051"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="e23fb-102">\<xmlSerializer > 元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-102">\<xmlSerializer> Element</span></span>
<span data-ttu-id="e23fb-103">指定是否完成 <xref:System.Xml.Serialization.XmlSerializer> 进度的额外检查。</span><span class="sxs-lookup"><span data-stu-id="e23fb-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="e23fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e23fb-104">\<configuration></span></span>  
<span data-ttu-id="e23fb-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e23fb-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e23fb-106">语法</span><span class="sxs-lookup"><span data-stu-id="e23fb-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e23fb-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e23fb-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e23fb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e23fb-109">特性</span><span class="sxs-lookup"><span data-stu-id="e23fb-109">Attributes</span></span>  
  
|<span data-ttu-id="e23fb-110">特性</span><span class="sxs-lookup"><span data-stu-id="e23fb-110">Attribute</span></span>|<span data-ttu-id="e23fb-111">描述</span><span class="sxs-lookup"><span data-stu-id="e23fb-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e23fb-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="e23fb-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="e23fb-113">指定是否已检查 <xref:System.Xml.Serialization.XmlSerializer> 的进度。</span><span class="sxs-lookup"><span data-stu-id="e23fb-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="e23fb-114">将特性设置为“true”或“false”。</span><span class="sxs-lookup"><span data-stu-id="e23fb-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="e23fb-115">默认值为“true”。</span><span class="sxs-lookup"><span data-stu-id="e23fb-115">The default is "true".</span></span>|  
|<span data-ttu-id="e23fb-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="e23fb-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="e23fb-117">指定 <xref:System.Xml.Serialization.XmlSerializer> 是否使用旧的序列化生成，该方法通过将 C# 代码写入到一个文件，然后将其编译为程序集来生成程序集。</span><span class="sxs-lookup"><span data-stu-id="e23fb-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="e23fb-118">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="e23fb-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e23fb-119">子元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-119">Child Elements</span></span>  
 <span data-ttu-id="e23fb-120">无。</span><span class="sxs-lookup"><span data-stu-id="e23fb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e23fb-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e23fb-122">元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-122">Element</span></span>|<span data-ttu-id="e23fb-123">描述</span><span class="sxs-lookup"><span data-stu-id="e23fb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e23fb-124">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="e23fb-125">包含 <xref:System.Xml.Serialization.XmlSerializer> 和 <xref:System.Xml.Serialization.XmlSchemaImporter> 类的配置设置。</span><span class="sxs-lookup"><span data-stu-id="e23fb-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e23fb-126">备注</span><span class="sxs-lookup"><span data-stu-id="e23fb-126">Remarks</span></span>  
 <span data-ttu-id="e23fb-127">默认情况下，当反序列化不受信任的数据时，<xref:System.Xml.Serialization.XmlSerializer> 会额外提供一层防范潜在拒绝服务攻击的安全保护。</span><span class="sxs-lookup"><span data-stu-id="e23fb-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="e23fb-128">它通过在反序列化期间尝试检测无限循环来实现以上保护。</span><span class="sxs-lookup"><span data-stu-id="e23fb-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="e23fb-129">如果检测到此类情况，则引发异常并显示以下消息："内部错误： 反序列化无法越过基础流。"</span><span class="sxs-lookup"><span data-stu-id="e23fb-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="e23fb-130">接收到此消息并不一定表示正在发生拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="e23fb-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="e23fb-131">在某些极少出现的情况下，无限循环检测机制会产生误报，并对合法的传入消息引发异常。</span><span class="sxs-lookup"><span data-stu-id="e23fb-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="e23fb-132">如果发现在你的特定应用程序中，合法消息被这一额外的保护层拒绝，请将 checkDeserializeAdvances 属性设置为“false”。</span><span class="sxs-lookup"><span data-stu-id="e23fb-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="e23fb-133">示例</span><span class="sxs-lookup"><span data-stu-id="e23fb-133">Example</span></span>  
 <span data-ttu-id="e23fb-134">下面的代码示例将 checkDeserializeAdvances 属性设置为“false”。</span><span class="sxs-lookup"><span data-stu-id="e23fb-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e23fb-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="e23fb-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="e23fb-136">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="e23fb-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="e23fb-137">XML 和 SOAP 序列化</span><span class="sxs-lookup"><span data-stu-id="e23fb-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
