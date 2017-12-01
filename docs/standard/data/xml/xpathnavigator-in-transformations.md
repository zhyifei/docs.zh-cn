---
title: "转换中的 XPathNavigator"
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
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f89708607ada18181bc6605994c7908e1dd14b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xpathnavigator-in-transformations"></a>转换中的 XPathNavigator
<xref:System.Xml.XPath.XPathNavigator> 类提供对数据的只读随机访问，旨在用作可扩展样式表语言转换 (XSLT) 的输入。 它在 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDataDocument> 和 <xref:System.Xml.XmlDocument> 上实现。 <xref:System.Xml.XPath.XPathNavigator> 基于 XML 路径语言 (XPath) 建议第 5 节中所述的万维网联合会 (W3C) 数据模型。  
  
 <xref:System.Xml.XPath.XPathNavigator> 定义一个适用于任何存储区的游标模型，并提供对任何数据存储区的快速、只读 XPath 查询。 <xref:System.Xml.XPath.XPathNavigator> 还是用来循环访问结果树片段的类。  
  
 API 使您能够从存储区的当前节点中获取信息，并移动到连接的节点。 <xref:System.Xml.XPath.XPathNavigator>是存储区中使用的一组上执行遍历的游标样式模型**移动**方法。 <xref:System.Xml.XPath.XPathNavigator> 总是定位在节点上。 任何**移动**失败的方法<xref:System.Xml.XPath.XPathNavigator>不变。  
  
 <xref:System.Xml.XPath.XPathNavigator> 是用来循环访问结果树片段的类。 下面的代码示例通过调用带参数 `fragment`（包含 XML）的函数，在样式表中创建一个结果树片段。  
  
## <a name="testxsl"></a>test.xsl  
  
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
  
## <a name="testxml"></a>test.xml  
  
```xml  
<root>Some text</root>  
```  
  
 下面的代码使用**test.xsl**样式表和**test.xml**输入数据。  
  
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
  
## <a name="output"></a>输出  
 在文件中找到的转换结果**out.xml**:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a>另请参阅  
 [XslTransform 类实现 XSLT 处理器](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
