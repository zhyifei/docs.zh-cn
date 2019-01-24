---
title: 如何：使用 XSD (LINQ to XML) 进行验证 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
ms.openlocfilehash: 9e4250ac1da4b25ce3f1644b38ff0e71693ecc57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691211"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="da650-102">如何：使用 XSD (LINQ to XML) 进行验证 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da650-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="da650-103"><xref:System.Xml.Schema> 命名空间包含扩展方法，这些扩展方法可以简化针对 XML 架构定义语言 (XSD) 文件验证 XML 树的过程。</span><span class="sxs-lookup"><span data-stu-id="da650-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="da650-104">有关更多信息，请参见 <xref:System.Xml.Schema.Extensions.Validate%2A> 方法文档。</span><span class="sxs-lookup"><span data-stu-id="da650-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da650-105">示例</span><span class="sxs-lookup"><span data-stu-id="da650-105">Example</span></span>  
 <span data-ttu-id="da650-106">下面的示例创建一个 <xref:System.Xml.Schema.XmlSchemaSet>，然后针对架构集验证两个 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="da650-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="da650-107">其中一个文档为有效文档，而另一个则不是。</span><span class="sxs-lookup"><span data-stu-id="da650-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="da650-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="da650-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="da650-109">示例</span><span class="sxs-lookup"><span data-stu-id="da650-109">Example</span></span>  
 <span data-ttu-id="da650-110">下面的示例验证的 XML 文档从[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)根据从架构有效[示例 XSD 文件：客户和订单](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)。</span><span class="sxs-lookup"><span data-stu-id="da650-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="da650-111">然后修改源 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="da650-111">It then modifies the source XML document.</span></span> <span data-ttu-id="da650-112">它更改第一个客户的 `CustomerID` 属性。</span><span class="sxs-lookup"><span data-stu-id="da650-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="da650-113">更改后，订单将指向不存在的客户，因此该 XML 文档不再有效。</span><span class="sxs-lookup"><span data-stu-id="da650-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="da650-114">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="da650-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="da650-115">本示例使用下面的 XSD 架构：[示例 XSD 文件：客户和订单](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)。</span><span class="sxs-lookup"><span data-stu-id="da650-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="da650-116">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="da650-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="da650-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="da650-117">See also</span></span>
- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="da650-118">创建 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da650-118">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
