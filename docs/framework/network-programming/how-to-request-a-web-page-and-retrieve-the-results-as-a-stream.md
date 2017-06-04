---
title: "如何：请求 Web 页并以流的形式检索结果 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 如何：请求 Web 页并以流的形式检索结果
此示例演示如何请求网页和检索在流的结果。  
  
## 示例  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## 编译代码  
 此示例需要：  
  
-   对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。  
  
## 请参阅  
 [正在请求数据...](../../../docs/framework/network-programming/requesting-data.md)