---
title: 在 Visual Basic 中访问 XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734377"
---
# <a name="accessing-xml-in-visual-basic"></a>在 Visual Basic 中访问 XML
Visual Basic 提供了用于访问和导航 XML 轴属性[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]结构。 这些属性使用特殊语法，可以通过指定的 XML 名称来访问元素和属性。  
  
 下表列出了使你能够访问 XML 元素和属性在 Visual Basic 中的语言功能。  
  
### <a name="xml-axis-properties"></a>XML 轴属性  
  
|属性说明|示例|描述|  
|--------------------------|-------------|-----------------|  
|*子轴*|`contact.<phone>`|获取所有`phone`元素的子元素的`contact`元素。|  
|*attribute 轴*|`phone.@type`|获取所有`type`的属性`phone`元素。|  
|*descendant 轴*|`contacts...<name>`|获取所有`name`的元素`contacts`元素，而不考虑它们在层次结构中深度。|  
|*扩展索引器*|`contacts...<name>(0)`|获取第一个`name`序列中的元素。|  
|*value*|`contacts...<name>.Value`|获取在序列中，第一个对象的字符串表示形式或`Nothing`如果序列为空。|  
  
## <a name="in-this-section"></a>本节内容  
 [如何：访问 XML 子代元素](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 演示如何使用子代轴属性访问具有指定的名称并且包含指定的 XML 元素下的所有 XML 元素。  
  
 [如何：访问 XML 子元素](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。  
  
 [如何：访问 XML 特性](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 演示如何使用特性轴属性访问某个 XML 元素中具有指定的名称的所有 XML 属性。  
  
 [如何：声明和使用 XML 命名空间前缀](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 演示如何声明 XML 命名空间前缀，并使用它来创建和访问 XML 元素。  
  
## <a name="related-sections"></a>相关章节  
 [XML 轴属性](../../../../visual-basic/language-reference/xml-axis/index.md)  
 提供指向介绍各种 XML 访问属性的章节。  
  
 [Visual Basic 中的 LINQ to XML 概述](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 介绍了使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。  
  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 提供介绍如何在 Visual Basic 中使用 XML 文本。  
  
 [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 提供有关加载和修改 Visual Basic 中的 XML 部分的链接。  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 提供指向介绍如何使用章节[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。
