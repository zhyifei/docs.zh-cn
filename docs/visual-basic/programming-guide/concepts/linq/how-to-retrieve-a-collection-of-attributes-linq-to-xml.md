---
title: "如何： 检索特性 (LINQ to XML) 的集合 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 934559b5c27d243930c191dd3d601fbf8c5beb65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a>如何： 检索特性 (LINQ to XML) 的集合 (Visual Basic)
本主题介绍 <xref:System.Xml.Linq.XElement.Attributes%2A> 方法。 此方法检索元素的属性。  
  
## <a name="example"></a>示例  
 下面的示例演示如何循环访问一个元素的属性集合。  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 此代码生成以下输出：  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>另请参阅  
 [LINQ to XML 轴 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
