---
title: "已声明的 XML 元素和特性的名称 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 846a028e076873d1978f751fdb70e93c7c6a81af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>已声明的 XML 元素和特性的名称 (Visual Basic)
本主题提供[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]命名 XML 元素和属性 XML 文本中的准则。  在 XML 文本，可以指定本地名称或限定的名称。 限定的名称由 XML 命名空间前缀、 冒号和本地名称组成。 有关 XML 命名空间前缀的详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。  
  
## <a name="rules"></a>规则  
 元素或属性中的本地名称[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]必须遵守以下规则。  
  
-   它可以开始使用命名空间。 它必须以字母字符或下划线开头 (`_`)。  
  
-   它必须包含仅字母字符、 十进制数字、 下划线、 句点 （.） 和连字符 （-）。  
  
-   它不得超过 1,024 个字符。  
  
-   出现在名称中的冒号指示命名空间划分。 因此，你可以使用冒号只能用于指定特定名称的 XML 命名空间。  
  
 此外，你应遵循以下准则。  
  
-   XML 1.0 规范保留以字符串的任何大小写变体"xml"开头的所有名称。 因此，不要使用这些名称用作元素和属性名称。  
  
### <a name="name-length-guidelines"></a>名称长度准则  
 在实践中，名称应尽可能短同时在仍然能够清楚地标识的元素的性质。 这可以提高代码的可读性，并减少行长度和源文件大小。  
  
 但是，你的名称不应为太短，它不能充分描述元素或你的代码如何使用它。 这是你代码的可读性很重要。 如果其他人尝试理解它，或你自己正在寻求通过它您在编写后很长时间，则相应的元素名称可以节省时间。  
  
## <a name="case-sensitivity-in-names"></a>在名称中的区分大小写  
 XML 元素名称是区分大小写。 这意味着当[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将只按字母顺序排列的大小写不同的两个名称进行比较，它会将其解析为不同的名称。 例如，它会`ABC`和`abc`为引用不同元素。  
  
## <a name="xml-namespaces"></a>XML 命名空间  
 在创建一个 XML 元素文本时，你可以指定的元素名称的 XML 命名空间前缀。 有关详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
