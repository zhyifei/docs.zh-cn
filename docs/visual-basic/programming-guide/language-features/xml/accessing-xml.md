---
title: 在 Visual Basic 中访问 XML
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 064e4b224d37172b8f79e57c73164b90186ef922
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-xml-in-visual-basic"></a>在 Visual Basic 中访问 XML
Visual Basic 提供用于访问和导航 XML 轴属性[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]结构。 这些属性使用特殊语法，可以通过指定的 XML 名称来访问元素和属性。  
  
 下表列出可用于访问 XML 元素和属性在 Visual Basic 中的语言功能。  
  
### <a name="xml-axis-properties"></a>XML 轴属性  
  
|属性说明|示例|描述|  
|--------------------------|-------------|-----------------|  
|*子轴*|`contact.<phone>`|获取所有`phone`是中的子元素的元素`contact`元素。|  
|*属性轴*|`phone.@type`|获取所有`type`属性`phone`元素。|  
|*子代轴*|`contacts...<name>`|获取所有`name`元素`contacts`元素，而不考虑如何深层他们发生层次结构中。|  
|*扩展索引器*|`contacts...<name>(0)`|获取第一个`name`从序列的元素。|  
|*value*|`contacts...<name>.Value`|序列中获取的字符串表示形式的第一个对象或`Nothing`如果序列为空。|  
  
## <a name="in-this-section"></a>本节内容  
 [如何：访问 XML 子代元素](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 演示如何使用子代轴属性来访问具有指定的名称和指定的 XML 元素下包含的所有 XML 元素。  
  
 [如何：访问 XML 子元素](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。  
  
 [如何：访问 XML 特性](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 演示如何使用特性轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 特性。  
  
 [如何：声明和使用 XML 命名空间前缀](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 演示如何声明 XML 命名空间前缀，并使用它来创建和访问 XML 元素。  
  
## <a name="related-sections"></a>相关章节  
 [XML 轴属性](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 提供指向介绍各种 XML 访问属性的章节。  
  
 [Visual Basic 中的 LINQ to XML 概述](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 提供介绍了如何使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。  
  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 提供在 Visual Basic 中使用 XML 文本的说明。  
  
 [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 提供指向有关加载和修改 Visual Basic 中的 XML 的章节。  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 提供指向介绍如何使用章节[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。
