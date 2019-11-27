---
title: XML 注释文本
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 8d9db66aabe344bd5c8f9a92ac8618b7bc1abb43
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349390"
---
# <a name="xml-comment-literal-visual-basic"></a>XML 注释文本 (Visual Basic)
表示 <xref:System.Xml.Linq.XComment> 对象的文本。  
  
## <a name="syntax"></a>语法  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`<!--`|必需。 表示 XML 注释的开头。|  
|`content`|必需。 要在 XML 注释中显示的文本。 不能包含一系列两个连字符（--），也不能以与结束标记相邻的连字符结尾。|  
|`-->`|必需。 表示 XML 注释的结尾。|  
  
## <a name="return-value"></a>返回值  
 一个 <xref:System.Xml.Linq.XComment> 对象。  
  
## <a name="remarks"></a>备注  
 XML 注释文本不包含文档内容;它们包含有关文档的信息。 XML 注释部分以序列 "-->" 结尾。 这意味着：  
  
- 不能在 XML 注释文本中使用嵌入表达式，因为嵌入式表达式分隔符是有效的 XML 注释内容。  
  
- XML 注释部分不能嵌套，因为 `content` 不能包含值 "-->"。  
  
 可以将 XML 注释文本分配给一个变量，也可以将其包含在 XML 元素文本中。  
  
> [!NOTE]
> XML 文本可以跨多行，而无需使用行继续符。 此功能使你能够从 XML 文档复制内容并将其直接粘贴到 Visual Basic 程序。  
  
 Visual Basic 编译器将 XML 注释文本转换为对 <xref:System.Xml.Linq.XComment.%23ctor%2A> 构造函数的调用。  
  
## <a name="example"></a>示例  
 下面的示例创建一个包含文本 "This is a comment" 的 XML 注释。  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XComment>
- [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
