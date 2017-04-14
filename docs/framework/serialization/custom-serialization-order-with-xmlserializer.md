---
title: "使用 XmlSerializer 自定义序列化顺序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 使用 XmlSerializer 自定义序列化顺序
[下载示例](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 此示例演示如何控制序列化和反序列化元素的顺序来进行 XML 序列化。  
  
 有关序列化的更多信息，请查看源代码中的注释以及 build.proj 文件。  
  
### 使用命令提示生成示例  
  
1.  打开命令提示窗口，然后定位到该示例的语言特定子目录之一。  
  
2.  在命令行中键入 **msbuild CustomOrder.sln**。  
  
### 使用 Visual Studio 生成示例  
  
1.  打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到该示例的语言特定的子目录之一。  
  
2.  双击 CustomOrder.sln 的图标，在 Visual Studio 中打开该文件。  
  
3.  在**“生成”**菜单中选择**“生成解决方案”**。  
  
4.  示例应用程序将在默认的 \\bin 或 \\bin\\Debug 子目录中生成。  
  
## 请参阅  
 [System.Runtime.Serialization 命名空间](frlrfSystemRuntimeSerialization)   
 [System.Xml.Serialization 命名空间](frlrfSystemXmlSerialization)   
 [基本序列化](../../../docs/framework/serialization/basic-serialization.md)   
 [二进制序列化](../../../docs/framework/serialization/binary-serialization.md)   
 [使用特性控制 XML 序列化](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [XML 序列化简介](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [序列化](../../../docs/framework/serialization/index.md)   
 [SOAP Service](http://msdn.microsoft.com/zh-cn/2051c992-28d1-499e-961f-17e9b675cec9)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)