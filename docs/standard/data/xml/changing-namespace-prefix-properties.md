---
title: "更改命名空间前缀属性"
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3cb0db0fbffa5f42fb09f29da2976727451e3741
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="changing-namespace-prefix-properties"></a>更改命名空间前缀属性
使用 XmlNode 类，可以更改与给定节点关联的命名空间前缀。 例如，下面的代码显示所更改元素的前缀。  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **输出**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 更改节点的前缀不会更改节点的命名空间。 命名空间只能在创建节点时设置。 当保持树时，可能需要在外部保存新的命名空间属性，以满足所设置的前缀的需要。 如果无法创建新的命名空间，则更改此前缀以使节点保留其本地名称和命名空间。 下面的示例显示所添加的命名空间属性。  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **输出**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 如果树由于 doc.InnerXml 调用而暂留到字符串，添加的 `xmlns:a='123'` 属性是为了暂留 `test` 元素的命名空间。 以前为 `'123'`，并保持为 `'123'`。  
  
## <a name="see-also"></a>请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
