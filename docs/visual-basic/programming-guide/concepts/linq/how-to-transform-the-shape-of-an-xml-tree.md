---
title: "如何： 转换 XML 树 (Visual Basic) 的形状"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cad7e5fc53b59593cf0c367d65d5bd44564bb1c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="de054-102">如何： 转换 XML 树 (Visual Basic) 的形状</span><span class="sxs-lookup"><span data-stu-id="de054-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="de054-103">XML 文档的*形状*是指它的元素名称、属性名称以及它的层次结构的特征。</span><span class="sxs-lookup"><span data-stu-id="de054-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="de054-104">有时，您将不得不更改 XML 文档的形状。</span><span class="sxs-lookup"><span data-stu-id="de054-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="de054-105">例如，您可能必须将一个现有 XML 文档发送到另一个系统，而该系统要求使用不同的元素和属性名称。</span><span class="sxs-lookup"><span data-stu-id="de054-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="de054-106">你可以在整个文档中，根据需要删除和重命名元素，但是，如果使用函数构造，则可获得可读性更强、更易于维护的代码。</span><span class="sxs-lookup"><span data-stu-id="de054-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="de054-107">函数构造有关的详细信息，请参阅[函数构造 (LINQ to XML) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="de054-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="de054-108">第一个示例更改 XML 文档的组织结构。</span><span class="sxs-lookup"><span data-stu-id="de054-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="de054-109">它将复杂元素从树中的一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="de054-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="de054-110">本主题的第二个示例创建一个 XML 文档，该文档具有与源文档不同的形状。</span><span class="sxs-lookup"><span data-stu-id="de054-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="de054-111">它更改元素名称的大小写，重命名某些元素，转换后的树中不包含源树的某些元素。</span><span class="sxs-lookup"><span data-stu-id="de054-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de054-112">示例</span><span class="sxs-lookup"><span data-stu-id="de054-112">Example</span></span>  
 <span data-ttu-id="de054-113">下面的代码使用嵌入式查询表达式更改 XML 文件的形状。</span><span class="sxs-lookup"><span data-stu-id="de054-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="de054-114">本示例中的源 XML 文档在 `Customers` 元素（它包含所有客户）下包含一个 `Root` 元素。</span><span class="sxs-lookup"><span data-stu-id="de054-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="de054-115">此外，在 `Orders` 元素（包含所有订单）下包含一个 `Root` 元素。</span><span class="sxs-lookup"><span data-stu-id="de054-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="de054-116">本示例创建一个新的 XML 树，在该树中，每个客户的订单都包含在 `Orders` 元素内的 `Customer` 元素中。</span><span class="sxs-lookup"><span data-stu-id="de054-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="de054-117">原始文档还在 `CustomerID` 元素中包含一个 `Order` 元素；此元素将从重新变形的文档中移除。</span><span class="sxs-lookup"><span data-stu-id="de054-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="de054-118">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="de054-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="de054-119">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="de054-119">This code produces the following output:</span></span>  
  
```xml  
        <Root>  
<Customer CustomerID="GREAL">  
  <CompanyName>Great Lakes Food Market</CompanyName>  
  <ContactName>Howard Snyder</ContactName>  
  <ContactTitle>Marketing Manager</ContactTitle>  
  <Phone>(503) 555-7555</Phone>  
  <FullAddress>  
    <Address>2732 Baker Blvd.</Address>  
    <City>Eugene</City>  
    <Region>OR</Region>  
    <PostalCode>97403</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
. . .  
```  
  
## <a name="example"></a><span data-ttu-id="de054-120">示例</span><span class="sxs-lookup"><span data-stu-id="de054-120">Example</span></span>  
 <span data-ttu-id="de054-121">本示例重命名某些元素并将某些属性转换为元素。</span><span class="sxs-lookup"><span data-stu-id="de054-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="de054-122">代码调用 `ConvertAddress`，它返回一个 <xref:System.Xml.Linq.XElement> 对象列表。</span><span class="sxs-lookup"><span data-stu-id="de054-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="de054-123">此方法的参数是一个查询，该查询确定 `Address` 属性值为 `Type` 的 `"Shipping"` 复杂元素。</span><span class="sxs-lookup"><span data-stu-id="de054-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="de054-124">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="de054-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="de054-125">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="de054-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de054-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de054-126">See Also</span></span>  
 [<span data-ttu-id="de054-127">投影和转换 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de054-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
