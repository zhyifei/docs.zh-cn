---
title: 带 XML 声明的序列化 (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 613280efc8c734c53c4af9252b4b83e2dd942f36
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586283"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="6afae-102">带 XML 声明的序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="6afae-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="6afae-103">本主题说明如何控制序列化是否生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="6afae-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="6afae-104">XML 声明的生成</span><span class="sxs-lookup"><span data-stu-id="6afae-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="6afae-105">使用 <xref:System.IO.File> 方法或 <xref:System.IO.TextWriter> 方法序列化为 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> 或 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> 将生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="6afae-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="6afae-106">在序列化为 <xref:System.Xml.XmlWriter> 时，编写器设置（在 <xref:System.Xml.XmlWriterSettings> 对象中指定）将确定是否生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="6afae-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="6afae-107">如果要使用 `ToString` 方法序列化为字符串，则生成的 XML 不会包括 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="6afae-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="6afae-108">使用 XML 声明进行序列化</span><span class="sxs-lookup"><span data-stu-id="6afae-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="6afae-109">下面的示例创建一个 <xref:System.Xml.Linq.XElement>，将文档保存到文件，然后将文件打印到控制台：</span><span class="sxs-lookup"><span data-stu-id="6afae-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="6afae-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="6afae-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="6afae-111">不带 XML 声明的序列化</span><span class="sxs-lookup"><span data-stu-id="6afae-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="6afae-112">下面的示例演示如何将一个 <xref:System.Xml.Linq.XElement> 保存到一个 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="6afae-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="6afae-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="6afae-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6afae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6afae-114">See Also</span></span>

- [<span data-ttu-id="6afae-115">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="6afae-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
