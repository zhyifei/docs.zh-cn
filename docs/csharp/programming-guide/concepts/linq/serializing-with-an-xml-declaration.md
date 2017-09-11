---
title: "带 XML 声明的序列化 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36ffb8ddd584785c660896ca77707d504638852f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="9690f-102">带 XML 声明的序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="9690f-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="9690f-103">本主题说明如何控制序列化是否生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="9690f-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="9690f-104">XML 声明的生成</span><span class="sxs-lookup"><span data-stu-id="9690f-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="9690f-105">使用 <xref:System.IO.File> 方法或 <xref:System.IO.TextWriter> 方法序列化为 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> 或 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> 将生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="9690f-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="9690f-106">在序列化为 <xref:System.Xml.XmlWriter> 时，编写器设置（在 <xref:System.Xml.XmlWriterSettings> 对象中指定）将确定是否生成 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="9690f-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="9690f-107">如果要使用 `ToString` 方法序列化为字符串，则生成的 XML 不会包括 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="9690f-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="9690f-108">使用 XML 声明进行序列化</span><span class="sxs-lookup"><span data-stu-id="9690f-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="9690f-109">下面的示例创建一个 <xref:System.Xml.Linq.XElement>，将文档保存到文件，然后将文件打印到控制台：</span><span class="sxs-lookup"><span data-stu-id="9690f-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="9690f-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="9690f-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="9690f-111">不带 XML 声明的序列化</span><span class="sxs-lookup"><span data-stu-id="9690f-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="9690f-112">下面的示例演示如何将一个 <xref:System.Xml.Linq.XElement> 保存到一个 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="9690f-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="9690f-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="9690f-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9690f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9690f-114">See Also</span></span>  
 [<span data-ttu-id="9690f-115">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="9690f-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

