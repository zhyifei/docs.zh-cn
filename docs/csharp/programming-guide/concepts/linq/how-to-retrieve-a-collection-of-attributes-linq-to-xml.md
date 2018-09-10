---
title: 如何：检索属性的集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: e872d0fefa5ea3c25208bf5deab42b59b5b7d5b0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526928"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>如何：检索属性的集合 (LINQ to XML) (C#)
本主题介绍 <xref:System.Xml.Linq.XElement.Attributes%2A> 方法。 此方法检索元素的属性。  
  
## <a name="example"></a>示例  
 下面的示例演示如何循环访问一个元素的属性集合。  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 此代码生成以下输出：  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>请参阅

- [LINQ to XML 轴 (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
