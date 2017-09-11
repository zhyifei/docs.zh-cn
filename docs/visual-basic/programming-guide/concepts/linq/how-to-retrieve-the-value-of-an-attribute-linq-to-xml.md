---
title: "如何︰ 检索特性 (LINQ to XML) 的值 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 6ecc1368832b9c98efeae65c95438efb80f164f6
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="3ec8f-102">如何︰ 检索特性 (LINQ to XML) 的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ec8f-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3ec8f-103">本主题说明如何获取属性的值。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="3ec8f-104">有两种主要方法︰ 您可以强制转换<xref:System.Xml.Linq.XAttribute>为所需的类型; 显式转换运算符将元素或属性设置为指定类型的内容。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="3ec8f-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="3ec8f-105">或者，可以使用<xref:System.Xml.Linq.XAttribute.Value%2A>属性。</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="3ec8f-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="3ec8f-106">但是，强制转换通常是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="3ec8f-107">在检索可能存在也可能不存在的属性的值时，如果将属性强制转换为可以为 null 的类型，则代码会更易于编写。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="3ec8f-108">有关此技术的示例，请参阅[如何︰ 检索元素 (LINQ to XML) 的值 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ec8f-109">示例</span><span class="sxs-lookup"><span data-stu-id="3ec8f-109">Example</span></span>  
 <span data-ttu-id="3ec8f-110">在 Visual Basic 中，可以使用集成的属性 (Attribute) 属性 (Property) 来检索属性 (Attribute) 的值。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="3ec8f-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="3ec8f-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="3ec8f-112">示例</span><span class="sxs-lookup"><span data-stu-id="3ec8f-112">Example</span></span>  
 <span data-ttu-id="3ec8f-113">在 Visual Basic 中，可以使用集成的属性 (Attribute) 属性 (Property) 来设置属性 (Attribute) 的值。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="3ec8f-114">此外，如果使用集成的属性 (Attribute) 属性 (Property) 来设置不存在的属性 (Attribute) 的值，则会创建该属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="3ec8f-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="3ec8f-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="3ec8f-116">示例</span><span class="sxs-lookup"><span data-stu-id="3ec8f-116">Example</span></span>  
 <span data-ttu-id="3ec8f-117">下面的示例演示在属性处于命名空间中时，如何检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="3ec8f-118">有关详细信息，请参阅[处理 XML 命名空间 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec8f-118">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="3ec8f-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="3ec8f-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ec8f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ec8f-120">See Also</span></span>  
 [<span data-ttu-id="3ec8f-121">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ec8f-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
