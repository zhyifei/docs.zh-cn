---
title: "使用 XML 声明 (Visual Basic 中) 进行序列化 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 50707da956df593f176764bed94adfc6aec3dfa5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="8c783-102">使用 XML 声明 (Visual Basic 中) 进行序列化</span><span class="sxs-lookup"><span data-stu-id="8c783-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="8c783-103">本主题说明如何控制序列化是否生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="8c783-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="8c783-104">XML 声明的生成</span><span class="sxs-lookup"><span data-stu-id="8c783-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="8c783-105">序列化为<xref:System.IO.File>或<xref:System.IO.TextWriter>使用<xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>方法或<xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>方法生成 XML 声明。</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="8c783-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="8c783-106">在序列化为<xref:System.Xml.XmlWriter>，编写器设置 (在指定<xref:System.Xml.XmlWriterSettings>对象) 确定是否生成 XML 声明。</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="8c783-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="8c783-107">如果要使用 `ToString` 方法序列化为字符串，则生成的 XML 不会包括 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="8c783-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="8c783-108">使用 XML 声明进行序列化</span><span class="sxs-lookup"><span data-stu-id="8c783-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="8c783-109">下面的示例创建<xref:System.Xml.Linq.XElement>、 将文档保存到文件中，并打印到控制台文件︰</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="8c783-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="8c783-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="8c783-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="8c783-111">不带 XML 声明的序列化</span><span class="sxs-lookup"><span data-stu-id="8c783-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="8c783-112">下面的示例演示如何将保存<xref:System.Xml.Linq.XElement>到<xref:System.Xml.XmlWriter>。</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="8c783-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="8c783-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="8c783-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c783-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c783-114">See Also</span></span>  
 [<span data-ttu-id="8c783-115">序列化 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c783-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
