---
ms.openlocfilehash: be9933e177954dc0aced81a550ef92f2c2ca08f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803291"
---
### <a name="xslt-style-sheet-exception-message-changed"></a>XSLT 样式表异常消息已更改

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，XSLT 文件过于复杂时显示的错误消息的文本为“样式表太复杂”。在先前版本中，错误消息为“XSLT 编译错误”。取决于错误消息的文本的应用程序代码将不再有效。 但是，异常类型保持不变，因此，此更改应该不会造成实际影响。|
|建议|根据此错误条件发出的异常消息更新任何应用代码，以收到新消息，或者（最好是）更新代码以仅依赖于未更改的异常类型 (<xref:System.Xml.Xsl.XsltException?displayProperty=name>)。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
