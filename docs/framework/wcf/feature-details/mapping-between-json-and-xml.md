---
title: "JSON 和 XML 之间的映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8bcc8f178f76c536b189058210a586d0d37a1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-between-json-and-xml"></a><span data-ttu-id="32e69-102">JSON 和 XML 之间的映射</span><span class="sxs-lookup"><span data-stu-id="32e69-102">Mapping Between JSON and XML</span></span>
<span data-ttu-id="32e69-103"><xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> 生成的读取器和编写器通过 JavaScript 对象表示法 (JSON) 内容提供 XML API。</span><span class="sxs-lookup"><span data-stu-id="32e69-103">The readers and writers produced by the <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> provide an XML API over JavaScript Object Notation (JSON) content.</span></span> <span data-ttu-id="32e69-104">JSON 使用 JavaScript 的对象文字子集对数据进行编码。</span><span class="sxs-lookup"><span data-stu-id="32e69-104">JSON encodes data using a subset of the object literals of JavaScript.</span></span> <span data-ttu-id="32e69-105">在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序使用 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> 或 <xref:System.ServiceModel.WebHttpBinding> 发送或接收 JSON 内容时，也使用此工厂生成的读取器和编写器。</span><span class="sxs-lookup"><span data-stu-id="32e69-105">The readers and writers produced by this factory are also used when JSON content is being sent or received by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications using the <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> or the <xref:System.ServiceModel.WebHttpBinding>.</span></span>  
  
 <span data-ttu-id="32e69-106">使用 JSON 内容进行初始化时，JSON 读取器的行为方式与文本 XML 读取器通过 XML 实例执行的方式相同。</span><span class="sxs-lookup"><span data-stu-id="32e69-106">When initialized with JSON content, the JSON reader behaves in the same way that a textual XML reader does over an instance of XML.</span></span> <span data-ttu-id="32e69-107">对文本 XML 读取器的调用序列生成某个 XML 实例时，JSON 编写器写出 JSON 内容。</span><span class="sxs-lookup"><span data-stu-id="32e69-107">The JSON writer, when given a sequence of calls that on a textual XML reader produces a certain XML instance, writes out JSON content.</span></span> <span data-ttu-id="32e69-108">本主题中描述此 XML 实例和 JSON 内容之间的映射以供在高级方案中使用。</span><span class="sxs-lookup"><span data-stu-id="32e69-108">The mapping between this instance of XML and the JSON content is described in this topic for use in advanced scenarios.</span></span>  
  
 <span data-ttu-id="32e69-109">在内部，由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 处理时，JSON 表示为 XML infoset。</span><span class="sxs-lookup"><span data-stu-id="32e69-109">Internally, JSON is represented as an XML infoset when processed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="32e69-110">通常，无须关注此内部表示，因为该映射仅仅是逻辑映射：JSON 通常并不物理转换为内存中的 XML 或从 XML 转换为 JSON。</span><span class="sxs-lookup"><span data-stu-id="32e69-110">Normally you do not have to be concerned with this internal representation as the mapping is only a logical one: JSON is normally not physically converted to XML in memory or converted to JSON from XML.</span></span> <span data-ttu-id="32e69-111">该映射意味着 XML API 用于访问 JSON 内容。</span><span class="sxs-lookup"><span data-stu-id="32e69-111">The mapping means that XML APIs are used to access JSON content.</span></span>  
  
 <span data-ttu-id="32e69-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用 JSON 时，通常的方案是在适当时由 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 行为或 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> 行为自动插入 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="32e69-112">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses JSON, the usual scenario is that the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is automatically plugged in by the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior, or by the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior when appropriate.</span></span> <span data-ttu-id="32e69-113"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 了解 JSON 和 XML infoset 之间的映射，其行为就像它直接处理 JSON 那样。</span><span class="sxs-lookup"><span data-stu-id="32e69-113">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> understands the mapping between JSON and the XML infoset and acts as if it is dealing with JSON directly.</span></span> <span data-ttu-id="32e69-114">（通过了解 XML 符合下面的映射，可以将 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 与任何 XML 读取器或编写器一起使用。）</span><span class="sxs-lookup"><span data-stu-id="32e69-114">(It is possible to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> with any XML reader or writer, with the understanding that the XML conforms to the following mapping.)</span></span>  
  
 <span data-ttu-id="32e69-115">在高级方案中，可能需要直接访问下面的映射。</span><span class="sxs-lookup"><span data-stu-id="32e69-115">In advanced scenarios, it may become necessary to directly access the following mapping.</span></span> <span data-ttu-id="32e69-116">希望以自定义方式序列化和反序列化 JSON 而不依赖于 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 时，或者直接为包含 JSON 的消息处理 <xref:System.ServiceModel.Channels.Message> 类型时，会出现这些方案。</span><span class="sxs-lookup"><span data-stu-id="32e69-116">These scenarios occur when you want to serialize and deserialize JSON in custom ways, without relying on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, or when dealing with the <xref:System.ServiceModel.Channels.Message> type directly for messages containing JSON.</span></span> <span data-ttu-id="32e69-117">JSON-XML 映射也用于消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="32e69-117">The JSON-XML mapping is also used for message logging.</span></span> <span data-ttu-id="32e69-118">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中使用消息日志记录功能时，按照下一节中描述的映射，将 JSON 消息记录为 XML。</span><span class="sxs-lookup"><span data-stu-id="32e69-118">When using the message logging feature in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], JSON messages is logged as XML according to the mapping described in the next section.</span></span>  
  
 <span data-ttu-id="32e69-119">为阐明映射的概念，下面的示例采用一个 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="32e69-119">To clarify the concept of a mapping, the following example is of a JSON document.</span></span>  
  
