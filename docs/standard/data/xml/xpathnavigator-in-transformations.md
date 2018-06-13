---
title: 转换中的 XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76cfa51c7d434a6dfdcdc1e6852779decaa601e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570447"
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="a7ca3-102">转换中的 XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a7ca3-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="a7ca3-103"><xref:System.Xml.XPath.XPathNavigator> 类提供对数据的只读随机访问，旨在用作可扩展样式表语言转换 (XSLT) 的输入。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="a7ca3-104">它在 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDataDocument> 和 <xref:System.Xml.XmlDocument> 上实现。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="a7ca3-105"><xref:System.Xml.XPath.XPathNavigator> 基于 XML 路径语言 (XPath) 建议第 5 节中所述的万维网联合会 (W3C) 数据模型。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="a7ca3-106"><xref:System.Xml.XPath.XPathNavigator> 定义一个适用于任何存储区的游标模型，并提供对任何数据存储区的快速、只读 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="a7ca3-107"><xref:System.Xml.XPath.XPathNavigator> 还是用来循环访问结果树片段的类。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="a7ca3-108">API 使您能够从存储区的当前节点中获取信息，并移动到连接的节点。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="a7ca3-109"><xref:System.Xml.XPath.XPathNavigator> 是使用 Move 方法集遍历存储的游标样式模型。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="a7ca3-110"><xref:System.Xml.XPath.XPathNavigator> 总是定位在节点上。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="a7ca3-111">只要 Move 方法失败，<xref:System.Xml.XPath.XPathNavigator> 就会保持不变。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="a7ca3-112"><xref:System.Xml.XPath.XPathNavigator> 是用来循环访问结果树片段的类。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="a7ca3-113">下面的代码示例通过调用带参数 `fragment`（包含 XML）的函数，在样式表中创建一个结果树片段。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="a7ca3-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="a7ca3-114">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="a7ca3-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="a7ca3-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="a7ca3-116">下面的代码使用 test.xsl 样式表和 test.xml 输入数据。</span><span class="sxs-lookup"><span data-stu-id="a7ca3-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
    End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a><span data-ttu-id="a7ca3-117">输出</span><span class="sxs-lookup"><span data-stu-id="a7ca3-117">Output</span></span>  
 <span data-ttu-id="a7ca3-118">转换结果位于文件 out.xml 中：</span><span class="sxs-lookup"><span data-stu-id="a7ca3-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7ca3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7ca3-119">See Also</span></span>  
 [<span data-ttu-id="a7ca3-120">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="a7ca3-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
