---
title: XML 和 SOAP 序列化
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: 4ca812c03949cb6a2cb903ae041e54311e9486bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591513"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="de46d-102">XML 和 SOAP 序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-102">XML and SOAP Serialization</span></span>
<span data-ttu-id="de46d-103">XML 序列化将对象的公共字段和属性或者方法的参数及返回值转换（序列化）为符合特定 XML 架构定义语言 (XSD) 文档的 XML 流。</span><span class="sxs-lookup"><span data-stu-id="de46d-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="de46d-104">XML 序列化会生成强类型类，同时将公共属性和字段转换为序列格式（在此情况下为 XML），以便存储或传输。</span><span class="sxs-lookup"><span data-stu-id="de46d-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>  
  
 <span data-ttu-id="de46d-105">由于 XML 是开放式的标准，因此可以根据需要由任何应用程序处理 XML 流，而与平台无关。</span><span class="sxs-lookup"><span data-stu-id="de46d-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="de46d-106">例如，用 ASP.NET 创建的 XML Web services 使用 <xref:System.Xml.Serialization.XmlSerializer> 类来创建 XML 流，这些流在整个 Internet 中或在 Intranet 上的 XML Web services 应用程序之间传递数据。</span><span class="sxs-lookup"><span data-stu-id="de46d-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="de46d-107">相反，反序列化采用这样一个 XML 流并重新构造对象。</span><span class="sxs-lookup"><span data-stu-id="de46d-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>  
  
 <span data-ttu-id="de46d-108">XML 序列化还可用于将对象序列化为符合 SOAP 规范的 XML 流。</span><span class="sxs-lookup"><span data-stu-id="de46d-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="de46d-109">SOAP 是一种基于 XML 的协议，它是专门为使用 XML 来传输过程调用而设计的。</span><span class="sxs-lookup"><span data-stu-id="de46d-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>  
  
 <span data-ttu-id="de46d-110">若要序列化或反序列化对象，请使用 <xref:System.Xml.Serialization.XmlSerializer> 类。</span><span class="sxs-lookup"><span data-stu-id="de46d-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="de46d-111">要创建待序列化的类，请使用 XML 架构定义工具。</span><span class="sxs-lookup"><span data-stu-id="de46d-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de46d-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="de46d-112">In This Section</span></span>  
 [<span data-ttu-id="de46d-113">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="de46d-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 <span data-ttu-id="de46d-114">提供序列化（尤其是 XML 序列化）的一般定义。</span><span class="sxs-lookup"><span data-stu-id="de46d-114">Provides a general definition of serialization, particularly XML serialization.</span></span>  
  
 [<span data-ttu-id="de46d-115">如何：序列化对象</span><span class="sxs-lookup"><span data-stu-id="de46d-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 <span data-ttu-id="de46d-116">提供序列化对象的分步说明。</span><span class="sxs-lookup"><span data-stu-id="de46d-116">Provides step-by-step instructions for serializing an object.</span></span>  
  
 [<span data-ttu-id="de46d-117">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="de46d-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 <span data-ttu-id="de46d-118">提供反序列化对象的分步说明。</span><span class="sxs-lookup"><span data-stu-id="de46d-118">Provides step-by-step instructions for deserializing an object.</span></span>  
  
 [<span data-ttu-id="de46d-119">XML 序列化示例</span><span class="sxs-lookup"><span data-stu-id="de46d-119">Examples of XML Serialization</span></span>](../../../docs/standard/serialization/examples-of-xml-serialization.md)  
 <span data-ttu-id="de46d-120">提供说明 XML 序列化基础的示例。</span><span class="sxs-lookup"><span data-stu-id="de46d-120">Provides examples that demonstrate the basics of XML serialization.</span></span>  
  
 [<span data-ttu-id="de46d-121">XML 架构定义工具和 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-121">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 <span data-ttu-id="de46d-122">描述如何使用 XML 架构定义工具创建遵循特定 XML 架构定义语言 (XSD) 架构的类，或者利用 .dll 文件生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="de46d-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>  
  
 [<span data-ttu-id="de46d-123">使用属性控制 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-123">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 <span data-ttu-id="de46d-124">描述如何使用属性控制序列化。</span><span class="sxs-lookup"><span data-stu-id="de46d-124">Describes how to control serialization by using attributes.</span></span>  
  
 [<span data-ttu-id="de46d-125">用来控制 XML 序列化的属性</span><span class="sxs-lookup"><span data-stu-id="de46d-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 <span data-ttu-id="de46d-126">列出用于控制 XML 序列化的属性。</span><span class="sxs-lookup"><span data-stu-id="de46d-126">Lists the attributes that are used to control XML serialization.</span></span>  
  
 [<span data-ttu-id="de46d-127">如何：指定 XML 流的替代元素名称</span><span class="sxs-lookup"><span data-stu-id="de46d-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 <span data-ttu-id="de46d-128">提供一个高级方案，显示如何通过重写序列化来生成多个 XML 流。</span><span class="sxs-lookup"><span data-stu-id="de46d-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>  
  
 [<span data-ttu-id="de46d-129">如何：控制派生类的序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-129">How to: Control Serialization of Derived Classes</span></span>](../../../docs/standard/serialization/how-to-control-serialization-of-derived-classes.md)  
 <span data-ttu-id="de46d-130">提供如何控制派生类的序列化的示例。</span><span class="sxs-lookup"><span data-stu-id="de46d-130">Provides an example of how to control the serialization of derived classes.</span></span>  
  
 [<span data-ttu-id="de46d-131">如何：限定 XML 元素和 XML 属性名</span><span class="sxs-lookup"><span data-stu-id="de46d-131">How to: Qualify XML Element and XML Attribute Names</span></span>](../../../docs/standard/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 <span data-ttu-id="de46d-132">描述如何定义和控制 XML 命名空间在 XML 流中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="de46d-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>  
  
 [<span data-ttu-id="de46d-133">使用 XML Web services 进行 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-133">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 <span data-ttu-id="de46d-134">说明如何在 XML Web services 中使用 XML 序列化。</span><span class="sxs-lookup"><span data-stu-id="de46d-134">Explains how XML serialization is used in XML Web services.</span></span>  
  
 [<span data-ttu-id="de46d-135">如何：将对象序列化为 SOAP 编码的 XML 流</span><span class="sxs-lookup"><span data-stu-id="de46d-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 <span data-ttu-id="de46d-136">描述如何使用 <xref:System.Xml.Serialization.XmlSerializer> 类来创建编码的 SOAP XML 流，这些流符合万维网联合会 (www.w3.org) 文档“简单对象访问协议 (SOAP) 1.1”(Simple Object Access Protocol (SOAP) 1.1) 的第 5 节。</span><span class="sxs-lookup"><span data-stu-id="de46d-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (www.w3.org) document titled "Simple Object Access Protocol (SOAP) 1.1."</span></span>  
  
 [<span data-ttu-id="de46d-137">如何：重写编码的 SOAP XML 序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-137">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 <span data-ttu-id="de46d-138">描述将对象的 XML 序列化重写为 SOAP 消息的过程。</span><span class="sxs-lookup"><span data-stu-id="de46d-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>  
  
 [<span data-ttu-id="de46d-139">用来控制编码的 SOAP 序列化的属性</span><span class="sxs-lookup"><span data-stu-id="de46d-139">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 <span data-ttu-id="de46d-140">列出用于控制 SOAP 编码的序列化的属性。</span><span class="sxs-lookup"><span data-stu-id="de46d-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>  
  
 [<span data-ttu-id="de46d-141">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="de46d-141">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 <span data-ttu-id="de46d-142">用于控制 XML 序列化的顶级配置元素。</span><span class="sxs-lookup"><span data-stu-id="de46d-142">The top-level configuration element for controlling XML serialization.</span></span>  
  
 [<span data-ttu-id="de46d-143">\<dateTimeSerialization> 元素</span><span class="sxs-lookup"><span data-stu-id="de46d-143">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 <span data-ttu-id="de46d-144">控制 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="de46d-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 [<span data-ttu-id="de46d-145">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="de46d-145">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 <span data-ttu-id="de46d-146">包含 <xref:System.Xml.Serialization.XmlSchemaImporter> 类所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="de46d-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
 [<span data-ttu-id="de46d-147">\<xmlSchemaImporterExtensions> 的 \<add> 元素</span><span class="sxs-lookup"><span data-stu-id="de46d-147">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 <span data-ttu-id="de46d-148">添加 <xref:System.Xml.Serialization.XmlSchemaImporter> 类所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="de46d-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de46d-149">相关章节</span><span class="sxs-lookup"><span data-stu-id="de46d-149">Related Sections</span></span>  
 [<span data-ttu-id="de46d-150">高级开发技术</span><span class="sxs-lookup"><span data-stu-id="de46d-150">Advanced Development Technologies</span></span>](https://msdn.microsoft.com/library/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 <span data-ttu-id="de46d-151">提供链接来指向关于 .NET Framework 中完善的开发任务和技术的更多信息。</span><span class="sxs-lookup"><span data-stu-id="de46d-151">Provides links to more information on sophisticated development tasks and techniques in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="de46d-152">使用 ASP.NET 创建的 XML Web service 以及 XML Web Service 客户端</span><span class="sxs-lookup"><span data-stu-id="de46d-152">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="de46d-153">提供一些主题，描述并说明如何使用 ASP.NET 对 XML Web services 进行编程。</span><span class="sxs-lookup"><span data-stu-id="de46d-153">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de46d-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="de46d-154">See Also</span></span>  
 [<span data-ttu-id="de46d-155">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="de46d-155">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