```json  
{"product":"pencil","price":12}  
```  
  
 <span data-ttu-id="32e69-120">若要使用前面提到的读取器之一读取此 JSON 文档，请使用与读取以下 XML 文档所用相同的 <xref:System.Xml.XmlDictionaryReader> 调用序列。</span><span class="sxs-lookup"><span data-stu-id="32e69-120">To read this JSON document using one of the readers previously mentioned, use the same sequence of <xref:System.Xml.XmlDictionaryReader> calls as you would to read the following XML document.</span></span>  
  
```xml  
<root type="object">  
    <product type="string">pencil</product>  
    <price type="number">12</price>  
</root>  
```  
  
 <span data-ttu-id="32e69-121">此外，如果示例中的 JSON 消息由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 接收并记录，则在前面的日志中会看到 XML 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-121">Furthermore, if the JSON message in the example is received by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and logged, you would see the XML fragment in the preceding log.</span></span>  
  
## <a name="mapping-between-json-and-the-xml-infoset"></a><span data-ttu-id="32e69-122">JSON 和 XML Infoset 之间的映射</span><span class="sxs-lookup"><span data-stu-id="32e69-122">Mapping Between JSON and the XML Infoset</span></span>  
 <span data-ttu-id="32e69-123">准确地讲，映射是之间 JSON 中所述[RFC 4627](http://go.microsoft.com/fwlink/?LinkId=98808) （除非包含某些限制宽松和某些添加其他限制） 和 XML 信息集 （以及不文本 XML） 中所述[XML 信息设置](http://go.microsoft.com/fwlink/?LinkId=98809)。</span><span class="sxs-lookup"><span data-stu-id="32e69-123">Formally, the mapping is between JSON as described in [RFC 4627](http://go.microsoft.com/fwlink/?LinkId=98808) (except with certain restrictions relaxed and certain other restrictions added) and the XML infoset (and not textual XML) as described in [XML Information Set](http://go.microsoft.com/fwlink/?LinkId=98809) .</span></span> <span data-ttu-id="32e69-124">请参阅本主题的定义*信息项*和 [方括号] 中的字段。</span><span class="sxs-lookup"><span data-stu-id="32e69-124">See this topic for the definitions of *information items* and fields in [square brackets].</span></span>  
  
 <span data-ttu-id="32e69-125">空 JSON 文档映射到空 XML 文档，而空 XML 文档映射到空 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="32e69-125">A blank JSON document maps to blank XML document, and a blank XML document maps to a blank JSON document.</span></span> <span data-ttu-id="32e69-126">在 XML 到 JSON 的映射上，文档之后不允许有前导空白和尾随空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-126">On the XML to JSON mapping, preceding whitespace and trailing whitespace after the document are not allowed.</span></span>  
  
 <span data-ttu-id="32e69-127">映射是在文档信息项 (DII) 或元素信息项 (EII) 和 JSON 之间定义的。</span><span class="sxs-lookup"><span data-stu-id="32e69-127">The mapping is defined between either a Document Information Item (DII) or an Element Information Item (EII) and JSON.</span></span> <span data-ttu-id="32e69-128">EII 或 DII 的 [文档元素] 属性称为根 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-128">The EII, or the DII’s [document element] property, is referred to as the Root JSON Element.</span></span> <span data-ttu-id="32e69-129">请注意此映射不支持文档片段（具有多个根元素的 XML）。</span><span class="sxs-lookup"><span data-stu-id="32e69-129">Note that document fragments (XML with multiple root elements) are not supported in this mapping.</span></span>  
  
 <span data-ttu-id="32e69-130">示例：下面的文档：</span><span class="sxs-lookup"><span data-stu-id="32e69-130">Example: The following document:</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="32e69-131">和下面的元素：</span><span class="sxs-lookup"><span data-stu-id="32e69-131">And the following element:</span></span>  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="32e69-132">都具有到 JSON 的映射。</span><span class="sxs-lookup"><span data-stu-id="32e69-132">Both have a mapping to JSON.</span></span> <span data-ttu-id="32e69-133"><`root`> 元素是两种情况下的根 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-133">The <`root`> element is the Root JSON Element in both cases.</span></span>  
  
 <span data-ttu-id="32e69-134">此外，在使用 DII 的情况下，应该考虑以下内容：</span><span class="sxs-lookup"><span data-stu-id="32e69-134">Furthermore, in the case of a DII, the following should be considered:</span></span>  
  
-   <span data-ttu-id="32e69-135">[子级] 列表中的某些项不得存在。</span><span class="sxs-lookup"><span data-stu-id="32e69-135">Some items in the [children] list must not be present.</span></span> <span data-ttu-id="32e69-136">读取从 JSON 映射的 XML 时，不要依赖于此事实。</span><span class="sxs-lookup"><span data-stu-id="32e69-136">Do not rely on this fact when reading XML mapped from JSON.</span></span>  
  
-   <span data-ttu-id="32e69-137">[子级] 列表不包含注释信息项。</span><span class="sxs-lookup"><span data-stu-id="32e69-137">The [children] list holds no comment information items.</span></span>  
  
-   <span data-ttu-id="32e69-138">[子级] 列表不包含 DTD 信息项。</span><span class="sxs-lookup"><span data-stu-id="32e69-138">The [children] list holds no DTD information items.</span></span>  
  
-   <span data-ttu-id="32e69-139">[子级] 列表不包含个人信息 (PI) 信息项 ( \<？ xml … > 声明不被视为 PI 信息项)</span><span class="sxs-lookup"><span data-stu-id="32e69-139">The [children] list holds no personal Information (PI) information items (the \<?xml…> declaration is not considered a PI information item)</span></span>  
  
-   <span data-ttu-id="32e69-140">[符号] 集为空。</span><span class="sxs-lookup"><span data-stu-id="32e69-140">The [notations] set is empty.</span></span>  
  
-   <span data-ttu-id="32e69-141">[未分析的实体] 集为空。</span><span class="sxs-lookup"><span data-stu-id="32e69-141">The [unparsed entities] set is empty.</span></span>  
  
 <span data-ttu-id="32e69-142">示例：下面的文档没有到 JSON 的映射，因为 [子级] 包含 PI 和注释。</span><span class="sxs-lookup"><span data-stu-id="32e69-142">Example: The following document has no mapping to JSON because [children] holds a PI and a comment.</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<!--comment--><?pi?>`  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="32e69-143">根 JSON 元素的 EII 具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="32e69-143">The EII for the Root JSON Element has the following characteristics:</span></span>  
  
-   <span data-ttu-id="32e69-144">[本地名称] 具有值“root”。</span><span class="sxs-lookup"><span data-stu-id="32e69-144">[local name] has the value "root".</span></span>  
  
-   <span data-ttu-id="32e69-145">[命名空间名称] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-145">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-146">[前缀] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-146">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-147">[子级] 可能包含 EII（表示内部元素，将进一步描述）或 CII（字符信息项，将进一步描述）或这两者都不包含，但不能同时包含这两者。</span><span class="sxs-lookup"><span data-stu-id="32e69-147">[children] may either contain EIIs (which represent Inner Elements as described further) or CIIs (Character Information Items as described further) or none of these, but not both.</span></span>  
  
-   <span data-ttu-id="32e69-148">[属性] 可能包含以下可选的属性信息项 (AII)</span><span class="sxs-lookup"><span data-stu-id="32e69-148">[attributes] may contain the following optional attribute information items (AIIs)</span></span>  
  
-   <span data-ttu-id="32e69-149">JSON 类型属性（“type”），将进一步描述。</span><span class="sxs-lookup"><span data-stu-id="32e69-149">The JSON Type Attribute ("type") as described further.</span></span> <span data-ttu-id="32e69-150">此属性用于保留已映射 XML 中的 JSON 类型（字符串、数字、boolean、对象、数组或 null）。</span><span class="sxs-lookup"><span data-stu-id="32e69-150">This attribute is used to preserve the JSON type (string, number, boolean, object, array or null) in the mapped XML.</span></span>  
  
-   <span data-ttu-id="32e69-151">数据协定名称属性（“__type”），将进一步描述。</span><span class="sxs-lookup"><span data-stu-id="32e69-151">The Data Contract Name Attribute ("__type") as described further.</span></span> <span data-ttu-id="32e69-152">仅当 JSON 类型属性也存在且其 [正常化值] 为“object”时，此属性才能存在。</span><span class="sxs-lookup"><span data-stu-id="32e69-152">This attribute is can only be present if the JSON type attribute is also present and its [normalized value] is "object".</span></span> <span data-ttu-id="32e69-153">此属性由 `DataContractJsonSerializer` 用来保留数据协定类型信息 - 例如，在序列化派生类型和期望基类型的多态情况下。</span><span class="sxs-lookup"><span data-stu-id="32e69-153">This attribute is used by the `DataContractJsonSerializer` to preserve data contract type information - for example, in polymorphic cases where a derived type is serialized and where a base type is expected.</span></span> <span data-ttu-id="32e69-154">如果未使用 `DataContractJsonSerializer`，则大多数情况下忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="32e69-154">If you are not working with the `DataContractJsonSerializer`, in most cases, this attribute is ignored.</span></span>  
  
-   <span data-ttu-id="32e69-155">[范围内命名空间] 包含“xml”到“http://www.w3.org/XML/1998/namespace”的绑定，如 infoset 规范要求的那样。</span><span class="sxs-lookup"><span data-stu-id="32e69-155">[in-scope namespaces] contains the binding of "xml" to "http://www.w3.org/XML/1998/namespace" as mandated by the infoset specification.</span></span>  
  
-   <span data-ttu-id="32e69-156">[子级]、[属性] 和 [范围内命名空间] 不得具有除前面指定的之外的任何项，[命名空间属性] 不得具有成员，但是在读取从 JSON 映射的 XML 时不依赖于这些事实。</span><span class="sxs-lookup"><span data-stu-id="32e69-156">[children], [attributes] and [in-scope namespaces] must not have any items other than as specified previously and [namespace attributes] must have no members, but do not rely on these facts when reading XML mapped from JSON.</span></span>  
  
 <span data-ttu-id="32e69-157">示例：下面的文档没有到 JSON 的映射，因为 [命名空间属性] 不为空。</span><span class="sxs-lookup"><span data-stu-id="32e69-157">Example: The following document has no mapping to JSON because [namespace attributes] is not empty.</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<root  xmlns:a="myattributevalue">42</root>`  
  
 <span data-ttu-id="32e69-158">JSON 类型属性的 AII 具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="32e69-158">The AII for the JSON Type Attribute has the following characteristics:</span></span>  
  
-   <span data-ttu-id="32e69-159">[命名空间名称] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-159">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-160">[前缀] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-160">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-161">[本地名称] 为“type”。</span><span class="sxs-lookup"><span data-stu-id="32e69-161">[local name] is "type".</span></span>  
  
-   <span data-ttu-id="32e69-162">[正常化值] 是下面部分中描述的可能类型值之一。</span><span class="sxs-lookup"><span data-stu-id="32e69-162">[normalized value] is one of the possible type values described in the following section.</span></span>  
  
-   <span data-ttu-id="32e69-163">[已指定] 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="32e69-163">[specified] is `true`.</span></span>  
  
-   <span data-ttu-id="32e69-164">[属性类型] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-164">[attribute type] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-165">[引用] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-165">[references] has no value.</span></span>  
  
 <span data-ttu-id="32e69-166">数据协定名称属性的 AII 具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="32e69-166">The AII for the Data Contract Name Attribute has the following characteristics:</span></span>  
  
-   <span data-ttu-id="32e69-167">[命名空间名称] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-167">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-168">[前缀] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-168">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-169">[本地名称] 为“__type”（双下划线后跟“type”）。</span><span class="sxs-lookup"><span data-stu-id="32e69-169">[local name] is "__type" (two underscores and then "type").</span></span>  
  
-   <span data-ttu-id="32e69-170">[正常化值] 是任何有效的 Unicode 字符串 – 此字符串到 JSON 的映射将在下面的部分中进行描述。</span><span class="sxs-lookup"><span data-stu-id="32e69-170">[normalized value] is any valid Unicode string – the mapping of this string to JSON is described in the following section.</span></span>  
  
-   <span data-ttu-id="32e69-171">[已指定] 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="32e69-171">[specified] is `true`.</span></span>  
  
-   <span data-ttu-id="32e69-172">[属性类型] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-172">[attribute type] has no value.</span></span>  
  
-   <span data-ttu-id="32e69-173">[引用] 没有值。</span><span class="sxs-lookup"><span data-stu-id="32e69-173">[references] has no value.</span></span>  
  
 <span data-ttu-id="32e69-174">根 JSON 元素中包含的内部元素或其他内部元素具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="32e69-174">Inner elements contained within the Root JSON Element or other inner elements have the following characteristics:</span></span>  
  
-   <span data-ttu-id="32e69-175">[本地名称] 可能具有任何值，将进一步描述</span><span class="sxs-lookup"><span data-stu-id="32e69-175">[local name] may have any value as described further</span></span>  
  
-   <span data-ttu-id="32e69-176">[命名空间名称]、[前缀]、[子级]、[属性]、[命名空间属性] 和 [范围内命名空间] 遵循与根 JSON 元素相同的规则。</span><span class="sxs-lookup"><span data-stu-id="32e69-176">[namespace name], [prefix], [children], [attributes], [namespace attributes], and [in-scope namespaces] are subject to the same rules as the Root JSON Element.</span></span>  
  
 <span data-ttu-id="32e69-177">在根 JSON 元素和内部元素中，JSON 类型属性定义到 JSON 的映射和可能的 [子级] 及其解释。</span><span class="sxs-lookup"><span data-stu-id="32e69-177">In both the Root JSON Element and the inner elements, the JSON Type Attribute defines the mapping to JSON and the possible [children] and their interpretation.</span></span> <span data-ttu-id="32e69-178">属性的 [正常化值] 区分大小写，必须为小写，且不能包含空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-178">The attribute’s [normalized value] is case-sensitive and must be lowercase, and cannot contain whitespace.</span></span>  
  
|<span data-ttu-id="32e69-179">`JSON Type Attribute` 的 AII 的 [正常化值]</span><span class="sxs-lookup"><span data-stu-id="32e69-179">[normalized value] of `JSON Type Attribute`’s AII</span></span>|<span data-ttu-id="32e69-180">对应 EII 的已允许 [子级]</span><span class="sxs-lookup"><span data-stu-id="32e69-180">Allowed [children] of the corresponding EII</span></span>|<span data-ttu-id="32e69-181">映射到 JSON</span><span class="sxs-lookup"><span data-stu-id="32e69-181">Mapping to JSON</span></span>|  
|---------------------------------------------------------|---------------------------------------------------|---------------------|  
|<span data-ttu-id="32e69-182">`string`（或缺少 JSON 类型 AII）</span><span class="sxs-lookup"><span data-stu-id="32e69-182">`string` (or absence of the JSON type AII)</span></span><br /><br /> <span data-ttu-id="32e69-183">`string` 与缺少 JSON 类型 AII 相同，使 `string` 成为默认值。</span><span class="sxs-lookup"><span data-stu-id="32e69-183">A `string` and the absence of the JSON type AII are the same makes `string` the default.</span></span><br /><br /> <span data-ttu-id="32e69-184">因此，`<root> string1</root>` 映射到 JSON `string`“string1”。</span><span class="sxs-lookup"><span data-stu-id="32e69-184">So, `<root> string1</root>` maps to the JSON `string` "string1".</span></span>|<span data-ttu-id="32e69-185">0 个或多个 Cii</span><span class="sxs-lookup"><span data-stu-id="32e69-185">0 or more CIIs</span></span>|<span data-ttu-id="32e69-186">JSON `string`（JSON RFC，第 2.5 节）。</span><span class="sxs-lookup"><span data-stu-id="32e69-186">A JSON `string` (JSON RFC, section 2.5).</span></span> <span data-ttu-id="32e69-187">每个 `char` 是对应于来自 CII 的 [字符代码] 的字符。</span><span class="sxs-lookup"><span data-stu-id="32e69-187">Each `char` is a character that corresponds to the [character code] from the CII.</span></span> <span data-ttu-id="32e69-188">如果没有 CII，则它映射到空 JSON `string`。</span><span class="sxs-lookup"><span data-stu-id="32e69-188">If there are no CIIs, it maps to an empty JSON `string`.</span></span><br /><br /> <span data-ttu-id="32e69-189">示例：下面的元素映射到 JSON 片段：</span><span class="sxs-lookup"><span data-stu-id="32e69-189">Example: The following element maps to a JSON fragment:</span></span><br /><br /> `<root type="string">42</root>`<br /><br /> <span data-ttu-id="32e69-190">JSON 片段是“42”。</span><span class="sxs-lookup"><span data-stu-id="32e69-190">The JSON fragment is "42".</span></span><br /><br /> <span data-ttu-id="32e69-191">在 XML 到 JSON 的映射上，必须转义的字符映射到转义符，所有其他字符都映射到未转义的字符。</span><span class="sxs-lookup"><span data-stu-id="32e69-191">On XML to JSON mapping, characters that must be escaped map to escaped characters, all others map to characters that are not escaped.</span></span> <span data-ttu-id="32e69-192">"/"字符是特殊字符 – 即使它不一定要转义 (写出为"\\/")。</span><span class="sxs-lookup"><span data-stu-id="32e69-192">The "/" character is special – it is escaped even though it does not have to be (written out as "\\/").</span></span><br /><br /> <span data-ttu-id="32e69-193">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-193">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> <span data-ttu-id="32e69-194">JSON 片段是" \\"da\\/ta\\""。</span><span class="sxs-lookup"><span data-stu-id="32e69-194">The JSON fragment is "the \\"da\\/ta\\"".</span></span><br /><br /> <span data-ttu-id="32e69-195">在 JSON 到 XML 的映射上，任何转义符和未转义的字符都正确映射到对应的 [字符代码]。</span><span class="sxs-lookup"><span data-stu-id="32e69-195">On JSON to XML mapping, any escaped characters and characters that are not escaped map correctly to the corresponding [character code].</span></span><br /><br /> <span data-ttu-id="32e69-196">示例：JSON 片段“\u0041BC”映射到下面的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-196">Example: The JSON fragment "\u0041BC", maps to the following XML element.</span></span><br /><br /> `<root type="string">ABC</root>`<br /><br /> <span data-ttu-id="32e69-197">字符串可以由未映射到 XML 的空白（JSON RFC 第 2 节中的“ws”）围绕。</span><span class="sxs-lookup"><span data-stu-id="32e69-197">The string can be surrounded by whitespace ('ws' in section 2 of the JSON RFC) that does not get mapped to XML.</span></span><br /><br /> <span data-ttu-id="32e69-198">示例：JSON 片段           "ABC"（在第一个双引号之前存在空格）映射到下面的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-198">Example: The JSON fragment           "ABC", (there are spaces before the first double quote), maps to the following XML element.</span></span><br /><br /> `<root type="string">ABC</root>`<br /><br /> <span data-ttu-id="32e69-199">XML 中的任何空白都映射到 JSON 中的空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-199">Any whitespace in XML maps to whitespace in JSON.</span></span><br /><br /> <span data-ttu-id="32e69-200">示例：下面的 XML 元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-200">Example: The following XML element maps to a JSON fragment.</span></span><br /><br /> `<root type="string">  A BC      </root>`<br /><br /> <span data-ttu-id="32e69-201">JSON 片段是“ A BC ”。</span><span class="sxs-lookup"><span data-stu-id="32e69-201">The JSON fragment is " A BC ".</span></span>|  
|`number`|<span data-ttu-id="32e69-202">1 个或多个 CII</span><span class="sxs-lookup"><span data-stu-id="32e69-202">1 or more CIIs</span></span>|<span data-ttu-id="32e69-203">可能由空白围绕的 JSON `number`（JSON RFC，第 2.4 节）。</span><span class="sxs-lookup"><span data-stu-id="32e69-203">A JSON `number` (JSON RFC, section 2.4), possibly surrounded by whitespace.</span></span> <span data-ttu-id="32e69-204">数字/空白组合中的每个字符都是对应于 CII 中 [字符代码] 的字符。</span><span class="sxs-lookup"><span data-stu-id="32e69-204">Each character in the number/whitespace combination is a character that corresponds to the [character code] from the CII.</span></span><br /><br /> <span data-ttu-id="32e69-205">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-205">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="number">    42</root>`<br /><br /> <span data-ttu-id="32e69-206">JSON 片段是    42</span><span class="sxs-lookup"><span data-stu-id="32e69-206">The JSON fragment is    42</span></span><br /><br /> <span data-ttu-id="32e69-207">（保留空白）。</span><span class="sxs-lookup"><span data-stu-id="32e69-207">(Whitespace is preserved).</span></span>|  
|`boolean`|<span data-ttu-id="32e69-208">4 个或 5 个 CII（对应于 `true` 或 `false`），可能由其他空白 CII 围绕。</span><span class="sxs-lookup"><span data-stu-id="32e69-208">4 or 5 CIIs (which corresponds to `true` or `false`), possibly surrounded by additional whitespace CIIs.</span></span>|<span data-ttu-id="32e69-209">对应于字符串“true”的 CII 序列被映射到文字 `true`，而对应于字符串“false”的 CII 序列被映射到文字 `false`。</span><span class="sxs-lookup"><span data-stu-id="32e69-209">A CII sequence that corresponds to the string "true" is mapped to the literal `true`, and a CII sequence that corresponds to the string "false" is mapped to the literal `false`.</span></span> <span data-ttu-id="32e69-210">保留了围绕的空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-210">Surrounding whitespace is preserved.</span></span><br /><br /> <span data-ttu-id="32e69-211">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-211">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="boolean"> false</root>`<br /><br /> <span data-ttu-id="32e69-212">JSON 片段是 `false`。</span><span class="sxs-lookup"><span data-stu-id="32e69-212">The JSON fragment is `false`.</span></span>|  
|`null`|<span data-ttu-id="32e69-213">都不允许。</span><span class="sxs-lookup"><span data-stu-id="32e69-213">None allowed.</span></span>|<span data-ttu-id="32e69-214">文字 `null`。</span><span class="sxs-lookup"><span data-stu-id="32e69-214">The literal `null`.</span></span> <span data-ttu-id="32e69-215">在 JSON 到 XML 的映射上，`null` 可能由未映射到 XML 的空白（第 2 节中的“ws”）围绕。</span><span class="sxs-lookup"><span data-stu-id="32e69-215">On JSON to XML mapping, the `null` may be surrounded by whitespace (‘ws’ in section 2) that does not get mapped to XML.</span></span><br /><br /> <span data-ttu-id="32e69-216">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-216">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="null"/>`<br /><br /> <span data-ttu-id="32e69-217">或</span><span class="sxs-lookup"><span data-stu-id="32e69-217">or</span></span><br /><br /> `<root type="null"></root>`<br /><br /> <span data-ttu-id="32e69-218">:</span><span class="sxs-lookup"><span data-stu-id="32e69-218">:</span></span><br /><br /> <span data-ttu-id="32e69-219">在这两种情况下 JSON 片段都是 `Null`。</span><span class="sxs-lookup"><span data-stu-id="32e69-219">The JSON fragment in both cases is `Null`.</span></span>|  
|`object`|<span data-ttu-id="32e69-220">0 个或多个 EII。</span><span class="sxs-lookup"><span data-stu-id="32e69-220">0 or more EIIs.</span></span>|<span data-ttu-id="32e69-221">如 JSON RFC 第 2.2 节中的 `begin-object`（左花括号），后跟每个 EII 的成员记录，将进一步说明。</span><span class="sxs-lookup"><span data-stu-id="32e69-221">A `begin-object` (left curly brace) as in section 2.2 of the JSON RFC, followed by a member record for each EII as described further.</span></span> <span data-ttu-id="32e69-222">如果存在多个 EII，则在成员记录之间存在值分隔符（逗号）。</span><span class="sxs-lookup"><span data-stu-id="32e69-222">If there is more than one EII, there are value-separators (commas) between the member records.</span></span> <span data-ttu-id="32e69-223">所有这一切后跟 end-object（右花括号）。</span><span class="sxs-lookup"><span data-stu-id="32e69-223">All this is followed by an end-object (right curly brace).</span></span><br /><br /> <span data-ttu-id="32e69-224">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-224">Example: The following element maps to the JSON fragment.</span></span><br /><br /> <span data-ttu-id="32e69-225">\<根类型 ="对象"></span><span class="sxs-lookup"><span data-stu-id="32e69-225">\<root type="object"></span></span><br /><br /> <span data-ttu-id="32e69-226">\<type1 类型 ="string"> aaa\</type1 ></span><span class="sxs-lookup"><span data-stu-id="32e69-226">\<type1 type="string">aaa\</type1></span></span><br /><br /> <span data-ttu-id="32e69-227">\<type2 类型 ="string"> bbb\</type2 ></span><span class="sxs-lookup"><span data-stu-id="32e69-227">\<type2 type="string">bbb\</type2></span></span><br /><br /> <span data-ttu-id="32e69-228">\<根/></span><span class="sxs-lookup"><span data-stu-id="32e69-228">\</root ></span></span><br /><br /> <span data-ttu-id="32e69-229">JSON 片段是 {"type1":"aaa","type2":"bbb"}。</span><span class="sxs-lookup"><span data-stu-id="32e69-229">The JSON fragment is {"type1":"aaa","type2":"bbb"}.</span></span><br /><br /> <span data-ttu-id="32e69-230">如果在 XML 到 JSON 的映射上存在数据协定类型属性，则在开头插入其他成员记录。</span><span class="sxs-lookup"><span data-stu-id="32e69-230">If the Data Contract Type Attribute is present on XML to JSON mapping, then an additional Member Record is inserted at the beginning.</span></span> <span data-ttu-id="32e69-231">其名称是数据协定类型属性（“__type”）的 [本地名称]，其值是该属性的 [正常化值]。</span><span class="sxs-lookup"><span data-stu-id="32e69-231">Its name is the [local name] of the Data Contract Type Attribute ("__type"), and its value is the attribute's [normalized value].</span></span> <span data-ttu-id="32e69-232">相反，在 JSON 到 XML 的映射，如果第一个成员记录的名称是数据协定类型属性的 [本地名称] (即"\_（_t)")，相应的数据协定类型属性位于在映射的 XML 中，但不是对应的 EII存在。</span><span class="sxs-lookup"><span data-stu-id="32e69-232">Conversely, on JSON to XML mapping, if the first member-record’s name is the [local name] of the Data Contract Type Attribute (that is, "\__type"), a corresponding Data Contract Type Attribute is present in the mapped XML, but a corresponding EII is not present.</span></span> <span data-ttu-id="32e69-233">请注意，此成员记录必须首先出现在 JSON 对象中才能应用此特殊映射。</span><span class="sxs-lookup"><span data-stu-id="32e69-233">Note that this member record must occur first in the JSON object for this special mapping to apply.</span></span> <span data-ttu-id="32e69-234">这与通常的 JSON 处理（成员记录的顺序是不重要的）相背离。</span><span class="sxs-lookup"><span data-stu-id="32e69-234">This represents a departure from usual JSON processing, where the order of member records is not significant.</span></span><br /><br /> <span data-ttu-id="32e69-235">示例:</span><span class="sxs-lookup"><span data-stu-id="32e69-235">Example:</span></span><br /><br /> <span data-ttu-id="32e69-236">下面的 JSON 片段映射到 XML。</span><span class="sxs-lookup"><span data-stu-id="32e69-236">The following JSON fragment maps to XML.</span></span><br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> <span data-ttu-id="32e69-237">XML 是下面的代码。</span><span class="sxs-lookup"><span data-stu-id="32e69-237">The XML is the following code.</span></span><br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> <span data-ttu-id="32e69-238">请注意， \_（_t） AII 是存在，但没有任何\_（_t) EII。</span><span class="sxs-lookup"><span data-stu-id="32e69-238">Notice that the \__type AII is present, but there is no \__type EII.</span></span><br /><br /> <span data-ttu-id="32e69-239">但是，如果保留 JSON 中的顺序，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="32e69-239">However, if the order in the JSON is reversed as shown in the following example.</span></span><br /><br /> <span data-ttu-id="32e69-240">{"name":"John"，"\_（_t)":"Person"}</span><span class="sxs-lookup"><span data-stu-id="32e69-240">{"name":"John","\__type":"Person"}</span></span><br /><br /> <span data-ttu-id="32e69-241">则显示对应的 XML。</span><span class="sxs-lookup"><span data-stu-id="32e69-241">The corresponding XML is shown.</span></span><br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> <span data-ttu-id="32e69-242">也就是说， \_（_t） 不再具有特殊含义，映射到 EII 像往常一样，不是 AII。</span><span class="sxs-lookup"><span data-stu-id="32e69-242">That is, \__type ceases to have special meaning and maps to an EII as usual, not AII.</span></span><br /><br /> <span data-ttu-id="32e69-243">映射到 JSON 值时，AII 的 [正常化值] 的转义/未转义规则与在此表的“string”行中指定的 JSON 字符串的相同。</span><span class="sxs-lookup"><span data-stu-id="32e69-243">Escaping/unescaping rules for the AII’s [normalized value] when mapped to a JSON value are the same as for JSON strings, specified in the "string" row of this table.</span></span><br /><br /> <span data-ttu-id="32e69-244">示例:</span><span class="sxs-lookup"><span data-stu-id="32e69-244">Example:</span></span><br /><br /> `<root type="object" __type="\abc" />`<br /><br /> <span data-ttu-id="32e69-245">前面的示例可以映射到下面的 JSON。</span><span class="sxs-lookup"><span data-stu-id="32e69-245">to the previous example can be mapped to the following JSON.</span></span><br /><br /> `{"__type":"\\abc"}`<br /><br /> <span data-ttu-id="32e69-246">不能在 XML 到 JSON 的映射，第一个 EII 的 [本地名称]"\_（_t)"。</span><span class="sxs-lookup"><span data-stu-id="32e69-246">On an XML to JSON mapping, the first EII’s [local name] must not be "\__type".</span></span><br /><br /> <span data-ttu-id="32e69-247">在对象的 XML 到 JSON 的映射上从不生成空白 (`ws`)，且在 JSON 到 XML 的映射上忽略空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-247">Whitespace (`ws`) is never generated on XML to JSON mapping for objects and is ignored on JSON to XML mapping.</span></span><br /><br /> <span data-ttu-id="32e69-248">示例：下面的 JSON 片段映射到 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-248">Example: The following JSON fragment maps to an XML element.</span></span><br /><br /> <span data-ttu-id="32e69-249">{   "ccc"   :  "aaa",   "ddd"    :"bbb"}</span><span class="sxs-lookup"><span data-stu-id="32e69-249">{   "ccc"   :  "aaa",   "ddd"    :"bbb"}</span></span><br /><br /> <span data-ttu-id="32e69-250">在下面的代码中显示了 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-250">The XML element is shown in the following code.</span></span><br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|  
<span data-ttu-id="32e69-251">射线</span><span class="sxs-lookup"><span data-stu-id="32e69-251">ray\`</span></span>|<span data-ttu-id="32e69-252">0 个或多个 EII</span><span class="sxs-lookup"><span data-stu-id="32e69-252">0 or more EIIs</span></span>|<span data-ttu-id="32e69-253">如 JSON RFC 第 2.3 节中的 begin-array（左花括号），后跟每个 EII 的数组记录，将进一步描述。</span><span class="sxs-lookup"><span data-stu-id="32e69-253">A begin-array (left square bracket) as in section 2.3 of the JSON RFC, followed by an array record for each EII as described further.</span></span> <span data-ttu-id="32e69-254">如果存在多个 EII，则在数组记录之间存在值分隔符（逗号）。</span><span class="sxs-lookup"><span data-stu-id="32e69-254">If there is more than one EII, there are value-separators (commas) between the array records.</span></span> <span data-ttu-id="32e69-255">所有这一切后跟 end-array。</span><span class="sxs-lookup"><span data-stu-id="32e69-255">All this is followed by an end-array.</span></span><br /><br /> <span data-ttu-id="32e69-256">示例：下面的 XML 元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-256">Example: The following XML element maps to a JSON fragment.</span></span><br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> <span data-ttu-id="32e69-257">JSON 片段是 ["aaa","bbb"]</span><span class="sxs-lookup"><span data-stu-id="32e69-257">The JSON fragment is ["aaa","bbb"]</span></span><br /><br /> <span data-ttu-id="32e69-258">在数组的 XML 到 JSON 的映射上从不生成空白 (`ws`)，且在 JSON 到 XML 的映射上忽略空白。</span><span class="sxs-lookup"><span data-stu-id="32e69-258">Whitespace (`ws`) is never generated on XML to JSON mapping for arrays and is ignored on JSON to XML mapping.</span></span><br /><br /> <span data-ttu-id="32e69-259">示例：AJSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-259">Example: AJSON fragment.</span></span><br /><br /> <span data-ttu-id="32e69-260">[     "aaa",     "bbb"]</span><span class="sxs-lookup"><span data-stu-id="32e69-260">[     "aaa",     "bbb"]</span></span><br /><br /> <span data-ttu-id="32e69-261">它映射到的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="32e69-261">The XML element that it maps to.</span></span><br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|  
  
 <span data-ttu-id="32e69-262">成员记录的工作原理如下：</span><span class="sxs-lookup"><span data-stu-id="32e69-262">Member Records work as follows:</span></span>  
  
-   <span data-ttu-id="32e69-263">内部元素的 [本地名称] 映射到 `string` 的 `member` 部分，如 JSON RFC 第 2.2 节所定义。</span><span class="sxs-lookup"><span data-stu-id="32e69-263">Inner element’s [local name] maps to the `string` part of the `member` as defined in section 2.2 of the JSON RFC.</span></span>  
  
 <span data-ttu-id="32e69-264">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-264">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="object"/>`  
  
 `<myLocalName type="string">aaa</myLocalName>`  
  
 `</root >`  
  
 <span data-ttu-id="32e69-265">将显示下面的 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-265">The following JSON fragment is displayed.</span></span>  
  
 `{"myLocalName":"aaa"}`  
  
