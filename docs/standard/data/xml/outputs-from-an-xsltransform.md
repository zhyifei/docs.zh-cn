---
title: XslTransform 的输出
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 647f3829f4b26791c063d5646669b2fcb7ab6684
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="outputs-from-an-xsltransform"></a>XslTransform 的输出
样式表可以结合使用 `<xsl:output>` 语句和 `method` 属性来确定输出格式，下表说明了使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法写入输出并将输出格式声明为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter> 时的输出格式。  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。 可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。 请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。  
  
 样式表可以结合使用 `<xsl:output>` 语句和 `method` 属性来确定输出格式，下表说明了使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法写入输出并将输出格式声明为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter> 时的输出格式。 下表说明了结合使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法和 `<xsl:output>` 语句来声明输出类型时的结果：  
  
|\<xsl:output method = > attribute|结果格式|  
|-----------------------------------------|-------------------|  
|method="xml"|XML|  
|method="html"|HTML|  
|method="text"|Text|  
  
> [!NOTE]
>  注意：当 `<xsl:output>` 方法的输出为 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 或 <xref:System.Xml.XmlReader> 时，将忽略 <xref:System.Xml.XmlWriter> 语句。  
  
 如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法的输出为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter>，将支持下列属性：  
  
-   encoding*  
  
-   omit-xml-declaration  
  
-   独立  
  
-   doctype-public  
  
-   doctype-system  
  
-   cdata-section-elements  
  
-   indent  
  
    > [!NOTE]
    >  *如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法将其输出发送到 <xref:System.IO.TextWriter>，将忽略 encoding 属性。 而是改用 <xref:System.IO.TextWriter> 的 encoding 属性。  
  
 如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法的输出为 <xref:System.IO.Stream> 时，将忽略下列属性：  
  
-   version：版本始终为 1.0  
  
-   media-type：媒体类型  
  
## <a name="escaping-special-characters"></a>转义特殊字符  
 `<xsl:text disable-output-escaping>` 标记用于指示特殊字符是需要转义为 XML 形式（例如使用 `<&lt>` 替代 `"<"` 符号）还是保持现在的状态。 如果转换为 `disable-output-escaping` 或 <xref:System.Xml.XmlReader> 对象，将忽略 <xref:System.Xml.XmlWriter> 属性，对特殊字符没有影响。  
  
## <a name="see-also"></a>另请参阅  
 [XslTransform 类实现 XSLT 处理器](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
