---
title: 如何：检索特性的值 (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: d03b2b146ad2f6b796ba6589cf99d06aa429535d
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710494"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="548b4-102">如何：检索特性的值 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="548b4-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="548b4-103">本主题说明如何获取属性的值。</span><span class="sxs-lookup"><span data-stu-id="548b4-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="548b4-104">主要有两种方法：可以将 <xref:System.Xml.Linq.XAttribute> 强制转换为所需的类型；然后，显式转换运算符将元素或属性的内容转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="548b4-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="548b4-105">此外，还可以使用 <xref:System.Xml.Linq.XAttribute.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="548b4-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="548b4-106">但是，强制转换通常是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="548b4-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="548b4-107">在检索可能存在也可能不存在的属性的值时，如果将属性强制转换为可以为 null 的类型，则代码会更易于编写。</span><span class="sxs-lookup"><span data-stu-id="548b4-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="548b4-108">有关此技术的示例，请参见[如何：检索元素 (LINQ to XML) 的值 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="548b4-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="548b4-109">示例</span><span class="sxs-lookup"><span data-stu-id="548b4-109">Example</span></span>  
 <span data-ttu-id="548b4-110">在 Visual Basic 中，可以使用集成的属性 (Attribute) 属性 (Property) 来检索属性 (Attribute) 的值。</span><span class="sxs-lookup"><span data-stu-id="548b4-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="548b4-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="548b4-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="548b4-112">示例</span><span class="sxs-lookup"><span data-stu-id="548b4-112">Example</span></span>  
 <span data-ttu-id="548b4-113">在 Visual Basic 中，可以使用集成的属性 (Attribute) 属性 (Property) 来设置属性 (Attribute) 的值。</span><span class="sxs-lookup"><span data-stu-id="548b4-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="548b4-114">此外，如果使用集成的属性 (Attribute) 属性 (Property) 来设置不存在的属性 (Attribute) 的值，则会创建该属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="548b4-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="548b4-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="548b4-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="548b4-116">示例</span><span class="sxs-lookup"><span data-stu-id="548b4-116">Example</span></span>  
 <span data-ttu-id="548b4-117">下面的示例演示在属性处于命名空间中时，如何检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="548b4-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="548b4-118">有关详细信息, 请参阅[命名空间概述 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="548b4-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="548b4-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="548b4-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="548b4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="548b4-120">See also</span></span>

- [<span data-ttu-id="548b4-121">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="548b4-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
