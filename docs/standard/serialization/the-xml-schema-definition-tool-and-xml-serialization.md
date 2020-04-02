---
title: XML 架构定义工具和 XML 序列化
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: b51b9a0112893d9a7838155f4af051e7079c8cdd
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588393"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>XML 架构定义工具和 XML 序列化

XML 架构定义工具[（XML 架构定义工具 （Xsd.exe）](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)与 .NET 框架工具一起安装，作为&reg;Windows 软件开发工具包 （SDK） 的一部分。 该工具主要有下面两个用途：  
  
- 生成 C# 或 Visual Basic 类文件，而这些文件符合特定的 XML 架构定义语言 (XSD) 架构。 该工具将 XML 架构用作参数，并输出一个包含若干类的文件，在使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化时，这些类符合这种架构。 有关如何使用该工具生成符合特定架构的类的信息，请参阅 [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)。  
  
- 通过 .dll 或 .exe 文件生成 XML 架构文档。 若要查看已经创建或已使用特性进行修改的一组文件的架构，可以将 DLL 或 EXE 作为参数传递到该工具，以便生成 XML 架构。 有关如何使用该工具从一组类生成 XML 架构文档的信息，请参阅 [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)。  
  
有关使用该工具的详细信息，请参阅 XML[架构定义工具 （Xsd.exe）。](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)  
  
## <a name="see-also"></a>请参阅

- <xref:System.Data.DataSet>
- [XML 序列化简介](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [如何：序列化对象](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [如何：反序列化对象](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [如何：使用 XML 架构定义工具生成类和 XML 架构文档](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [XML 架构绑定支持](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