-   <span data-ttu-id="32e69-266">在 XML 到 JSON 的映射上，对必须在 JSON 中转义的字符进行转义，而不对其他字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="32e69-266">On the XML to JSON mapping, the characters that must be escaped in JSON are escaped, and the others are not escaped.</span></span> <span data-ttu-id="32e69-267">但是，对“/”字符进行转义，尽管它不是必须转义的字符（在 JSON 到 XML 的映射上不必对它进行转义）。</span><span class="sxs-lookup"><span data-stu-id="32e69-267">The "/" character, even though it is not a character that must be escaped, is escaped nevertheless (it does not have to be escaped on JSON to XML mapping).</span></span> <span data-ttu-id="32e69-268">这是支持 JSON 中 `DateTime` 数据的 ASP.NET AJAX 格式所必需的。</span><span class="sxs-lookup"><span data-stu-id="32e69-268">This is required to support the ASP.NET AJAX format for `DateTime` data in JSON.</span></span>  
  
-   <span data-ttu-id="32e69-269">在 JSON 到 XML 的映射上，提取所有字符（如有必要，则包括未转义的字符）以构成一个生成 [本地名称] 的 `string`。</span><span class="sxs-lookup"><span data-stu-id="32e69-269">On the JSON to XML mapping, all characters (including the not escaped characters, if necessary) are taken to form a `string` that produces a [local name].</span></span>  
  
