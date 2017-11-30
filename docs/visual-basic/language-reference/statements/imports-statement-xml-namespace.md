---
title: "Imports 语句（XML 命名空间）"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0fe6d37c58ead94f2c03736318209abb67cd6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-xml-namespace"></a>Imports 语句（XML 命名空间）
导入在 XML 文本和 XML 轴属性中使用的 XML 命名空间前缀。  
  
## <a name="syntax"></a>语法  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>部件  
 `xmlNamespacePrefix`  
 可选。 通过的 XML 元素和属性可以指字符串`xmlNamespaceName`。 如果没有`xmlNamespacePrefix`是提供，导入的 XML 命名空间是默认 XML 命名空间。 必须是有效的 XML 标识符。 有关详细信息，请参阅[名称的声明 XML 元素和属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。  
  
 `xmlNamespaceName`  
 必需。 标识要导入的 XML 命名空间的字符串。  
  
## <a name="remarks"></a>备注  
 你可以使用`Imports`语句以定义你可以使用具有 XML 文本和 XML 轴属性，或作为参数传递到的全局 XML 命名空间`GetXmlNamespace`运算符。 (有关使用信息`Imports`语句导入别名，可在代码中，其中使用类型名称请参阅[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。)通过使用声明 XML 命名空间的语法`Imports`语句等同于在 XML 中使用的语法。 因此，你可以从 XML 文件中复制的命名空间声明，并使用它在`Imports`语句。  
  
 当你想要重复创建来自相同的命名空间的 XML 元素，XML 命名空间前缀非常有用。 使用声明 XML 命名空间前缀`Imports`语句是全局也就是说，它是适用于文件中的所有代码。 在创建 XML 元素文本和 XML 轴属性的访问时，你可以使用它。 有关详细信息，请参阅[XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)和[XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)。  
  
 如果定义一个不带命名空间前缀的全局 XML 命名空间 (例如， `Imports <xmlns="http://SomeNameSpace>"`)，该命名空间被视为默认 XML 命名空间。 默认 XML 命名空间用于任何 XML 元素文本或不显式指定命名空间的 XML 特性轴属性。 如果指定的命名空间是空的命名空间，则还会使用默认命名空间 (即， `xmlns=""`)。 默认 XML 命名空间不适用于到 XML 文本中的 XML 属性或不具有命名空间的 XML 特性轴属性。  
  
 XML 命名空间中 XML 文本定义称为*本地 XML 命名空间*，优先于 XML 命名空间定义的`Imports`语句为全局。 XML 命名空间定义的`Imports`语句优先于为 Visual Basic 项目导入的 XML 命名空间。 如果 XML 文本定义的 XML 命名空间，该本地命名空间不适用于嵌入的表达式。  
  
 全局 XML 命名空间按照与.NET Framework 命名空间相同的作用域和定义规则。 因此，你可以包括`Imports`语句以定义一个全局 XML 命名空间可以在任意位置导入.NET Framework 命名空间。 这包括代码文件和项目级导入命名空间。 有关项目级导入命名空间的信息，请参阅[引用页上，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)。  
  
 每个源文件可以包含任意数量的`Imports`语句。 这些必须遵循选项声明，如`Option Strict`语句，并且它们必须位于之前编程元素声明，如`Module`或`Class`语句。  
  
## <a name="example"></a>示例  
 下面的示例导入默认 XML 命名空间和 XML 命名空间前缀使用标识`ns`。 然后，它将创建使用两个命名空间的 XML 文本。  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 此代码显示以下文本：  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>示例  
 下面的示例导入的 XML 命名空间前缀`ns`。 然后，它创建 XML 文本，使用的命名空间前缀将显示元素的最终形式。  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 此代码显示以下文本：  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 请注意，编译器为本地前缀定义从全局前缀转换的 XML 命名空间前缀。  
  
## <a name="example"></a>示例  
 下面的示例导入的 XML 命名空间前缀`ns`。 然后它使用该命名空间前缀来创建 XML 文本并访问具有限定名称 `ns:name` 的第一个子节点。  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 此代码显示以下文本：  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>另请参阅  
 [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [GetXmlNamespace 运算符](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
