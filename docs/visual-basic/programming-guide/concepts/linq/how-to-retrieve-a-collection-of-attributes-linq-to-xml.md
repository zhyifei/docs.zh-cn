---
title: 如何：检索的特性 (LINQ to XML) 的集合 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: 691ec9edda6051ba1f598891dfb9331b85ceb278
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716605"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a><span data-ttu-id="2c901-102">如何：检索的特性 (LINQ to XML) 的集合 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c901-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="2c901-103">本主题介绍 <xref:System.Xml.Linq.XElement.Attributes%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c901-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="2c901-104">此方法检索元素的属性。</span><span class="sxs-lookup"><span data-stu-id="2c901-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c901-105">示例</span><span class="sxs-lookup"><span data-stu-id="2c901-105">Example</span></span>  
 <span data-ttu-id="2c901-106">下面的示例演示如何循环访问一个元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="2c901-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="2c901-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="2c901-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c901-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c901-108">See also</span></span>
- [<span data-ttu-id="2c901-109">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c901-109">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