-   <span data-ttu-id="32e69-270">按照 `JSON Type Attribute`，内部元素 [子级] 映射到第 2.2 节中的值，就像 `Root JSON Element` 那样。</span><span class="sxs-lookup"><span data-stu-id="32e69-270">Inner elements [children] map to the value in section 2.2, according to the `JSON Type Attribute` just like for the `Root JSON Element`.</span></span> <span data-ttu-id="32e69-271">允许 EII 的多级嵌套（包括数组中的嵌套）。</span><span class="sxs-lookup"><span data-stu-id="32e69-271">Multiple levels of nesting of EIIs (including nesting within arrays) are allowed.</span></span>  
  
 <span data-ttu-id="32e69-272">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-272">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="object">`  
  
 `<myLocalName1 type="string">myValue1</myLocalName1>`  
  
 `<myLocalName2 type="number">2</myLocalName2>`  
  
 `<myLocalName3 type="object">`  
  
 `<myNestedName1 type="boolean">true</myNestedName1>`  
  
 `<myNestedName2 type="null"/>`  
  
 `</myLocalName3>`  
  
 `</root >`  
  
 <span data-ttu-id="32e69-273">下面的 JSON 片段是它映射到的内容。</span><span class="sxs-lookup"><span data-stu-id="32e69-273">The following JSON fragment is what it maps to.</span></span>  
  
 `{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}`  
  
