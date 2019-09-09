---
title: 如何：检索属性集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: b1721de5ac396faab010dab691bfd88991bad638
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253438"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="f14a5-102">如何：检索属性集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f14a5-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="f14a5-103">本主题介绍 <xref:System.Xml.Linq.XElement.Attributes%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f14a5-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="f14a5-104">此方法检索元素的属性。</span><span class="sxs-lookup"><span data-stu-id="f14a5-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14a5-105">示例</span><span class="sxs-lookup"><span data-stu-id="f14a5-105">Example</span></span>  
 <span data-ttu-id="f14a5-106">下面的示例演示如何循环访问一个元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="f14a5-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="f14a5-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="f14a5-107">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="f14a5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f14a5-108">See also</span></span>

- [<span data-ttu-id="f14a5-109">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="f14a5-109">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
