---
title: "用来控制编码的 SOAP 序列化的属性"
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
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: a6af8cd2560bb9c39657d8e5b088954996ba2a04
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="ece05-102">用来控制编码的 SOAP 序列化的属性</span><span class="sxs-lookup"><span data-stu-id="ece05-102">Attributes That Control Encoded SOAP Serialization</span></span> 
<span data-ttu-id="ece05-103">命名为“简单对象访问协议 (SOAP) 1.1”(Simple Object Access Protocol (SOAP) 1.1) 的万维网联合会 (www.w3.org) 文档包含一个可选章节（第 5 节），该节描述了如何编码 SOAP 参数。</span><span class="sxs-lookup"><span data-stu-id="ece05-103">The World Wide Web Consortium (www.w3.org) document named "Simple Object Access Protocol (SOAP) 1.1" contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="ece05-104">要符合该规范的第 5 节，必须使用在 <xref:System.Xml.Serialization> 命名空间中找到的一组特殊属性。</span><span class="sxs-lookup"><span data-stu-id="ece05-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="ece05-105">将这些特性适当应用于类和类的成员，然后使用 <xref:System.Xml.Serialization.XmlSerializer> 序列化一个或多个类的实例。</span><span class="sxs-lookup"><span data-stu-id="ece05-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>  
  
 <span data-ttu-id="ece05-106">下表显示属性、属性的应用范围及其作用。</span><span class="sxs-lookup"><span data-stu-id="ece05-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="ece05-107">有关使用这些属性控制 XML 序列化的更多信息，请参阅[如何：将对象序列化为 SOAP 编码的 XML 流](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)和[如何：替代编码的 SOAP XML 序列化](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="ece05-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span></span>  
  
 <span data-ttu-id="ece05-108">有关属性的详细信息，请参阅[属性](../../../docs/standard/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ece05-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>  
  
|<span data-ttu-id="ece05-109">特性</span><span class="sxs-lookup"><span data-stu-id="ece05-109">Attribute</span></span>|<span data-ttu-id="ece05-110">适用对象</span><span class="sxs-lookup"><span data-stu-id="ece05-110">Applies to</span></span>|<span data-ttu-id="ece05-111">指定</span><span class="sxs-lookup"><span data-stu-id="ece05-111">Specifies</span></span>|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="ece05-112">公共字段、属性、参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="ece05-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="ece05-113">类成员将序列化为 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="ece05-113">The class member will be serialized as an XML attribute.</span></span>|  
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="ece05-114">公共字段、属性、参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="ece05-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="ece05-115">类将序列化为 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="ece05-115">The class will be serialized as an XML element.</span></span>|  
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="ece05-116">作为枚举标识符的公共字段。</span><span class="sxs-lookup"><span data-stu-id="ece05-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="ece05-117">枚举成员的元素名称。</span><span class="sxs-lookup"><span data-stu-id="ece05-117">The element name of an enumeration member.</span></span>|  
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="ece05-118">公共属性和公共字段。</span><span class="sxs-lookup"><span data-stu-id="ece05-118">Public properties and fields.</span></span>|<span data-ttu-id="ece05-119">序列化包含类时，应该忽略属性或字段。</span><span class="sxs-lookup"><span data-stu-id="ece05-119">The property or field should be ignored when the containing class is serialized.</span></span>|  
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="ece05-120">公共的派生类声明，以及 Web 服务描述语言 (WSDL) 文档的公共方法。</span><span class="sxs-lookup"><span data-stu-id="ece05-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="ece05-121">生成要在序列化时识别的架构时，应该将该类型包括在内。</span><span class="sxs-lookup"><span data-stu-id="ece05-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|  
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="ece05-122">公共类声明。</span><span class="sxs-lookup"><span data-stu-id="ece05-122">Public class declarations.</span></span>|<span data-ttu-id="ece05-123">类应序列化为 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="ece05-123">The class should be serialized as an XML type.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ece05-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ece05-124">See Also</span></span>  
 <span data-ttu-id="ece05-125">[XML 和 SOAP 序列化](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="ece05-125">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span></span>  
 <span data-ttu-id="ece05-126">[如何：将对象序列化为 SOAP 编码的 XML 流](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) </span><span class="sxs-lookup"><span data-stu-id="ece05-126">[How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) </span></span>  
 <span data-ttu-id="ece05-127">[如何：重写编码的 SOAP XML 序列化](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="ece05-127">[How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md) </span></span>  
 <span data-ttu-id="ece05-128">[特性](../../../docs/standard/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="ece05-128">[Attributes](../../../docs/standard/attributes/index.md) </span></span>  
 <span data-ttu-id="ece05-129"><xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="ece05-129"><xref:System.Xml.Serialization.XmlSerializer></span></span>   
 <span data-ttu-id="ece05-130">[如何：序列化对象](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="ece05-130">[How to: Serialize an Object](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span></span>  
 [<span data-ttu-id="ece05-131">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="ece05-131">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

