---
title: "如何：检索属性的值 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 12720ca8bd1937d37f8d30400e0b25afa22a40cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="c1960-102">如何：检索属性的值 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c1960-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="c1960-103">本主题说明如何获取属性的值。</span><span class="sxs-lookup"><span data-stu-id="c1960-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="c1960-104">主要方法有两种：可以将 <xref:System.Xml.Linq.XAttribute> 强制转换为所需的类型；然后，显式转换运算符将元素或属性的内容转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="c1960-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="c1960-105">此外，还可以使用 <xref:System.Xml.Linq.XAttribute.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c1960-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="c1960-106">但是，强制转换通常是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="c1960-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="c1960-107">在检索可能存在也可能不存在的属性的值时，如果将属性强制转换为可以为 null 的类型，则代码会更易于编写。</span><span class="sxs-lookup"><span data-stu-id="c1960-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="c1960-108">有关此技术的示例，请参阅[如何：检索元素的值 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="c1960-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1960-109">示例</span><span class="sxs-lookup"><span data-stu-id="c1960-109">Example</span></span>  
 <span data-ttu-id="c1960-110">若要检索属性的值，只需将 <xref:System.Xml.Linq.XAttribute> 对象强制转换为所需的类型即可。</span><span class="sxs-lookup"><span data-stu-id="c1960-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c1960-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c1960-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="c1960-112">示例</span><span class="sxs-lookup"><span data-stu-id="c1960-112">Example</span></span>  
 <span data-ttu-id="c1960-113">下面的示例演示在属性处于命名空间中时，如何检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="c1960-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="c1960-114">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="c1960-114">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c1960-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c1960-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1960-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1960-116">See Also</span></span>  
 [<span data-ttu-id="c1960-117">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="c1960-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
