---
title: "GetXmlNamespace 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace 运算符 (Visual Basic)
获取<xref:System.Xml.Linq.XNamespace>对应于指定的 XML 命名空间前缀的对象。  
  
## <a name="syntax"></a>语法  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>部件  
 `xmlNamespacePrefix`  
 可选。 标识 XML 命名空间前缀的字符串。 如果提供，此字符串必须是有效的 XML 标识符。 有关详细信息，请参阅[名称的声明 XML 元素和属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。 如果不指定任何前缀，则返回默认命名空间。 如果指定默认命名空间，则返回空命名空间。  
  
## <a name="return-value"></a>返回值  
 <xref:System.Xml.Linq.XNamespace>对应于 XML 命名空间前缀的对象。  
  
## <a name="remarks"></a>备注  
 `GetXmlNamespace`运算符获取<xref:System.Xml.Linq.XNamespace>对应于 XML 命名空间前缀的对象`xmlNamespacePrefix`。  
  
 你可以使用直接在 XML 文本和 XML 轴属性中的 XML 命名空间前缀。 但是，你必须使用`GetXmlNamespace`运算符以转换到的命名空间前缀<xref:System.Xml.Linq.XNamespace>对象，然后你可以在代码中使用它。 你可以将附加到的非限定的元素名称<xref:System.Xml.Linq.XNamespace>要获取完全限定对象<xref:System.Xml.Linq.XName>对象，哪些多[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]方法需要。  
  
## <a name="example"></a>示例  
 下面的示例导入`ns`作为 XML 命名空间前缀。 然后，它使用的命名空间前缀来创建 XML 文本和访问具有限定的名称的第一个子节点`ns:phone`。 然后将其传递到该子节点`ShowName`子例程，通过构造一个限定的名`GetXmlNamespace`运算符。 `ShowName`子例程随后将传递到的限定的名称<xref:System.Xml.Linq.XNode.Ancestors%2A>方法要获取其父类`ns:contact`节点。  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 当调用`TestGetXmlNamespace.RunSample()`，它将显示一个消息框，包含以下文本：  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>另请参阅  
 [Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [在 Visual Basic 中访问 XML](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
