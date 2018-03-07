---
title: "XslTransform 的 XPathDocument 输入"
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
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 22adc805a1174b566d3febf8c6182527df59b32c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="b2738-102">XslTransform 的 XPathDocument 输入</span><span class="sxs-lookup"><span data-stu-id="b2738-102">XPathDocument Input to XslTransform</span></span>
<span data-ttu-id="b2738-103"><xref:System.Xml.XPath.XPathDocument> 是只读缓存，配合 <xref:System.Xml.Xsl.XslTransform> 处理文档。</span><span class="sxs-lookup"><span data-stu-id="b2738-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="b2738-104">它在结构上与 XML 文档对象模型 (DOM) 类似，但是已使用 <xref:System.Xml.XPath.XPathNavigator> 上的 XPath 优化功能，针对可扩展样式表语言转换 (XSLT) 处理和 XML 路径语言 (XPath) 数据模型进行了高度优化。</span><span class="sxs-lookup"><span data-stu-id="b2738-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2738-105"><xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="b2738-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="b2738-106">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="b2738-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="b2738-107">请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2738-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="b2738-108">下面的代码示例创建 <xref:System.Xml.XPath.XPathDocument> 作为转换的输入。</span><span class="sxs-lookup"><span data-stu-id="b2738-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2738-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2738-109">See Also</span></span>  
 [<span data-ttu-id="b2738-110">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="b2738-110">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
