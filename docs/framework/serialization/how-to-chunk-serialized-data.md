---
title: "如何：对序列化数据进行分块 | Microsoft Docs"
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
helpviewer_keywords: 
  - "二进制序列化, 对数据进行分块"
  - "二进制序列化, 示例"
  - "对序列化数据进行分块"
  - "对数据进行分块"
  - "对大型数据集进行分块"
  - "序列化, 对数据进行分块"
  - "序列化, 示例"
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 如何：对序列化数据进行分块
在 Web 服务消息中发送大型数据集时，会出现下面两个问题：  
  
1.  因序列化引擎执行缓冲而使工作集（内存）很大。  
  
2.  因使用 Base64 编码后产生 33% 的膨胀而过度占用带宽。  
  
 若要解决这两个问题，可以通过实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口，来控制序列化和反序列化。具体来讲，就是实现 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> 和 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 方法，对数据进行分块。  
  
### 实现服务器端数据分块  
  
1.  在服务器计算机上，必须采用 Web 方法禁用 ASP.NET 缓冲，并返回实现 <xref:System.Xml.Serialization.IXmlSerializable> 的类型。  
  
2.  实现 <xref:System.Xml.Serialization.IXmlSerializable> 的类型可以采用 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> 方法对数据进行分块。  
  
### 实现客户端处理  
  
1.  通过更改客户端代理上的 Web 方法，可以返回实现 <xref:System.Xml.Serialization.IXmlSerializable> 的类型。可以使用 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> 自动执行这项操作，但此处不加以说明。  
  
2.  通过实现 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 方法，可以读取分块数据流，并将字节写入磁盘。此实现还会引发可供图形控件（如进度栏）使用的进度事件。  
  
## 示例  
 下面的代码示例演示客户端上用于禁用 ASP.NET 缓冲的 Web 方法。它还演示了如何在客户端实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口，该实现可以采用 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> 方法对数据进行分块。  
  
 [!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
 [!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## 编译代码  
  
-   代码使用下面的命名空间：<xref:System>、<xref:System.Runtime.Serialization>、<xref:System.Web.Services>、<xref:System.Web.Services.Protocols>、<xref:System.Xml>、<xref:System.Xml.Serialization> 和 <xref:System.Xml.Schema>。  
  
## 请参阅  
 [自定义序列化](../../../docs/framework/serialization/custom-serialization.md)