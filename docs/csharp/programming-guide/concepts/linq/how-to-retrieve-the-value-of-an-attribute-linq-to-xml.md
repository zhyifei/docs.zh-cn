---
title: 如何：检索特性的值 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 94cab43571f7ade55155e7925975f253e452ceb7
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485005"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="d3fc1-102">如何：检索特性的值 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d3fc1-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="d3fc1-103">本主题说明如何获取属性的值。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="d3fc1-104">主要有两种方法：可以将 <xref:System.Xml.Linq.XAttribute> 强制转换为所需的类型；然后，显式转换运算符将元素或属性的内容转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="d3fc1-105">此外，还可以使用 <xref:System.Xml.Linq.XAttribute.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="d3fc1-106">但是，强制转换通常是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="d3fc1-107">在检索可能存在也可能不存在的属性的值时，如果将属性强制转换为可以为 null 的类型，则代码会更易于编写。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="d3fc1-108">有关此技术的示例，请参见[如何：检索元素的值 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3fc1-109">示例</span><span class="sxs-lookup"><span data-stu-id="d3fc1-109">Example</span></span>  
 <span data-ttu-id="d3fc1-110">若要检索属性的值，只需将 <xref:System.Xml.Linq.XAttribute> 对象强制转换为所需的类型即可。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="d3fc1-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d3fc1-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="d3fc1-112">示例</span><span class="sxs-lookup"><span data-stu-id="d3fc1-112">Example</span></span>  
 <span data-ttu-id="d3fc1-113">下面的示例演示在属性处于命名空间中时，如何检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="d3fc1-114">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fc1-114">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="d3fc1-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d3fc1-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3fc1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3fc1-116">See also</span></span>

- [<span data-ttu-id="d3fc1-117">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="d3fc1-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