> [!NOTE]
>  <span data-ttu-id="32e69-274">在前面的映射中没有 XML 编码步骤。</span><span class="sxs-lookup"><span data-stu-id="32e69-274">There is no XML encoding step in the preceding mapping.</span></span> <span data-ttu-id="32e69-275">因此，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 仅支持其中密钥名称包含的所有字符都是 XML 元素名称中的有效字符的 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="32e69-275">Therefore, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only supports JSON documents where all characters in key names are valid characters in XML element names.</span></span> <span data-ttu-id="32e69-276">例如，不支持 JSON 文档 {"<":"a"}，因为 < 不是 XML 元素的有效名称。</span><span class="sxs-lookup"><span data-stu-id="32e69-276">For example, the JSON document {"<":"a"} is not supported because < is not a valid name for an XML element.</span></span>  
  
 <span data-ttu-id="32e69-277">相反的情况（字符在 XML 中有效而在 JSON 中无效）不会导致任何问题，因为上述映射包括 JSON 转义/取消转义步骤。</span><span class="sxs-lookup"><span data-stu-id="32e69-277">The reverse situation (characters valid in XML but not in JSON) does not cause any problems because the preceding mapping includes JSON escaping/unescaping steps.</span></span>  
  
 <span data-ttu-id="32e69-278">数组记录的工作原理如下：</span><span class="sxs-lookup"><span data-stu-id="32e69-278">Array Records work as follows:</span></span>  
  
