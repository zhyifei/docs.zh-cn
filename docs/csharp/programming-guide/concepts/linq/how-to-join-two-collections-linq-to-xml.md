---
title: "如何：联接两个集合 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1ca088637629453b9d9f801b576ff195844c0bd1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="cdfd0-102">如何：联接两个集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cdfd0-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="cdfd0-103">XML 文档中的元素或属性有时可以引用另一个其他元素或属性。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="cdfd0-104">例如，[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML 文档包含一个客户列表和一个订单列表。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="cdfd0-105">每个 `Customer` 元素都包含一个 `CustomerID` 属性。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="cdfd0-106">每个 `Order` 元素都包含一个 `CustomerID` 元素。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="cdfd0-107">每个订单中的 `CustomerID` 元素都引用客户中的 `CustomerID` 属性。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="cdfd0-108">主题[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)包含一个可用于验证此文档的 XSD。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-108">The topic [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="cdfd0-109">它使用 XSD 的 `xs:key` 和 `xs:keyref` 功能，将 `CustomerID` 元素的 `Customer` 属性设置为键，并在每个 `CustomerID` 元素的 `Order` 元素和每个 `CustomerID` 元素的 `Customer` 属性之间建立关系。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="cdfd0-110">使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，可以通过使用 `join` 子句利用这种关系。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="cdfd0-111">请注意，由于没有可用的索引，这种联接的运行时性能较差。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="cdfd0-112">有关 `join` 的详细信息，请参阅[联接操作 (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-112">For more detailed information about `join`, see [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdfd0-113">示例</span><span class="sxs-lookup"><span data-stu-id="cdfd0-113">Example</span></span>  
 <span data-ttu-id="cdfd0-114">下面的示例将 `Customer` 元素与 `Order` 元素联接在一起，并生成一个新的 XML 文档，该文档包含订单中的 `CompanyName` 元素。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="cdfd0-115">执行查询之前，此示例验证文档是否符合[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)中的架构。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="cdfd0-116">这样可确保联接子句始终能运行。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="cdfd0-117">此查询首先检索所有 `Customer` 元素，然后将它们联接到 `Order` 元素。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="cdfd0-118">此查询仅选择 `CustomerID` 大于“K”的客户的订单。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="cdfd0-119">然后投影一个新的 `Order` 元素，该元素包含每个订单内的客户信息。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="cdfd0-120">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="cdfd0-121">本示例使用下面的 XSD 架构：[示例 XSD 文件：客户和订单](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="cdfd0-122">请注意，这种方式的联接将不能很好地执行。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="cdfd0-123">联接是通过线性搜索执行的。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="cdfd0-124">没有任何哈希表或索引来帮助改善性能。</span><span class="sxs-lookup"><span data-stu-id="cdfd0-124">There are no hash tables or indexes to help with performance.</span></span>  
  
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
  
 <span data-ttu-id="cdfd0-125">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="cdfd0-125">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cdfd0-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdfd0-126">See Also</span></span>  
 [<span data-ttu-id="cdfd0-127">高级查询技术 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cdfd0-127">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

