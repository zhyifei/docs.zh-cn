---
title: "将 XML 文档读入 DOM"
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
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a>将 XML 文档读入 DOM
XML 信息从不同的格式读入内存。 读取源包括字符串、流、URL、文本读取器或 <xref:System.Xml.XmlReader> 的派生类。  
  
 <xref:System.Xml.XmlDocument.Load%2A> 方法将文档置入内存中并包含可用于从每个不同的格式中获取数据的重载方法。 还存在 <xref:System.Xml.XmlDocument.LoadXml%2A> 方法，该方法从字符串中读取 XML。  
  
 不同的 <xref:System.Xml.XmlDocument.Load%2A> 方法影响在加载 XML 文档对象模型 (DOM) 时创建的节点。 下表列出了一些 <xref:System.Xml.XmlDocument.Load%2A> 方法的区别以及讲述这些区别的主题。  
  
|Subject|主题|  
|-------------|-----------|  
|创建空白节点|用来加载 DOM 的对象对 DOM 中生成的空白和有效空白节点有影响。 有关详细信息，请参阅[空白和有效空白处理加载 DOM 时](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md)。|  
|从特定节点开始加载 XML 或加载整个 XML 文档|使用<xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType>方法数据可以从特定的节点加载到 dom 中。 有关详细信息，请参阅[从读取器的负载数据](../../../../docs/standard/data/xml/load-data-from-a-reader.md)。|  
|在 XML 加载时进行验证|加载到 DOM 中的 XML 数据可以在加载时进行验证。 使用验证 <xref:System.Xml.XmlReader> 可以完成此操作。 有关验证 XML 加载的详细信息，请参阅[验证 XML 文档在 DOM 中](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)。|  
  
 以下示例显示使用 <xref:System.Xml.XmlDocument.LoadXml%2A> 方法加载的 XML 以及之后保存到称为 `data.xml` 的文本文件的数据。  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