-   <span data-ttu-id="32e69-279">内部元素的 [本地名称] 是“item”。</span><span class="sxs-lookup"><span data-stu-id="32e69-279">Inner element’s [local name] is "item".</span></span>  
  
-   <span data-ttu-id="32e69-280">按照 JSON 类型属性，内部元素的 [子级] 映射到第 2.3 节中的值，Root JSON 元素也是这样。</span><span class="sxs-lookup"><span data-stu-id="32e69-280">Inner element’s [children] map to the value in section 2.3, according to the JSON Type Attribute as is does for the Root JSON Element.</span></span> <span data-ttu-id="32e69-281">允许 EII 的多级嵌套（包括对象内的嵌套）。</span><span class="sxs-lookup"><span data-stu-id="32e69-281">Multiple levels of nesting of EIIs (including nesting within objects) are allowed.</span></span>  
  
 <span data-ttu-id="32e69-282">示例：下面的元素映射到 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-282">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="array"/>`  
  
 `<item type="string">myValue1</item>`  
  
 `<item type="number">2</item>`  
  
 `<item type="array">`  
  
 `<item type="boolean">true</item>`  
  
 `<item type="null"/>`  
  
 `</item>`  
  
 `</root >`  
  
 <span data-ttu-id="32e69-283">下面是 JSON 片段。</span><span class="sxs-lookup"><span data-stu-id="32e69-283">The following is the JSON fragment.</span></span>  
  
 `["myValue1",2,[true,null]]`  
  
## <a name="see-also"></a><span data-ttu-id="32e69-284">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32e69-284">See Also</span></span>  
 <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
 [<span data-ttu-id="32e69-285">独立 JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="32e69-285">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
