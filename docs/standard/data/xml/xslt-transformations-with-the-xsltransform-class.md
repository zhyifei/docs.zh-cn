---
title: "XslTransform 类的 XSLT 转换"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 619e37ab63735ea77d3afb0d94f284b2f310efc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="754f7-102">XslTransform 类的 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="754f7-102">XSLT Transformations with the XslTransform Class</span></span>
> [!NOTE]
>  <span data-ttu-id="754f7-103">
          <xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="754f7-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="754f7-104">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="754f7-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="754f7-105">请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[迁移从 XslTransform 类](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="754f7-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="754f7-106">XSLT 的目标是将源 XML 文档的内容转换为格式或结构不同的另一个文档（例如，将 XML 转换为在网站上使用的 HTML，或将其转换为只包含应用程序所需字段的文档）。</span><span class="sxs-lookup"><span data-stu-id="754f7-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="754f7-107">此转换过程由万维网联合会 (W3C) XSLT 1.0 版建议位于 www.w3.org/TR/xslt 指定。</span><span class="sxs-lookup"><span data-stu-id="754f7-107">This transformation process is specified by the World Wide Web Consortium (W3C) XSLT version 1.0 recommendation located at www.w3.org/TR/xslt.</span></span> <span data-ttu-id="754f7-108">在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 中，<xref:System.Xml.Xsl.XslTransform> 命名空间中的 <xref:System.Xml.Xsl> 类是实现此规范功能的 XSLT 处理器。</span><span class="sxs-lookup"><span data-stu-id="754f7-108">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="754f7-109">有少量的未实现的 W3C XSLT 1.0 建议中, 列出的功能[XslTransform 的输出](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)。</span><span class="sxs-lookup"><span data-stu-id="754f7-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="754f7-110">下图显示 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 的转换结构。</span><span class="sxs-lookup"><span data-stu-id="754f7-110">The following figure shows the transformation architecture of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="overview"></a><span data-ttu-id="754f7-111">概述</span><span class="sxs-lookup"><span data-stu-id="754f7-111">Overview</span></span>  
 <span data-ttu-id="754f7-112">![XSLT 转换体系结构](../../../../docs/standard/data/xml/media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span><span class="sxs-lookup"><span data-stu-id="754f7-112">![XSLT Transformation Architecture](../../../../docs/standard/data/xml/media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span></span>  
<span data-ttu-id="754f7-113">转换结构</span><span class="sxs-lookup"><span data-stu-id="754f7-113">Transformation Architecture</span></span>  
  
 <span data-ttu-id="754f7-114">XSLT 建议使用 XML 路径语言 (XPath) 选择 XML 文档的各部分，其中 XPath 是用于浏览文档树节点的查询语言。</span><span class="sxs-lookup"><span data-stu-id="754f7-114">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="754f7-115">如图所示，[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 实现的 XPath 用来选择存储在几个类中的 XML 部分，如 <xref:System.Xml.XmlDocument>、<xref:System.Xml.XmlDataDocument> 和 <xref:System.Xml.XPath.XPathDocument> 类。</span><span class="sxs-lookup"><span data-stu-id="754f7-115">As shown in the diagram, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="754f7-116"><xref:System.Xml.XPath.XPathDocument> 是一个优化的 XSLT 数据存储区，当与 <xref:System.Xml.Xsl.XslTransform> 一起使用时，可以提供性能良好的 XSLT 转换。</span><span class="sxs-lookup"><span data-stu-id="754f7-116">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>  
  
 <span data-ttu-id="754f7-117">下表列出了在使用 <xref:System.Xml.Xsl.XslTransform> 和 XPath 时常用的类及其功能。</span><span class="sxs-lookup"><span data-stu-id="754f7-117">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>  
  
|<span data-ttu-id="754f7-118">类或接口</span><span class="sxs-lookup"><span data-stu-id="754f7-118">Class or Interface</span></span>|<span data-ttu-id="754f7-119">函数</span><span class="sxs-lookup"><span data-stu-id="754f7-119">Function</span></span>|  
|------------------------|--------------|  
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="754f7-120">它是提供用于在存储区上浏览的游标样式模型以及 XPath 查询支持的 API。</span><span class="sxs-lookup"><span data-stu-id="754f7-120">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="754f7-121">它不提供对基础存储区的编辑。</span><span class="sxs-lookup"><span data-stu-id="754f7-121">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="754f7-122">要进行编辑，请使用 <xref:System.Xml.XmlDocument> 类。</span><span class="sxs-lookup"><span data-stu-id="754f7-122">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|  
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="754f7-123">它是为存储区提供 `CreateNavigator` 的 <xref:System.Xml.XPath.XPathNavigator> 方法的接口。</span><span class="sxs-lookup"><span data-stu-id="754f7-123">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|  
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="754f7-124">它启用对此文档的编辑。</span><span class="sxs-lookup"><span data-stu-id="754f7-124">It enables editing of this document.</span></span> <span data-ttu-id="754f7-125">它实现 <xref:System.Xml.XPath.IXPathNavigable>，从而允许随后需要 XSLT 转换的文档编辑方案。</span><span class="sxs-lookup"><span data-stu-id="754f7-125">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="754f7-126">有关详细信息，请参阅[xsltransform 的 XmlDocument 输入](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)。</span><span class="sxs-lookup"><span data-stu-id="754f7-126">For more information, see [XmlDocument Input to XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md).</span></span>|  
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="754f7-127">它从 <xref:System.Xml.XmlDocument> 派生。</span><span class="sxs-lookup"><span data-stu-id="754f7-127">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="754f7-128">它根据 <xref:System.Data.DataSet> 的指定映射，使用 <xref:System.Data.DataSet> 优化 XML 文档中的结构化数据存储，从而将关系世界与 XML 世界联系起来。</span><span class="sxs-lookup"><span data-stu-id="754f7-128">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="754f7-129">它实现 <xref:System.Xml.XPath.IXPathNavigable>，从而允许可以对从数据库中检索到的关系数据执行 XSLT 转换的方案。</span><span class="sxs-lookup"><span data-stu-id="754f7-129">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="754f7-130">有关详细信息，请参阅[关系数据和 ADO.NET 的 XML 集成](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)。</span><span class="sxs-lookup"><span data-stu-id="754f7-130">For more information, see [XML Integration with Relational Data and ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).</span></span>|  
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="754f7-131">此类针对 <xref:System.Xml.Xsl.XslTransform> 处理和 XPath 查询进行了优化，并提供只读的高性能缓存。</span><span class="sxs-lookup"><span data-stu-id="754f7-131">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="754f7-132">它实现 <xref:System.Xml.XPath.IXPathNavigable>，是用于 XSLT 转换的首选存储区。</span><span class="sxs-lookup"><span data-stu-id="754f7-132">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="754f7-133">它提供在 XPath 节点集上的浏览。</span><span class="sxs-lookup"><span data-stu-id="754f7-133">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="754f7-134"><xref:System.Xml.XPath.XPathNavigator> 的所有 XPath 选择方法都返回 <xref:System.Xml.XPath.XPathNodeIterator>。</span><span class="sxs-lookup"><span data-stu-id="754f7-134">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="754f7-135">可以在同一存储区上创建多个 <xref:System.Xml.XPath.XPathNodeIterator> 对象，每个对象表示一个选定的节点集。</span><span class="sxs-lookup"><span data-stu-id="754f7-135">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|  
  
## <a name="msxml-xslt-extensions"></a><span data-ttu-id="754f7-136">MSXML XSLT 扩展</span><span class="sxs-lookup"><span data-stu-id="754f7-136">MSXML XSLT Extensions</span></span>  
 <span data-ttu-id="754f7-137">`msxsl:script` 和 `msxsl:node-set` 函数是 <xref:System.Xml.Xsl.XslTransform> 类唯一支持的 Microsoft XML 核心服务 (MSXML) XSLT 扩展。</span><span class="sxs-lookup"><span data-stu-id="754f7-137">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="754f7-138">示例</span><span class="sxs-lookup"><span data-stu-id="754f7-138">Example</span></span>  
 <span data-ttu-id="754f7-139">下面的代码示例加载一个 XSL 样式表，将一个称为 mydata.xml 的文件读入 <xref:System.Xml.XPath.XPathDocument> 中，并对一个称为 myStyleSheet.xsl 的虚构文件上的数据执行转换，将格式化的输出发送到控制台。</span><span class="sxs-lookup"><span data-stu-id="754f7-139">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
    Private filename As [String] = "mydata.xml"  
    Private stylesheet As [String] = "myStyleSheet.xsl"  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load(stylesheet)  
        Dim xpathdocument As New XPathDocument(filename)  
        Dim writer As New XmlTextWriter(Console.Out)  
        writer.Formatting = Formatting.Indented  
  
        xslt.Transform(xpathdocument, Nothing, writer, Nothing)  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample   
{  
    private const String filename = "mydata.xml";  
    private const String stylesheet = "myStyleSheet.xsl";  
  
    public static void Main()   
    {  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
    XPathDocument xpathdocument = new  
    XPathDocument(filename);  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting=Formatting.Indented;  
  
    xslt.Transform(xpathdocument, null, writer, null);      
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="754f7-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="754f7-140">See Also</span></span>  
 <xref:System.Xml.Xsl.XslTransform>  
 [<span data-ttu-id="754f7-141">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="754f7-141">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="754f7-142">XslTransform 类中的任意行为的实现</span><span class="sxs-lookup"><span data-stu-id="754f7-142">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](../../../../docs/standard/data/xml/implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)  
 [<span data-ttu-id="754f7-143">转换中的 XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="754f7-143">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="754f7-144">转换中的 XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="754f7-144">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="754f7-145">Xsltransform 的 XPathDocument 输入</span><span class="sxs-lookup"><span data-stu-id="754f7-145">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="754f7-146">Xsltransform 的 XmlDataDocument 输入</span><span class="sxs-lookup"><span data-stu-id="754f7-146">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [<span data-ttu-id="754f7-147">Xsltransform 的 XmlDocument 输入</span><span class="sxs-lookup"><span data-stu-id="754f7-147">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
