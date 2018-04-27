---
title: XML 注释文本 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5bb8c10c28a4ab864220c1b4ce4702622e55c92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="xml-comment-literal-visual-basic"></a>XML 注释文本 (Visual Basic)
一个文本表示<xref:System.Xml.Linq.XComment>对象。  
  
## <a name="syntax"></a>语法  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`<!--`|必须的。 表示 XML 注释的开头。|  
|`content`|必须的。 若要显示的 XML 注释中的文本。 不能包含一系列的两个连字符 （-） 或靠近结束标记的连字符结尾。|  
|`-->`|必须的。 表示 XML 注释的结尾。|  
  
## <a name="return-value"></a>返回值  
 一个 <xref:System.Xml.Linq.XComment> 对象。  
  
## <a name="remarks"></a>备注  
 XML 注释文本不包含文档内容;它们包含有关文档的信息。 序列"-->"结尾的 XML 注释部分。 这意味着以下几点：  
  
-   你无法使用嵌入式的表达式 XML 注释文本中，因为嵌入式的表达式分隔符是有效的 XML 注释内容。  
  
-   XML 注释部分不能嵌套，因为`content`不能包含值"-->"。  
  
 可以将 XML 注释文本分配给一个变量，或者可以将其包含在 XML 元素文本。  
  
> [!NOTE]
>  XML 文本可以跨多行，而无需使用行继续符。 此功能，可从 XML 文档中复制内容，然后将其粘贴到 Visual Basic 程序直接。  
  
 Visual Basic 编译器将 XML 注释文本转换为调用<xref:System.Xml.Linq.XComment.%23ctor%2A>构造函数。  
  
## <a name="example"></a>示例  
 下面的示例创建包含文本的 XML 注释"这是一个注释"。  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Linq.XComment>  
 [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
