---
title: 如何：联接两个集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: 893966f3b803b92efbc89a65870623f10195c85f
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485376"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="21b32-102">如何：联接两个集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="21b32-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="21b32-103">XML 文档中的元素或属性有时可以引用另一个其他元素或属性。</span><span class="sxs-lookup"><span data-stu-id="21b32-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="21b32-104">例如，[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML 文档包含客户列表和订单列表。</span><span class="sxs-lookup"><span data-stu-id="21b32-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="21b32-105">每个 `Customer` 元素都包含一个 `CustomerID` 属性。</span><span class="sxs-lookup"><span data-stu-id="21b32-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="21b32-106">每个 `Order` 元素都包含一个 `CustomerID` 元素。</span><span class="sxs-lookup"><span data-stu-id="21b32-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="21b32-107">每个订单中的 `CustomerID` 元素都引用客户中的 `CustomerID` 属性。</span><span class="sxs-lookup"><span data-stu-id="21b32-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="21b32-108">主题[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)包含可用于验证此文档的 XSD。</span><span class="sxs-lookup"><span data-stu-id="21b32-108">The topic [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="21b32-109">它使用 XSD 的 `xs:key` 和 `xs:keyref` 功能，将 `CustomerID` 元素的 `Customer` 属性设置为键，并在每个 `CustomerID` 元素的 `Order` 元素和每个 `CustomerID` 元素的 `Customer` 属性之间建立关系。</span><span class="sxs-lookup"><span data-stu-id="21b32-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="21b32-110">使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，可以通过使用 `join` 子句利用这种关系。</span><span class="sxs-lookup"><span data-stu-id="21b32-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="21b32-111">请注意，由于没有可用的索引，这种联接的运行时性能较差。</span><span class="sxs-lookup"><span data-stu-id="21b32-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="21b32-112">有关 `join` 的详细信息，请参阅[联接操作 (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="21b32-112">For more detailed information about `join`, see [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21b32-113">示例</span><span class="sxs-lookup"><span data-stu-id="21b32-113">Example</span></span>  
 <span data-ttu-id="21b32-114">下面的示例将 `Customer` 元素与 `Order` 元素联接在一起，并生成一个新的 XML 文档，该文档包含订单中的 `CompanyName` 元素。</span><span class="sxs-lookup"><span data-stu-id="21b32-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="21b32-115">执行查询之前，示例确认文档符合[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)中的架构。</span><span class="sxs-lookup"><span data-stu-id="21b32-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="21b32-116">这样可确保联接子句始终能运行。</span><span class="sxs-lookup"><span data-stu-id="21b32-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="21b32-117">此查询首先检索所有 `Customer` 元素，然后将它们联接到 `Order` 元素。</span><span class="sxs-lookup"><span data-stu-id="21b32-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="21b32-118">此查询仅选择 `CustomerID` 大于“K”的客户的订单。</span><span class="sxs-lookup"><span data-stu-id="21b32-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="21b32-119">然后投影一个新的 `Order` 元素，该元素包含每个订单内的客户信息。</span><span class="sxs-lookup"><span data-stu-id="21b32-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="21b32-120">此示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)。</span><span class="sxs-lookup"><span data-stu-id="21b32-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="21b32-121">此示例使用以下 XSD 架构：[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)。</span><span class="sxs-lookup"><span data-stu-id="21b32-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="21b32-122">请注意，这种方式的联接将不能很好地执行。</span><span class="sxs-lookup"><span data-stu-id="21b32-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="21b32-123">联接是通过线性搜索执行的。</span><span class="sxs-lookup"><span data-stu-id="21b32-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="21b32-124">没有任何哈希表或索引来帮助改善性能。</span><span class="sxs-lookup"><span data-stu-id="21b32-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.Write("Attempting to validate, ");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
if (!errors)  
{  
    // Join customers and orders, and create a new XML document with  
    // a different shape.  
  
    // The new document contains orders only for customers with a  
    // CustomerID > 'K'  
    XElement custOrd = custOrdDoc.Element("Root");  
    XElement newCustOrd = new XElement("Root",  
        from c in custOrd.Element("Customers").Elements("Customer")  
        join o in custOrd.Element("Orders").Elements("Order")  
                   on (string)c.Attribute("CustomerID") equals  
                      (string)o.Element("CustomerID")  
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0  
        select new XElement("Order",  
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),  
            new XElement("CompanyName", (string)c.Element("CompanyName")),  
            new XElement("ContactName", (string)c.Element("ContactName")),  
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),  
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))  
        )  
    );  
    Console.WriteLine(newCustOrd);  
}  
```  
  
 <span data-ttu-id="21b32-125">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="21b32-125">This code produces the following output:</span></span>  
  
```  
Attempting to validate, custOrdDoc validated  
<Root>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-03-21T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-05-22T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-06-25T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-10-27T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>6</EmployeeID>  
    <OrderDate>1997-11-10T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>4</EmployeeID>  
    <OrderDate>1998-02-12T00:00:00</OrderDate>  
  </Order>  
</Root>  
```  
