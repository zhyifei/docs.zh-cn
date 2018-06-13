---
title: 已声明的 XML 元素和特性的名称 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 9b586936281bfbf2dcace7cf2892bebf305fc842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650421"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>已声明的 XML 元素和特性的名称 (Visual Basic)
本主题提供 Visual Basic 准则命名 XML 元素和 XML 文本中的属性。  在 XML 文本，可以指定本地名称或限定的名称。 限定的名称由 XML 命名空间前缀、 冒号和本地名称组成。 有关 XML 命名空间前缀的详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。  
  
## <a name="rules"></a>规则  
 元素或在 Visual Basic 中的属性的本地名称必须遵守以下规则。  
  
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
 XML 元素名称是区分大小写。 这意味着 Visual Basic 编译器在比较时只字母大小写不同的两个名称，将其解释为不同的名称。 例如，它会`ABC`和`abc`为引用不同元素。  
  
## <a name="xml-namespaces"></a>XML 命名空间  
 在创建一个 XML 元素文本时，你可以指定的元素名称的 XML 命名空间前缀。 有关详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
