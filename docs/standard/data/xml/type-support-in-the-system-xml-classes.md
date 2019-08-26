---
title: System.Xml 类中的类型支持
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 954ff12ae1ac8b4d601c35fcd76ea35b2bb3acbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939440"
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="016a7-102">System.Xml 类中的类型支持</span><span class="sxs-lookup"><span data-stu-id="016a7-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="016a7-103">在 .NET Framework 2.0 版中，核心 XML 类已得到增强，具有类型支持功能。</span><span class="sxs-lookup"><span data-stu-id="016a7-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="016a7-104"><xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 和 <xref:System.Xml.XPath.XPathNavigator> 类具有类型支持功能，可以在 XML 架构类型和公共语言运行库 (CLR) 类型之间转换。</span><span class="sxs-lookup"><span data-stu-id="016a7-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="016a7-105">在 .NET Framework 2.0 版中，<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 和 <xref:System.Xml.XPath.XPathNavigator> 类已得到增强，具有类型支持功能。</span><span class="sxs-lookup"><span data-stu-id="016a7-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
- <span data-ttu-id="016a7-106"><xref:System.Xml.XmlReader> 和 <xref:System.Xml.XPath.XPathNavigator> 类均包含 SchemaInfo  属性，用于返回节点的架构信息。</span><span class="sxs-lookup"><span data-stu-id="016a7-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
- <span data-ttu-id="016a7-107">ReadContentAs  和 ReadElementContentAs  以及 <xref:System.Xml.XmlReader> 类的方法在一个方法调用中，读取文本值并将它转换为 CLR 值。</span><span class="sxs-lookup"><span data-stu-id="016a7-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
- <span data-ttu-id="016a7-108">在写出 XML 时，<xref:System.Xml.XmlWriter.WriteValue%2A> 类的 <xref:System.Xml.XmlWriter> 方法将 CLR 类型转换为 XML 架构类型。</span><span class="sxs-lookup"><span data-stu-id="016a7-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
- <span data-ttu-id="016a7-109"><xref:System.Xml.XPath.XPathNavigator> 类的 ValueAs  和 <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> 属性在一个方法调用中，返回节点值并将它转换为 CLR 值。</span><span class="sxs-lookup"><span data-stu-id="016a7-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="016a7-110">在 .NET Framework 1.0 版中，需要使用 <xref:System.Xml.XmlConvert> 类在 XML 架构和 CLR 类型之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="016a7-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="016a7-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="016a7-111">In This Section</span></span>  
 [<span data-ttu-id="016a7-112">将 XML 数据类型映射到 CLR 类型</span><span class="sxs-lookup"><span data-stu-id="016a7-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="016a7-113">介绍 XML 数据类型与 CLR 类型的默认映射。</span><span class="sxs-lookup"><span data-stu-id="016a7-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="016a7-114">XML 类型支持实现说明</span><span class="sxs-lookup"><span data-stu-id="016a7-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="016a7-115">介绍一些类型支持实现的详细信息。</span><span class="sxs-lookup"><span data-stu-id="016a7-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="016a7-116">XML 数据类型转换</span><span class="sxs-lookup"><span data-stu-id="016a7-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="016a7-117">描述如何使用 <xref:System.Xml.XmlConvert> 类在 XML 架构和 CLR 类型之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="016a7-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="016a7-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="016a7-118">Related Sections</span></span>  
 [<span data-ttu-id="016a7-119">使用 XPathNavigator 访问强类型 XML 数据</span><span class="sxs-lookup"><span data-stu-id="016a7-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
